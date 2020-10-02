# Arem-Taller6

Este taller fue hecho para comprender la implementacion de aplicaciones seguras y la comunicacion entre ellas haciendo el uso del protocolo https del puerto 443 y validando los permisos de acceso a los servcios por medio certificados ,en este caso se tiene un server fachada que tiene la funcionalidad de login para auntenticar los usuarios y otro servicio de fachada para recibir los datos para enviar una peticion por https al otro servidor que es una calculadora trogonometrica que se encraga de recirbir los datos , realizar los calculos y devolver la respuesta en un json si y solo si el servidor fachada esta autorizado

# Pre-Requisitos

Para el uso de la aplicacion se requiere que el computador tenga instalados los siguientes prerequisitos:

   * Java 8
   * Maven
   * Git
   * Docker

# Despliegues

# Imagenes de Servicios en Doker Hub

La imagen del server fachada se encuentra en el siguiente link es:
   * [ImageServerFachada](https://hub.docker.com/repository/docker/fernando15/serverfachada)
    
La imagen de la calculadora trigonometrica se encuentra en el siguiente link es:
   * [ImageCalculadoraTrigonometrica](https://hub.docker.com/repository/docker/fernando15/calculadoratrigonometrica)

# Video de pruebas
   * [![video1](https://yt-embed.herokuapp.com/embed?v=8Xg4aOs5HoM)](https://www.youtube.com/watch?v=8Xg4aOs5HoM)
   
# Licencia

La aplicacion cuenta con la siguiente [MIT LICENCE](https://github.com/fernando-b15/Arem-Taller6/blob/master/LICENSE) 

# Autor

   * [Fernanado Barrera Barrera](https://github.com/fernando-b15) :guitar:   
