# Practica 3-2. Instalacion de Node.js Express y test de la primera aplicación.

Para empezar con esta práctica, debemos de parar nuestro servicio de Tomcat ya que nos podría ocasionar problemas. Para ello:

```sudo systemctl stop tomcat10```


![img1](./screenshots/1.png)


Una vez realizado, procedemos a instalar mediante el siguiente comando.

```sudo apt -y install nodejs npm```

![img2](./screenshots/2.png)

Cuando lo tengamos instalado, deberemos de instalar tambien Express. Para ello haremos uso del siguiente comando:

```sudo npm install -g express```

![img3](./screenshots/3.png)

Ahora, una vez que hayamos terminado de instalar todo lo necesario, procedemos con el despliegue de nuestra apliación.
Despliegue de aplicación de manera local.

Empezaremos clonando nuestro repositorio, del cual haremos el despliegue. ```git clone https://github.com/MehedilslamRipon/Shopping-Cart-Application```

![img4](./screenshots/4.png)

Y accederemos a la carpeta.

```cd Shopping-Cart-Application```


Una vez dentro, debemos instalar las librerías necesarias para que nuestra aplicación funcione correctamente.

```npm install```
![img5](./screenshots/5.png)

![img6](./screenshots/6.png)

Y haremos uso del siguiente comando para que no nos dé el error sh: 1: nodemon: not found.

```npm install nodemon --save--dev```

Y desplegamos nuestra aplicación.

![img7](./screenshots/7.png)

Y hacemos la comprobación de que accede correctamente.

![img8](./screenshots/8.png)

# Práctica 3.4: Despliegue de una aplicación una aplicación React en Netlify (PaaS)

Creación de nuestra aplicación

Lo primero es crear los siguientes archivos en un mismo directorio para crear la aplicación:

![img9](./screenshots/9.png)
![img10](./screenshots/10.png)
![img11](./screenshots/11.png)

Ahora se crea el package.json con npm init.

![img12](./screenshots/12.png)

![img13](./screenshots/13.png)


Y se comprueba qque funciona ejecutando node aplicacion.js y comprobándolo con la ip de la máquina y el puerto que por defecto es el 8080.

![img14](./screenshots/14.png)

## Aplicación para Netlify

Se clona el repositorio con el siguiente comando: ```git clone https://github.com/StackAbuse/color-shades-generator```

![img15](./screenshots/15.png)

Lo primero es registrarse en NETLIFY con el correo y sin usar el Github.

![img16](./screenshots/16.png)

Luego se crea un token de acceso y se copia dicho token.

![img17](./screenshots/17.png)

![img18](./screenshots/18.png)

![img19](./screenshots/19.png)



## Despliegue mediante CLI

Se instala el CLI de NETLIFY.

![img20](./screenshots/20.png)

Se guarda el token de antes para acceder, mediante una variable.

![img21](./screenshots/21.png)

Se hace el login con el comando siguiente:

![img22](./screenshots/22.png)

Dentro del proyecto se instala las librerías.

![img23](./screenshots/23.png)

Se ejecuta el proyecto.

![img24](./screenshots/24.png)

Se hace un pre despliegue ahora con netlify deploy.

![img25](./screenshots/25.png)

Y finalmente se despliega con netlify deploy --prod.

![img27](./screenshots/27.png)

Se comprueba el despliegue.

![img26](./screenshots/26.png)

![img28](./screenshots/28.png)

### Despliegue mediante conexión con Github

Lo primero es eliminar la página creada en netlify y el repositorio que se habia clonado.

![img29](./screenshots/29.png)

![img30](./screenshots/30.png)

Se descarga las fuentes en formato .zip.

![img31](./screenshots/31.png)

![img32](./screenshots/32.png)

![img33](./screenshots/33.png)


Se crea un nuevo repositorio.

![img34](./screenshots/34.png)

Se añade el contenido de la carpeta al repositorio.

![img35](./screenshots/35.png)

![img35](./screenshots/36.png)

Ahora se procede a conectar el repositorio con NETLIFY, se autoriza todo y luego se selecciona el repositorio creado antes.

![img37](./screenshots/37.png)

![img38](./screenshots/38.png)

Seleccionamos el repositorio que nos interesa y se comprueba que el nombre está disponible.

![img39](./screenshots/39.png)

Se introducen los siguientes comandos en los campos de datos y se le da a deploy.

![img40](./screenshots/40.png)

![img41](./screenshots/41.png)

![img42](./screenshots/42.png)

Ahora se accede a la carpeta public y se modifica el archivo robot.txt, se pone el nombre en disallow, se sube al repositorio con un commit y ya estaría hecho.

![img43](./screenshots/43.png)
