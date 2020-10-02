# Arem-Taller6

Este taller fue hecho para comprender la implementacion de aplicaciones seguras y la comunicacion entre ellas haciendo el uso del protocolo https del puerto 443 y validando los permisos de acceso a los servcios por medio certificados ,en este caso se tiene un server fachada que tiene la funcionalidad de login para auntenticar los usuarios y otro servicio de fachada para recibir los datos para enviar una peticion por https al otro servidor que es una calculadora trogonometrica que se encraga de recirbir los datos , realizar los calculos y devolver la respuesta en un json si y solo si el servidor fachada esta autorizado

# Pre-Requisitos

Para el uso de la aplicacion se requiere que el computador tenga instalados los siguientes prerequisitos:

   * Java 8
   * Maven
   * Git
   * Docker

# Despliegues

# Instalacion

Para comenzar la instalacion porfavor copie el siguiente comando en su linea de comandos :

~~~
git clone https://github.com/fernando-b15/Arem-Taller6
~~~

![image1](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/clone.PNG)

Posteriormente desde linea comandos ingrese al directorio de la aplicacion con el siguinete comando :

~~~
cd Arem-Taller6
~~~
Ahora proceda primero a entrar al directorio que contiene el servicio SeverFachada:

~~~
cd SeverFachada
~~~

Despues se realiza la compilacion y empaquetacion del  SeverFachada con el siguinte comando:

~~~
mvn package
~~~

![image2](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/packagefachada.PNG)

Pero adicionalmente vuelva al directorio principal de la aplicacion e ingrese al directorio que contiene el servicio CalculadoraTrigonometrica:

~~~
cd CalculadoraTrigonometrica
~~~

Despues se realiza la compilacion y empaquetacion del  servicio CalculadoraTrigonometrica con el siguinte comando:

~~~
mvn package
~~~

![image3](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/packagecalculadora.PNG)

# Ejecucion

Para la ejecucion de toda la arquitectura de servcios dockers se hace desde el directorio principal de la aplicacion, construimos la arquitectura de servicios que incluye los 2 dockers haciendo uso del docker-compose.yml con el siguiente comando:

~~~
docker-compose up -d 
~~~

![image4](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/docker0.PNG)

![image5](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/docker1.PNG)

Asi podemos ver que se desplegaron localmente los 2 dockers ,los cuales 1 corresponde al ServerFachada y el otro a la CalculadoraTrigonometrica

![image6](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/docker2.PNG)


Ahora ya podemos ver que podemos hacer uso de los servicios del log localmente desde nuestro en localhost en el buscador como se vera a continuacion:   

![image7](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/test1.PNG)


# Imagenes de Servicios en Doker Hub

La imagen del server fachada se encuentra en el siguiente link es:
   * [ImageServerFachada](https://hub.docker.com/repository/docker/fernando15/serverfachada)
    
La imagen de la calculadora trigonometrica se encuentra en el siguiente link es:
   * [ImageCalculadoraTrigonometrica](https://hub.docker.com/repository/docker/fernando15/calculadoratrigonometrica)
   
# Pruebas

Para realizar la prueba de lo servicios de nuestros dockers usaremos primero entraremos por https al ServerFachada que esta en el puerto 9001 y este procedera a enviarnos a la vista de logueo:

![image7](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/test1.PNG)

Si nos autenticamos correctamente nos enviara a la vista /home de la fachada si no se mostrara elsiguiente mensaje:

![image8](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/test2.PNG)

Una vez no autentiquemos correctamente iremos a la vista fachada del server en https que recogera la funcion y el valor digitado pro el usuario y le enviara la peticion al servicio ClaculadoraTrigonometrica por https tambien:

![image9](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/test3.PNG)

Como el ServerFachada usa un UrlReader que lee los certificados de ClaculadoraTrigonometrica lo cual le da autorizaciona acceder al servivio y recibir una respuesta por https :

![image10](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/test4.PNG) 

# Documentacion

Para obtener la documentacion del servicios del ServerFachada y la CalculadoraTrigonometrica, ingrese el siguinete codigo en el respectivo directorio que contiene el ServerFachada  y tambien en el que contiene la CalculadoraTrigonometrica

~~~
mvn javadoc:javadoc
~~~

![image11](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/javadoc1.PNG)


para acceder a la documentacion del ServerFachada ingrese al siguiente enlace [apidocs](https://github.com/fernando-b15/Arem-Taller6/tree/master/SeverFachada/apidocs) 

![image12](https://github.com/fernando-b15/Arem-Taller6/blob/master/img/javadoc2.PNG)

para acceder a la documentacion de la CalculadoraTrigonometrica ingrese al siguiente enlace [apidocs](https://github.com/fernando-b15/Arem-Taller6/tree/master/CalculadoraTrigonometrica/apidocs) 

# Video de pruebas en EC2 AWS
   * [![video1](https://yt-embed.herokuapp.com/embed?v=8Xg4aOs5HoM)](https://www.youtube.com/watch?v=8Xg4aOs5HoM)
   
# Licencia

La aplicacion cuenta con la siguiente [MIT LICENCE](https://github.com/fernando-b15/Arem-Taller6/blob/master/LICENSE) 

# Autor

   * [Fernando Barrera Barrera](https://github.com/fernando-b15) :guitar:   
