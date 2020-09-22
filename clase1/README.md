# Módulo 3 Introducción a las arquitecturas y desarrollo con API Rest 
# Clase 1 

# Tabla de Contenido

<!-- toc -->

- [Instalación de Python, VSCODE, Venv y Flask](#instalación-de-python-vscode-venv-y-flask)
  - [Instalación de Python](#instalación-de-python)
  - [Instalación de VSCode](#instalación-de-vscode)
  - [Instalación del Virtual Environment](#instalación-del-virtual-environment)
  - [Instalación y Ejecución de Flask](#instalación-y-ejecución-de-flask)


<!-- tocstop -->

## Instalación de Python, VSCODE, Venv y Flask


### Instalación de Python

Ingresamos al sitio https://www.python.org/ y le damos click a Downloads

![python-1](images/python-1.png)

Descargue la versión para su sistema Operativo. En el caso de Windows Python 3.8.5

![python-2](images/python-2.png)

Una vez termine la descarga, haga doble click en el archivo, Agregar Python 3.8 al path y luego en Instalar Ahora

![python-3](images/python-3.png)

Después de terminada la instalación, haga click en Deshabilitar el límite de longitud del Path

![python-4](images/python-4.png)


### Instalación de VSCode

Ingresamos al sitio https://code.visualstudio.com/ y le damos click a Download para el sistema operativo que estemos utilizando

![python-5](images/python-5.png)

Hacemos doble click en el archivo y aceptamos los términos y condiciones

![python-6](images/python-6.png)

En la siguiente pantalla le damos click a Crear icono en el escritorio y de nuevo siguiente

![python-7](images/python-7.png)

Hacemos click en Instalar

![python-8](images/python-8.png)

Finalmente, hacemos click en Terminar y Lanzar Visual Studio Code

![python-9](images/python-9.png)

Si nos sale una alerta de Firewall, hacemos click en Permitir acceso

![python-10](images/python-10.png)

Se recomienda instalar las extensiones de Python y Python Docstring Generator. Para hacerlo deben ir a la pestaña de extensiones, buscar Python y luego hacer click en instalar

![python-11](images/python-11.png)

Para instalar Python DocString, busca python doc, seleccionan la extensión y click en Instalar

![python-12](images/python-12.png)


### Instalación del Virtual Environment

El Virtual Environment nos permite crear grupos independientes de librerías en Python para cada proyecto. Esto resuelve posibles conflictos que se pueden presentar al trabajar diferentes versiones de una librería o del mismo Python si estás son instaladas de forma global

Creamos una carpeta, por ejemplo gestion-estudiantes, y adentro creamos la carpeta server.

Vamos a VsCode y hacemos click en Archivo - Abrir Carpeta, seleccionamos la carpeta de gestion-estudiantes y dentro de la carpeta server, creamos dos archivos:

- app.py
- requirements.txt

En caso de que VSCode nos pregunte que interprete utilizar para Python, seleccionamos la versión instalada

![python-13](images/python-13.png)

VsCode nos va a sugerir que utilicemos pylint para revisar nuestro código, hacemos click en Instalar

![python-14](images/python-14.png)

En Windows hacemos click en el menú de VsCode: Terminal - Nuevo Termina y ejecutamos los siguientes comandos:

```bash
py -3 -m venv .venv
.venv\scripts\activate
```

![python-15](images/python-15.png)

Si se genera el mensaje "Activate.ps1 is not digitally signed. You cannot run this script on the current system.", entonces debe ejecutar 

```bash
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
.venv\scripts\activate
```

![python-16](images/python-16.png)


Si está trabajando en MacOs o Linux, ejecute los siguientes comandos

```bash
python3 -m venv .venv
source .venv/bin/activate
```

![python-15](images/python-15.png)

Con esto, ya estamos trabajando en el entorno virtual de python

Para desactivar el entorno virtual, utilice deactivate

```bash
deactivate
```


### Instalación y Ejecución de Flask

Flask es un micro-framework que nos permite construir aplicaciones de servidor de forma rápida y eficiente. Ser un micro-framework no es indicativo de que es para aplicaciones pequeñas, por el contrario, significa que añade pocos elementos, permitiendo estar más cercano al lenguaje base, mejorando el rendimiento de la aplicación.

Para organizar nuestro proyecto, vamos a utilizar un archivo requirements.txt para gestionar las librerías. En el archivo requirements.tx incluya la librería de Flask

```python
Flask==1.1.2
```

Paquete           # Última versión

Paquete==1.0.4     # Versión específica

Paquete>=1.0.4     # Mínima versión a instalar

Paquete>=1.0,<=2.0 # Instalar última versión mayor a 1 y menor que 2

Dado una Versión MAJOR.MINOR.PATCH ,se hace incremento en cada uno cuando:

- MAJOR cuando se hacen cambios que generan incompatbilidad con la versión anterior
- MINOR cuando se agregan funcionalidades que son retro-compatibles
- PATCH cuando se corrigen errores que son retro-compatibles

Para instalar la librería, en la terminal ejecutamos el siguiente comando:

En Windows:

```bash
pip install -r requirements.txt
```

En MacOS/Linux:

```bash
pip3 install -r requirements.txt
```

En el archivo app.py importe Flask y cree una instancia de un objeto de Flask. Vamos a ejecutar el modo debug para que se recargue automáticamente y nos muestre más detalle de errores

```python
from flask import Flask
app = Flask(__name__)


if __name__ == '__main__':
    app.run(debug=True)
```

Con esto, ya tiene corriendo un servidor web en Python
