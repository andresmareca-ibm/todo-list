# Prueba Técnica: TODO List
Se trata de elaborar un TODO List individual por usuario, es decir, cada usuario tiene su propia TODO List. 
Para ello, hay que desarrollar una aplicación completa que incluya backend, frontend y modelo de datos para 
una base de datos relacional.

## Requisitos del Proyecto

### Backend
* Utilizar el framework [NestJS](https://nestjs.com/) para desarrollar el servidor.
* Utilizar el framework [Sequelize](https://sequelize.org/) para la comunicación desde el código con la base de datos.
* Implementar una API RESTful con las siguientes funcionalidades:
	* CRUD (Crear, Leer, Actualizar, Eliminar) para una entidad principal (por ejemplo, productos, usuarios, etc.).
	* Login (Ya viene implementado)
    * Validación de datos y manejo adecuado de errores.

### Frontend
* Utilizar React para desarrollar la interfaz de usuario.
* Utilizar [Carbon](https://react.carbondesignsystem.com/) para sistema de diseño.
* Crear una SPA (Single Page Application) que consuma la API desarrollada en el backend.
* Implementar las siguientes vistas/páginas:
	* Página de inicio con un listado de la entidad principal.
	* Formulario para crear y editar la entidad principal.
    * Página de login y registro de usuarios.

### Base de Datos
* Diseñar un modelo de datos relacional utilizando un SGBD relacional de tu elección).
* Incluir la creación de tablas necesarias y sus relaciones.
* Asegurar la integridad y consistencia de los datos mediante claves primarias, foráneas y restricciones necesarias.

## Criterios de Evaluación
* Correcta implementación de la funcionalidad requerida en el backend y frontend.
* Calidad y claridad del código, incluyendo comentarios y organización del mismo.
* Uso adecuado de las tecnologías especificadas (NestJS, React, DB).
* Diseño y normalización del modelo de datos.
* Experiencia de usuario y diseño responsivo del frontend.
* Seguridad y manejo de errores en la aplicación.

## Anexos

### Login
Para simplificar, el login se hará contra un sistema de autenticación ya existente y que viene configurado en el backend.
Para acceder a la documentación del mismo acceder a `http://localhost:4000/docs`. 
Solamente hay que implementar el flujo en el front:
1. Obtener la URL de redirección del login mediante un `GET /v1/login`
2. Redirigir al usuario a esa URL
3. Esperar la resupuesta del login capturando el parámetro `code`
4. Hacer un `POST /v1/login/generate` para obtener el token
5. Guardar el token en el localStorage para hacer el resto de las peticiones

### Arrancar el backend
1. `npm install`
2. ```shell
DB_NAME=
DB_HOSTNAME=
DB_SCHEMA=
DB_USER=
DB_PWD=
DB_PORT=
DB_CONNECTION_POOL_START=true
DB_CONNECTION_POOL=3
DB_SSL=

APPID_TENANT_ID=
APPID_CLIENT_ID=
APPID_SECRET=
APPID_SERVICE_URL=https://eu-de.appid.cloud.ibm.com
APPID_REDIRECT_URL=http://localhost:3000/login
```
3. `npm run start:dev`

### Arrancar el frontend
1. `npm i`
2. ```shell
REACT_APP_BACKEND_URL=http://localhost:4000
```
3. `npm run start`

