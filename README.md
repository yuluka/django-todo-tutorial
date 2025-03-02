# Django TODO tutorial

## About

En este repo encontrarás un ejemplo básico de cómo construir una aplicación web, usando el framework de Python **Django**, para la gestión de tareas por hacer.

En este documento _README_ podrás ver los pasos que debes seguir para construir la aplicación por tu cuenta. 

## Pasos

### Creación del proyecto

Para inicializar el proyecto deberás seguir estos pasos:

1. Crear entorno virtual de Python

    Crear un entorno virtual en Python te permite trabajar en un ambiente aislado, gestionando de manera independiente las dependencias de cada proyecto. Esto evita conflictos entre versiones de librerías y garantiza un entorno más ordenado y controlado.

    Usa este comando para crearlo:

    ```bash
    python -m venv venv
    ```

    > **Nota:** El entorno puede tener el nombre que desees. En este caso, uso `venv` por convención. Además, es necesario que crees el entorno en la carpeta raíz del proyecto.

2. Activar el entorno virtual

    Una vez creado el entorno virtual, es preciso activarlo dentro de la consola que usarás para manejar y ejecutar tu proyecto. 

    Usa este comando para activarlo:

    ```bash
    ./venv/Scripts/activate
    ```

    > **Nota:** Reempla `venv` con el nombre que hayas escogido para tu entorno.

3. Seleccionar Python Interpreter

    Una vez creado, y activado, el entorno virtual, es importante asegurarse de que tu editor o IDE utilice el intérprete correcto. Esto garantiza que las dependencias instaladas en el entorno virtual sean reconocidas y usadas en tu proyecto.

    En Visual Studio Code (VS Code) debes hacer lo siguiente:

    - Abrir el **Command Palette** presionando `Ctrl + Shift + P`.
    - Escribir "Python: Select Interpreter" y presionar `Enter`.
    - Buscar el intérprete correspondiente al entorno creado. Suele estar marcado con la palabra `Recommended`.
    - Seleccionar el intérprete.

4. Instalar dependencias necesarias

    Ahora que tu entorno está preparado, deberás instalar las dependencias necesarias para usar Django.

    Ve a la consola, en VSCode puedes hacer presionando `Ctrl + J`, y ejecuta:

    ```bash
    pip install django
    ```

    > **Nota:** Asegúrate de ejecutar este comando en la consola donde el entorno virtual esté activado. En VS Code, puedes verificarlo al inicio de cada línea de la terminal, donde debería aparecer el nombre del entorno entre paréntesis, por ejemplo: `(venv) PS E:\WORKSPACE (PC)\django-todo-tutorial>`.

    Ahora puedes verificar la versión instalada de Django usando el comando:

    ```bash
    django-admin --version
    ```

5. Crear archivo `requirements.txt`

    El archivo `requirements.txt` es una lista de todas las dependencias de tu proyecto. Guardar esta lista permite que otras personas (o tú mismo en otro momento) puedan instalar fácilmente las mismas versiones de las librerías necesarias. Es importante destacar que el entorno virtual, donde se instalan estas dependencias, **no debería** subirse al repositorio o sistema de control de versiones, por lo que este archivo es clave para reproducir el entorno de trabajo correctamente.

    Para generarlo:

    ```bash
    pip freeze > requirements.txt
    ```

    > **Nota:** Este comando creará un archivo con el nombre `requirements.txt`, en caso de que no exista, con los nombres de las librerías que tengas instaladas en tu entorno virtual. En caso de que el archivo ya exista, agregará las nuevas librerías que no estén listadas en dicho archivo. 

    > **Importante:** Ejecutar este comando cada vez que hagas la instalación de nuevas librerías para mantener el archivo de requerimentos actualizado.

    Para instalar las dependencias desde el archivo (en otra máquina, por ejemplo):

    ```bash
    pip install -r requirements.txt
    ```

6. Crear proyecto Django

    Hasta este punto, todo lo que has hecho es preparar tu entorno de desarrollo. Sin embargo, es necesario que crees tu proyecto de Django, donde estará todo el código de tu aplicación.

    Para crearlo, ejecuta:

    ```bash
    django-admin startproject todo_app .
    ```

    > **Nota:** En este caso, el nombre del proyecto es `todo_app`. Sin embargo, puedes nombrarlo como desees, dependiendo de su propósito y funcionalidad.

    Ahora, puedes ejecutar tu proyecto para verificar que todo esté bien:

    ```bash
    python manage.py runserver
    ```

    > **Nota:** Al ejecutar este comando, verás información relevante sobre tu proyecto, incluyendo la URL local para acceder a él (generalmente `http://127.0.0.1:8000/`). Es normal que, al correr el proyecto por primera vez, la consola muestre texto en rojo indicando que hay migraciones pendientes. No te preocupes, esto solo significa que debes aplicarlas antes de continuar (lo verás más adelante en el tutorial).

    Al abrir la URL, deberías ver algo así:
    ![Proyecto recién creado](docs/images/basic_project_initialized.png)