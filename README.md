# Pasos para iniciar un proyecto con Python

## 1 - Creamos la carpeta que tendra el proyecto

```
> mkdir folderName
```

## 2 - Crear entorno locar de desarrollo

```
> cd folderName
> python3 -m venv .
> source bin/activate <-- Activamos
```
* El punto es para que instale en el mismo directorio.

## 3 - Instalamos Django

```
> pip3 install django 
> pip3 freeze <-- Comprueba la instalación
```

## 4 - Creamos el Proyecto

```
> django-admin startproject setup
> cd setup
```
### Explicacion

<ul>
<li><p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">El directorio externo setup/root es un contenedor para su proyecto. </font><font style="vertical-align: inherit;">Su nombre no le importa a Django; </font><font style="vertical-align: inherit;">puedes cambiarle el nombre a lo que quieras.</font></font></p></li>
<li><p><code class=" notranslate">manage.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: una utilidad de línea de comandos que le permite interactuar con este proyecto de Django de varias maneras. </font><font style="vertical-align: inherit;">Puedes leer todos los detalles sobre </font></font><code class=" notranslate">manage.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">en </font></font><code class=" notranslate">django-admin</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">y </font></font><code class=" notranslate">manage.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></p></li>
<li><p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">El directorio interno </font></font><code class=" notranslate">setup/</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">es el paquete de Python real para su proyecto. </font><font style="vertical-align: inherit;">Su nombre es el nombre del paquete de Python que deberá usar para importar cualquier cosa dentro de él (por ejemplo, setup.urls).</font></font></p></li>
<li><p><code class=" notranslate">setup/__init__.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: un archivo vacío que le dice a Python que este directorio debe considerarse un paquete de Python. </font><font style="vertical-align: inherit;">Si es un principiante de Python, lea más sobre los paquetes en los documentos oficiales de Python.</font></font></p></li>
<li><p><code class=" notranslate">setup/settings.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: Ajustes/configuración para este proyecto Django. </font><font style="vertical-align: inherit;">La configuración de Django le dirá todo sobre cómo funcionan las configuraciones.</font></font></p></li>
<li><p><code class=" notranslate">setup/urls.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: Las declaraciones de URL para este proyecto Django; </font><font style="vertical-align: inherit;">una "tabla de contenido" de su sitio impulsado por Django. </font><font style="vertical-align: inherit;">Puede leer más sobre las URL en el despachador de URL.</font></font></p></li>
<li><p><code class=" notranslate">setup/asgi.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: Un punto de entrada para servidores web compatibles con ASGI para servir a su proyecto. </font><font style="vertical-align: inherit;">Consulte Cómo implementar con ASGI para obtener más detalles.</font></font></p></li>
<li><p><code class=" notranslate">setup/wsgi.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: Un punto de entrada para servidores web compatibles con WSGI para servir a su proyecto. </font><font style="vertical-align: inherit;">Consulte Cómo implementar con WSGI para obtener más detalles.</font></font></p></li>
</ul>

## Corremos migración

```
> python3 manage.py migrate
```

## Probamos Servidor Local

```
> python3 manage.py runserver
```

## Creamos el app

* Detenemos el app

```
> python3 manage.py startapp app
```

<p><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Explicación de la estructura de la aplicación</font></font></strong></p>

<p><code class=" notranslate">admin.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: registre sus modelos aquí para que se agreguen y personalicen en el panel de administración de Django</font></font></p>

<p><code class=" notranslate">apps.py:</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Contiene el código de configuración de la aplicación.</font></font></p>

<p><code class=" notranslate">models.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: Defina sus modelos aquí. </font><font style="vertical-align: inherit;">Estas son las tablas utilizadas para almacenar datos y definir sus relaciones.</font></font></p>

<p><code class=" notranslate">tests.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: Pruebas de escritura para la aplicación</font></font></p>

<p><code class=" notranslate">views.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: Definición de los datos que se representarán en las plantillas</font></font></p>

## Registramos el app en setup/settings.py

```python
# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # My Apps
    'app',
]
```
## Cremos la carpeta templates

```
> app/templates
```
## Creamos el controlador / views

```python
def HelloWorld(request):
    return render(request, 'index.html')
```

## Agregamos las RUTAS

Siempre en ```setup/urls.py```

