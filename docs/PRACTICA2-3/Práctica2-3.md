# Índice
1. [Nginx Servidor](#nginx-servidor)
2. [Nginx Proxy Inverso](#nginx-proxy-inverso)
3. [Comprobaciones](#comprobaciones)

# Nginx Servidor

![img1](/screenshots/1.png)
![img2](/screenshots/2.png)

Primero se debe cambiar el nombre de nuestra web a webserver, lo que implica que tenemos que cambiar el archivo de configuración y eliminar el enlace simbólico previo para crear uno nuevo con el nombre de archivo.

![img3](/screenshots/3.png)

Eliminamos enlace simbólico y creamos uno nuevo:

![img5](/screenshots/5.png)

![img6](/screenshots/6.png)

Cambiamos con sudo nano /etc/nginx/sites-available/webserver las directivas, añadiendo el puerto 8080 y toda configuración con el nuevo nombre.

![img4](/screenshots/4.png)

Después reiniciamos Nginx.

# Nginx Proxy Inverso

En el host de windows se cambia la IP por la de la nueva máquina que va a actuar de proxy y se le cambia el nombre.

![img8](/screenshots/8.png)

También debemos modificar el nuevo archivo en /etc/nginx/sites-available
, añadiendo la directiva pass_proxy con su nueva dirección y puerto 8080.

Después tendremos que modificar el hosts en la máquina con la ip del servidor:

![img7](/screenshots/7.png)

# Comprobaciones

Tras una serie de problemas, tuvimos que cambiarle el nombre a servidor 1, e intentamos entrar a la web desde la máquina.
Ahora hacemos la prueba al entrar a la web desde el proxy, y vemos que todo funciona correctamente: 

Podemos comprobar que en el acceso al log nos lo notifica correctamente.

![img11](/screenshots/11.png)

Y podemos comprobar en las herramientas de desarrollador, que nos notifica correctamente la petición con el código 200 Ok.

![img12](/screenshots/12.png)
