# Práctica 3.5: Despliegue de una aplicación Flask (Python)

## Índice
1. [Prerrequisitos](#prerrequisitos)
2. [Procedimiento Completo Para el Despliegue](#procedimiento-completo-para-el-despliegue)
3. [Cuestión](#cuestión)

## Prerrequisitos

Para esta práctica se deben tener las siguientes herramientas instaladas en el sistema: 
```- Nginx - Gunicorn - Pipenv```

## Procedimiento Completo Para el Despliegue

Como primer paso, se ha de instalar el gestor de paquetes de Python pip: ```Python3-pip```

![img1](./screenshots/1.png)


Una vez instalado pip, se ha de instalar pipenv:

![img2](./screenshots/2.png)


Se crea un directorio para la aplicación. Al crearla se apreciará que los permisos pertenecen a root. Para cambiarlos se ha de ejecutar el comando siguiente:

![img3](./screenshots/3.png)


Para ser cambiados se ejecutará el siguiente comando: 

![img4](./screenshots/4.png)

Y se le cambiarán los permisos para que al iniciar Nginx no haya problemas: 

![img5](./screenshots/5.png)

Ahora, dentro del directorio creado con anterioridad se creará el archivo oculto .env

![img6](./screenshots/6.png)

En el archivo .env se añadirán las siguientes lineas: 

![img7](./screenshots/7.png)

Se iniciará el entorno virtual y Pipenv cargará las dependencias del archivo .env:

![img8](./screenshots/8.png)


Como se aprecia en la utima línea de la captura, aparece el nombre de nuestro entorno virtual, lo cual significa que se ha iniciado correctamente.

Hecho esto, se instalarán las dependencias para la aplicación: 

![img9](./screenshots/9.png)

Se crearán los archivos app.py y wsgi.py que contendrán los siguientes codigos:

![img10](./screenshots/10.png)

![img11](./screenshots/11.png)

Se probará la aplicación con el comando siguiente: 

![img12](./screenshots/12.png)

Si todo ha ido bien, si se accede al enlace proporcionado se podrá ver la aplicación funcionando: 

![img13](./screenshots/13.png)

Se comprobará ahora que Gunicorn funciona correctamente: 

![img14](./screenshots/14.png)

Se tomará nota del path desde donde se ejectuta Gunicorn, para ello se ejecutará el siiguinte comandodentro de nuestro entorno virtual: 


![img15](./screenshots/15.png)

Se saldrá del entorno virtual con ```deactivate```

Se iniciará Nginx si no estaba iniciado de antemano y se comprobará que sigue funcionando perfectamente:

![img16](./screenshots/16.png)

Se creará un archivo de configuración para que systemd ejecute Gunicorn como otro servicio mas: 

Ahora se habilitará el servicio y se comprobará que se ha iniciado correctamente: 

![img17](./screenshots/17.png)

Ahora se modifiará el archivo de configuración de Nginx de la siguiente manera: Nginx

![img18](./screenshots/18.png)

Se creará el enlace simbólico para que Nginx pueda acceder a los archivos de la aplicación: 

![img19](./screenshots/19.png)

Se comptobará que la configuración de Nginx es correcta:

![img20](./screenshots/20.png)

Se editará el archivo hosts para que se pueda acceder a la aplicación desde el navegador:

![img21](./screenshots/21.png)


Se comprobará que la aplicación funciona correctamente en el navegador: 

![img22](./screenshots/22.png)

Ahora se deberá repetir el proceso para un repositorio que se clonará de GitHub:

![img23](./screenshots/23.png)

Se creará el archivo .env con las variables de entorno necesarias: 

![img24](./screenshots/24.png)

Se cambiarán los permisos del directorio y los propietarios: 

![img25](./screenshots/25.png)

Se iniciliazará el entorno virtual: 

![img26](./screenshots/26.png)

Y se probará la aplicación: 

![img27](./screenshots/27.png)

Se comprobará que funciona correctamente, que como hicimos antes, el Gunicorn funciona adecuadamente.

![img28](./screenshots/28.png)

## Cuestion
Un servidor WSGI (Web Server Gateway Interface) actúa como intermediario entre aplicaciones web escritas en Python y servidores web como Apache o Nginx, traduciendo solicitudes HTTP en datos procesables por Python y devolviendo respuestas al cliente. Permite compatibilidad entre frameworks, facilita el despliegue en producción y mejora el manejo de múltiples solicitudes concurrentes de manera eficiente



