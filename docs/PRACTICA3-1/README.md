# PRÁCTICA 3.1: Instalación de Tomcat
## Instalación de Tomcat
1. Instalación de Java
En el caso de que no lo tengamos instalado Java, instalaremos el jdk
```sudo apt install default-jre```
![img1](./screenshots/1.png)
Podemos comprobar la versión instalada con el siguiente comando: 
```java -version```
![img2](./screenshots/2.png)
2. Tomcat
Instalaremos la versión 10 de Tomcat
```sudo apt install tomcat10 tomcat10-admin```

![img3](./screenshots/3.png)
Posteriormente tendremos que crear el usuario para Tomcat. Y para ello, lo que debemos modificar es el archivo ```tomcat-users.xml``` 
y quedará de la siguiente forma: 
![img4](./screenshots/4.png)
Cuando ya hayamos configurado el archivo procederemos a reiniciar el servicio Tomcat con el siguiente comando: ```sudo systemctl restart tomcat```. Y comprobaremos que el servicio se ha iniciado correctamente usando ```sudo systemctl status tomcat```. Deberá aparecernos algo como lo siguiente:

![img5](./screenshots/5.png)

## Despliegue manual mediante la GUI de administración

Accederemos a la dirección ```http://localhost:8080/nombre_usuario/html y nos aparecerá algo así:

![img6](./screenshots/6.png)

![img7](./screenshots/7.png)

Cuando hayamos hecho la comprobación de que Tomcat se ha instalado correctamente, procederemos a intentar desplegar un archivo ```.war``` en Tomcat. Hay que aclarar que el archivo correspondiente al ```.war``` que se nos facilitó tiene errores y realizaremos la prueba con otro archivo ```.war``` de ejemplo.

Desde este enlace lo descargaremos: ```https://tomcat.apache.org/tomcat-6.0-doc/appdev/sample/```

Lo seleccionamos y lo desplegamos:

![img8](./screenshots/8.png)
![img9](./screenshots/9.png)

Y accedemos para ver que está correctamente desplegado:

![img10](./screenshots/10.png)

## Despliegue con Maven

### Instalación de Maven

Para el despliegue con Maven, tendremos que instalar Maven al igual que hicimos arriba con Tomcat:

![img11](./screenshots/11.png)

Podemos consultar la versión instalada con el comando: ```nvm --v```

### Configuración de Maven
Ahora lo que tenemos que hacer es añadir un nuevo usuario al archivo ```tomcat-users.xml``` para poder desplegar con Maven, y el archivo quedará ahora de la siguiente forma:

![img12](./screenshots/12.png)

Una vez que tengamos hecho eso, tendremos que configurar Maven de la siguiente manera: Tenemos que modificar el archivo ```settings.xml```. Quedará de tal forma:

![img13](./screenshots/13.png)

Ahora clonaremos el repositorio de ejemplo que se nos ha facilitado y lo desplegaremos con Maven:

![img14](./screenshots/14.png)

Cambiamos de rama para trabajar mejor: 
![img15](./screenshots/15.png)

Ahora tenemos que editar el archivo ```pom.xml``` para añadirle la configuración. 
![img16](./screenshots/16.png)

Tendrá que quedar así:

![img17](./screenshots/17.png)

### Despliegue
Usaremos el comando ````mvn tomcat7:deploy``` para desplegarlo:

![img18](./screenshots/18.png)

Y al acceder a la dirección ```http://localhost:8080/nombre_usuario/``` nos debe aparecer algo como lo siguiente:

![img20](./screenshots/20.jpg)

Y si se accede al archivo nos debe aparecer lo siguiente:

![img19](./screenshots/19.jpg)

## CUESTIONES

**Habéis visto que los archivos de configuración que hemos tocado contienen contraseñas en texto plano, por lo que cualquiera con acceso a ellos obtendría las credenciales de nuestras herramientas. En principio esto representa un gran riesgo de seguridad, ¿sabrías razonar o averigüar por qué esto está diseñado de esta forma?**

Guardar contraseñas en texto plano dentro de archivos de configuración no es seguro, aunque a menudo se recurre a ello por motivos prácticos. Esto puede simplificar el acceso durante el desarrollo, garantizar compatibilidad con herramientas obsoletas o incluso mejorar el rendimiento en sistemas cerrados con bajos requerimientos de seguridad. Sin embargo, en entornos de producción es fundamental optar por alternativas más seguras, como el uso de cifrado o gestores de secretos, para proteger las credenciales adecuadamente.