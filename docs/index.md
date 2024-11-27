# Práctica 3.5: Despliegue de una aplicación Flask (Python)

## Prerrequisitos

Para comenzar con la práctica, es necesario tener instalado en el sistema los siguientes paquetes:
- Nginx
- Gunicorn
- Pipenv

## Despliegue de la aplicación de prueba

Empezamos instalando pipenv:

![1](includes/images/1.png)

Ahora debemos de cambiar los propietarios de la carpeta de la aplicación:

![2](includes/images/4.png)

Así como los permisos:

![3](includes/images/5.png)

Creamos el archivo .env dentro de la carpeta de la aplicación y añadimos las variables de entorno necesarias:

![4](includes/images/6.png)

Contenido del archivo .env:

![5](includes/images/7.png)

Inicializamos el entorno virtual de la aplicación:

![6](includes/images/8.png)

Ahora instalamos las dependencias de la aplicación:

![7](includes/images/9.png)

Creamos los archivos app.py y wsgi.py:

![8](includes/images/10.png)

Contenido del archivo wsgi.py:

![9](includes/images/11.png)

Probamos la aplicación:

![10](includes/images/14.png)

Vemos que funciona:

![11](includes/images/16.png)

Ahora comprobamos que gunicorn funciona correctamente:

![11](includes/images/17.png)

Veremos cual es el path de gunicorn dado que lo necesitaremos para configurar systemd.
Acto seguido saldremos del entorno virtual e iniciaremos nginx:

![12](includes/images/18.png)

Iniciamos nginx:

![13](includes/images/20.png)

Ahora creamos el archivo de configuración para que systemd ejecute gunicorn:

![14](includes/images/21.png)

Comprobamos que el servicio se ha creado correctamente:

![15](includes/images/22.png)

Ahora configuramos nginx:

![16](includes/images/23.png)

Activamos el servidor nginx con el enlace simbólico:

![17](includes/images/24.png)

Comprobamos que el servicio de nginx se ha creado correctamente:

![18](includes/images/26.png)

Cambiamos el archivo /etc/host para que la dirección IP de la máquina física apunte a la dirección IP de la máquina virtual:

![19](includes/images/27.png)

Y vemos que la aplicación funciona correctamente:

![20](includes/images/28.png)

## Despliegue de la aplicación

Ahora debemos repetir todos los pasos anteriores pero con la aplicación 