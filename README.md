# Proyecto de Chat

Este proyecto proporciona una aplicación web que permite a los usuarios registrarse, iniciar sesión y chatear con sus amigos. Está construido con un frontend utilizando HTML, CSS y JavaScript. Como servidor web utilizamos Apache. El backend se realizo en el lenguaje Java y utilizando como servidor de aplicación Tomcat. Se utiliza MySQL como servicio de base de datos.

## Requisitos

- Java SDK (preferiblemente JDK 8 o superior)
- Servidor Apache Tomcat
- MySQL

## Instalación

1. Clona este repositorio en tu máquina local.
2. Importa el proyecto en tu IDE (Eclipse, VSCode).
3. Asegúrate de tener MySQL ejecutándose y crea una base de datos para este proyecto.
4. Configura el servidor Tomcat en tu IDE y despliega el proyecto.

## Uso

La aplicación tiene varios servicios de backend:

### Registro

Para registrar un nuevo usuario en la base de datos. Debe enviar un mensaje POST HTTP con los parámetros:

- user: nombre de usuario
- pass: contraseña del usuario
- mail: email del usuario
- codeCountry: código del país de origen.


### Lista de países

Este servicio devuelve una lista de países en formato JSON. Para usarlo, debe enviar un mensaje GET HTTP sin parámetros.


### Login

Este servicio verifica si un usuario está registrado en la base de datos y devuelve un código de sesión para identificar sus conexiones con el backend. Debe enviar un mensaje GET HTTP con los parámetros:

- mail: el identificador único del usuario
- pass: contraseña ingresada por el usuario.


### Agregar un amigo

Este servicio permite al usuario agregar un amigo a su lista de amigos. Debe enviar un mensaje POST HTTP con los parámetros:

- mail: correo electrónico del usuario activo.
- session: código de sesión.
- friend: correo electrónico del usuario que se quiere agregar a la lista de amigos.


### Recibir lista de amigos

Este servicio permite al usuario recibir su lista de amigos. Debe enviar un mensaje GET HTTP con los parámetros:

- mail: correo electrónico del usuario activo.
- session: código de sesión.


### Recibir mensaje

Este servicio permite solicitar un mensaje pendiente de recibir. Debe enviar un mensaje GET HTTP con los parámetros:

- mail: correo electrónico del usuario activo.
- session: código de sesión.


### Enviar mensaje

Este servicio permite enviar un mensaje al backend. Debe enviar un mensaje POST HTTP con los parámetros:

- mail: correo electrónico del usuario activo.
- session: código de sesión.
- receptor: correo electrónico del destinatario del mensaje.
- sms: texto del mensaje.
