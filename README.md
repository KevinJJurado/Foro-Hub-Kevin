![titulo](https://github.com/user-attachments/assets/be072df3-e3c5-4ecc-aa35-f83cc8e9a08f)
# DESAFIO FORO HUB
# Menú 
- [Descripción](#descripción)
- [Funcionalidades](#funcionalidades)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Ejecución de la Aplicación](#ejecución-de-la-aplicación)
- [Uso](#uso)
- [Capturas de Pantalla](#capturas-de-pantalla)
- [Video Demostrativo](#video-demostrativo)
- [Créditos](#créditos)

# Descripción

Este proyecto tiene como objetivo desarrollar una aplicación de foro utilizando Spring Boot y JWT (JSON Web Token) para la autenticación. La aplicación permite a los usuarios crear, listar, actualizar, borrar y obtener tópicos por ID, además de proporcionar funcionalidad de inicio de sesión.

# Funcionalidades

- **Crear Tópicos**: Los usuarios pueden crear nuevos tópicos en el foro proporcionando un título y contenido.
- **Listar Tópicos**: La aplicación permite a los usuarios obtener un listado de todos los tópicos creados.
- **Obtener Tópico por ID**: Los usuarios pueden obtener detalles de un tópico específico proporcionando su ID.
- **Actualizar Tópico**: Los usuarios pueden actualizar un tópico existente proporcionando su ID y la nueva información.
- **Borrar Tópico**: Los usuarios pueden eliminar un tópico proporcionando su ID.
- **Inicio de Sesión**: Los usuarios pueden autenticarse proporcionando sus credenciales y obteniendo un token JWT para acceder a las funcionalidades protegidas.

# Tecnologías Utilizadas

- **Spring Boot**: Framework para el desarrollo de aplicaciones Java con funcionalidades integradas como inyección de dependencias, configuración automática y acceso a datos.
- **JWT (JSON Web Token)**: Utilizado para la autenticación y autorización de usuarios.
- **MySQL**: Base de datos relacional para almacenar la información de los tópicos y usuarios.
- **Spring Security**: Framework para la gestión de la seguridad en aplicaciones Spring, utilizado junto con JWT para proteger las rutas.
- **Hibernate**: Framework ORM para interactuar con la base de datos PostgreSQL.

# Ejecución de la Aplicación

Para ejecutar la aplicación, sigue estos pasos:

1. Clonar el Repositorio: Clona el repositorio de GitHub en tu máquina local.
   
   ```bash
   git clone https://github.com/tu_usuario/foro-spring-jwt.git
   cd foro-spring-jwt

2. Configurar la Base de Datos: Configura una base de datos MySQL en tu entorno local y actualiza la configuración de la base de datos en el archivo
  - application.properties.
      ```bash
      spring.datasource.url=jdbc:postgresql://localhost:5432/tu_base_de_datos
      spring.datasource.username=tu_usuario
      spring.datasource.password=tu_contraseña
      spring.jpa.hibernate.ddl-auto=update
      spring.jpa.show-sql=true
      spring.jpa.properties.hibernate.format_sql=true
      server.error.include-stacktrace=never
      api.security.secret=${JWT_SECRET:tu_contraseña_de_usuario}
  - aplication.yml
   
     ```bash
     spring:
      profile.active: dev, test, prop
      datasource:
        url: jdbc:mysql://localhost/foro_hub_bd
        username: tu_usuario
        password: tu_contraseña
      jpa:
        show-sql: true
        properties:
          hibernate:
            format_sql: true
      server:
        error:
          include-stacktrace: never
      api:
        security:
          secret: ${JWT_SECRET:tu_contraseña_de_usuario}

5. Ejecutar la Aplicación: Ejecuta la aplicación utilizando Maven o tu IDE favorito.
   ```bash
   mvn spring-boot:run

6. Acceso a la Aplicación: Una vez que la aplicación esté en funcionamiento, podrás acceder a las diferentes funcionalidades del foro a través de las rutas proporcionadas.

# Uso
## Endpoints.

### Tópicos

- **Registrarse**:
  ```http
  POST http://localhost:8080/login

Cuerpo de la solicitud

    {
      "username": "nombre_usuario",
      "password": "contraseña"
    }

Respuesta

    {
      "token": "token_jwt"
    }

Cuerpo de la Solicitud

      {
      "titulo": "Nuevo título del tópico",
      "mensaje": "Nuevo contenido del tópico",
      "autor": "Tu nombre",
      "curso": "Tu curso"
      }
- **Crear, Actualizar, Listar Topicos**:
  ```http
  POST http://localhost:8080/topicos
- **Obtener, Eliminar Topico**:
  ```http
  POST http://localhost:8080/topcios/{id}



# Capturas de Pantalla

![User login](https://github.com/user-attachments/assets/418c3606-e9eb-4ce4-a136-fd9eb8051adb)

![Create](https://github.com/user-attachments/assets/abcae2c5-673b-4ba0-a0d8-75ceaabbd1cf)

![Get all](https://github.com/user-attachments/assets/4fb352d8-9b0d-4a78-a637-b0b867c508cd)

![GetOne](https://github.com/user-attachments/assets/9ee06b6a-e02d-47c6-9670-63ae0b1cd041)

![Update](https://github.com/user-attachments/assets/81611037-3849-4506-ad7c-d75514732e4b)

![Delete](https://github.com/user-attachments/assets/cd38f53f-1d49-4870-a5e6-5ab7ba7e2831)




# Video Demostrativo
![Video-funcionamiento](https://github.com/user-attachments/assets/912501b2-3c29-4c53-93a5-4de1ae9b2781)



# Créditos
Este proyecto fue desarrollado por [Kevin Jurado](https://github.com/KevinJJurado).
