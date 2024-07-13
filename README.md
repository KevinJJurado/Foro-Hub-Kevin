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

![Menu litealura](https://github.com/KevinJJurado/desafioLiteraturaSpring/assets/128235203/c48d070e-aef3-4eea-b56c-35e17850e297)


# Video Demostrativo
![videoConversor](https://github.com/KevinJJurado/desafioLiteraturaSpring/assets/128235203/abc41534-8a09-460a-99f3-1b860b681778)



# Créditos
Este proyecto fue desarrollado por [Kevin Jurado](https://github.com/KevinJJurado).
