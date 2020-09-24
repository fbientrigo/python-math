# Introducción



# Instrucciones

Para comenzar debes [instalar](https://docs.docker.com/get-docker/) docker. 

Luego correr mediante docker la imagen `jupyter/scipy-notebook` para poder visualizar los cuadernos (notebooks) de jupyter. Usar el siguiente comando:

    # para iniciar el contenedor en modo interactivo
    docker run \
        --rm \
        --tty \
        --interactive \
        --name jupyter \
        --publish 8888:8888 \
        --volume /$PWD/notebooks:/home/jovyan/notebooks \
        jupyter/scipy-notebook \
        start-notebook.sh \
        --NotebookApp.notebook_dir=notebooks

Luego en tu navegador ingresa a la url http://localhost:8888. Para obtener el token debes buscar en el historial de tu consola un texto similar a:

    To access the notebook, open this file in a browser:
        file:///home/jovyan/.local/share/jupyter/runtime/nbserver-6-open.html
    Or copy and paste one of these URLs:
        http://127.0.0.1:8888/?token=<token>

Donde el token se encuentra en la posicion en `<token>`. Si ejecutaste el contener con la opcion `--detached` puedes ver el token con:

    docker container logs jupyter
