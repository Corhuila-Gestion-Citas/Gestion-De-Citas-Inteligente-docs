# Manual del Proyecto - Gestión de Citas Inteligente

## 1. Información general

**Nombre del proyecto:** Gestión de Citas Inteligente  
**Asignatura:** Sistemas Distribuidos  
**Institución:** CORHUILA  
**Tipo de sistema:** Aplicación web distribuida para gestión de citas y turnos  
**Estado:** Versión final para entrega académica  

---

## 2. Descripción del proyecto

Gestión de Citas Inteligente es una aplicación web diseñada para permitir que los usuarios puedan registrarse, iniciar sesión, solicitar turnos, consultar sus citas, cancelar o reprogramar turnos, recibir notificaciones y revisar el historial de acciones realizadas dentro del sistema.

El proyecto fue desarrollado bajo una arquitectura distribuida basada en microservicios, API Gateway, frontend Angular, bases de datos separadas, Docker, Liquibase, GitHub Actions y despliegue en la nube.

---

## 3. Objetivo del sistema

El objetivo del sistema es mejorar la gestión de citas mediante una plataforma centralizada, organizada y fácil de usar, que permita al usuario realizar sus procesos de forma digital y que al mismo tiempo permita evidenciar una arquitectura distribuida para la asignatura de Sistemas Distribuidos.

---

## 4. Funcionalidades principales

El sistema permite realizar las siguientes acciones:

- Registro de usuario.
- Inicio de sesión.
- Consulta de información del usuario.
- Solicitud de turnos.
- Consulta de turnos.
- Cancelación de turnos.
- Reprogramación de turnos.
- Consulta de notificaciones.
- Marcado de notificaciones como leídas.
- Consulta de historial o auditoría.
- Cierre de sesión.

---

## 5. Arquitectura del proyecto

El proyecto utiliza una arquitectura basada en microservicios con API Gateway.

```txt
Frontend Angular / Vercel
        |
        v
API Gateway / Render
        |
        |-- users-service ------------ PostgreSQL
        |-- turnos-service ----------- PostgreSQL
        |-- notifications-service ---- PostgreSQL
        |-- audit-service ------------ MongoDB
```

---

## 6. Componentes del sistema

### 6.1 Frontend

El frontend fue desarrollado en Angular y permite la interacción del usuario con el sistema.

Principales vistas:

- Login.
- Registro.
- Inicio.
- Mis turnos.
- Solicitar turno.
- Notificaciones.
- Historial.
- Perfil.

### 6.2 API Gateway

El API Gateway funciona como punto central de entrada para las peticiones del frontend. Su función es recibir las solicitudes y redirigirlas al microservicio correspondiente.

Ejemplos de rutas:

```txt
/users
/turnos
/notifications
/audit
```

### 6.3 users-service

Microservicio encargado de gestionar usuarios, registro e inicio de sesión.

Funciones principales:

- Registrar usuarios.
- Iniciar sesión.
- Consultar usuarios.
- Validar credenciales.

### 6.4 turnos-service

Microservicio encargado de gestionar los turnos o citas.

Funciones principales:

- Crear turnos.
- Consultar turnos.
- Cancelar turnos.
- Reprogramar turnos.
- Consultar turnos por usuario.

### 6.5 notifications-service

Microservicio encargado de gestionar las notificaciones del sistema.

Funciones principales:

- Crear notificaciones.
- Consultar notificaciones.
- Filtrar notificaciones.
- Marcar notificaciones como leídas.

### 6.6 audit-service

Microservicio encargado de registrar el historial de acciones realizadas en el sistema.

Funciones principales:

- Registrar acciones del usuario.
- Consultar historial.
- Guardar eventos de auditoría.

---

## 7. Tecnologías utilizadas

| Área | Tecnología |
|---|---|
| Frontend | Angular |
| Backend | Java 17, Spring Boot |
| Gateway | Spring Cloud Gateway |
| Base de datos relacional | PostgreSQL |
| Base de datos documental | MongoDB |
| Migraciones | Liquibase |
| Contenedores | Docker |
| Orquestación local | Docker Compose |
| Integración continua | GitHub Actions |
| Despliegue frontend | Vercel |
| Despliegue backend | Render |
| Control de versiones | Git y GitHub |

---

## 8. Repositorios del proyecto

Organización GitHub:

```txt
https://github.com/Corhuila-Gestion-Citas
```

Repositorios principales:

```txt
Repositorio principal:
https://github.com/Corhuila-Gestion-Citas/Gestion-De-Citas-Inteligente

Repositorio documentación:
https://github.com/Corhuila-Gestion-Citas/Gestion-De-Citas-Inteligente-docs

Repositorio portal:
https://github.com/Corhuila-Gestion-Citas/Gestion-De-Citas-Inteligente-portal

Repositorio app / infraestructura:
https://github.com/Corhuila-Gestion-Citas/Gestion-De-Citas-Inteligente-app

Repositorio API:
https://github.com/Corhuila-Gestion-Citas/Gestion-De-Citas-Inteligente-api

Repositorio base de datos:
https://github.com/Corhuila-Gestion-Citas/Gestion-De-Citas-Inteligente-db

Repositorio gateway:
https://github.com/Corhuila-Gestion-Citas/Gestion-De-Citas-Inteligente-gateway
```

---

## 9. Flujo de ramas

El proyecto maneja el siguiente flujo de trabajo:

```txt
develop -> qa -> main
```

### Descripción de ramas

| Rama | Uso |
|---|---|
| develop | Desarrollo inicial y pruebas internas |
| qa | Validación antes de pasar a versión final |
| main | Versión estable para entrega y despliegue |

---

## 11. Credenciales de prueba

Usar las siguientes credenciales para validar el sistema:

```txt
prueba@gmail.com pass:123
yeison@gmail.com pass:123
nicolas@gmail.com pass:123
sofia@gmail.com pass:123
catalina@gmail.com pass:123
Rol: CLIENTE
```

> Importante: antes de entregar, verificar que estas credenciales permitan iniciar sesión correctamente.

---

## 12. Manual de uso para el usuario

### 12.1 Iniciar sesión

1. Ingresar a la URL de la aplicación.
2. Escribir el correo registrado.
3. Escribir la contraseña.
4. Presionar el botón de iniciar sesión.
5. El sistema redirige al usuario a la pantalla principal.

### 12.2 Registrarse

1. Ingresar a la pantalla de registro.
2. Digitar nombre completo.
3. Digitar correo electrónico.
4. Digitar contraseña.
5. Presionar el botón de registro.
6. El sistema crea el usuario con rol CLIENTE.

### 12.3 Solicitar turno

1. Iniciar sesión.
2. Ir a la opción **Solicitar Turno**.
3. Seleccionar especialidad.
4. Seleccionar doctor.
5. Seleccionar fecha y hora.
6. Confirmar la solicitud.
7. El sistema registra el turno y genera la notificación correspondiente.

### 12.4 Consultar mis turnos

1. Iniciar sesión.
2. Ir a la opción **Mis Turnos**.
3. Revisar los turnos registrados.
4. Verificar estado del turno: pendiente, confirmado o cancelado.

### 12.5 Cancelar turno

1. Ingresar a **Mis Turnos**.
2. Seleccionar el turno a cancelar.
3. Presionar la opción de cancelar.
4. Confirmar la acción.
5. El sistema actualiza el estado del turno.

### 12.6 Reprogramar turno

1. Ingresar a **Mis Turnos**.
2. Seleccionar el turno a reprogramar.
3. Elegir nueva fecha y hora.
4. Confirmar el cambio.
5. El sistema actualiza la información del turno.

### 12.7 Consultar notificaciones

1. Iniciar sesión.
2. Ir a la opción **Notificaciones**.
3. Revisar las notificaciones generadas por el sistema.
4. Usar filtros si están disponibles.
5. Marcar notificaciones como leídas cuando corresponda.

### 12.8 Consultar historial

1. Iniciar sesión.
2. Ir a la opción **Historial**.
3. Revisar las acciones registradas.
4. Verificar acciones como registro, login, creación de turno o cancelación.

---

## 13. Manual técnico de ejecución local

### 13.1 Requisitos previos

Antes de ejecutar el proyecto, instalar:

- Git.
- Docker Desktop.
- Java 17.
- Maven.
- Node.js.
- Angular CLI.
- Visual Studio Code.
- Postman.

---

## 14. Clonar el repositorio principal

```powershell
git clone https://github.com/Corhuila-Gestion-Citas/Gestion-De-Citas-Inteligente.git
cd Gestion-De-Citas-Inteligente
```

---

## 15. Ejecutar ambiente develop

```powershell
docker compose -f .\docker-compose.develop.yml up -d --build
```

Verificar contenedores:

```powershell
docker ps
```

Puertos principales:

```txt
API Gateway: http://localhost:8080
users-service: http://localhost:8081
turnos-service: http://localhost:8082
notifications-service: http://localhost:8083
audit-service: http://localhost:8084
```

---

## 16. Ejecutar ambiente QA

```powershell
docker compose -f .\docker-compose.qa.yml up -d --build
```

Puertos principales:

```txt
API Gateway QA: http://localhost:8180
users-service QA: http://localhost:8181
turnos-service QA: http://localhost:8182
notifications-service QA: http://localhost:8183
```

---

## 17. Ejecutar ambiente main

```powershell
docker compose -f .\docker-compose.main.yml up -d --build
```

Puertos principales:

```txt
API Gateway main: http://localhost:8280
users-service main: http://localhost:8281
turnos-service main: http://localhost:8282
notifications-service main: http://localhost:8283
```

---

## 18. Detener ambientes

### Detener develop

```powershell
docker compose -f .\docker-compose.develop.yml down
```

### Detener QA

```powershell
docker compose -f .\docker-compose.qa.yml down
```

### Detener main

```powershell
docker compose -f .\docker-compose.main.yml down
```

> Nota: el comando `down` detiene y elimina los contenedores, pero conserva los volúmenes si no se usa `-v`.

---

## 19. Ejecutar frontend local

Entrar a la carpeta del frontend:

```powershell
cd frontend\gestion-citas-frontend
```

Instalar dependencias:

```powershell
npm install
```

Ejecutar Angular:

```powershell
ng serve
```

Abrir en el navegador:

```txt
http://localhost:4200
```

---

## 20. Endpoints principales

### Usuarios

```txt
POST /users
POST /users/login
GET /users
GET /users/{id}
```

### Turnos

```txt
POST /turnos
GET /turnos
GET /turnos?idUsuario={id}
PUT /turnos/{id}/cancelar
PUT /turnos/{id}/reprogramar
```

### Notificaciones

```txt
GET /notifications
GET /notifications/user/{idUsuario}
PUT /notifications/{id}/read
```

### Auditoría

```txt
GET /audit
POST /audit
GET /audit/user/{idUsuario}
```

---

## 21. Pruebas en Postman

### Registro de usuario

```http
POST http://localhost:8080/users
```

Body:

```json
{
  "nombre": "Usuario Prueba",
  "email": "usuario.prueba@test.com",
  "password": "123456",
  "rol": "CLIENTE"
}
```

### Login

```http
POST http://localhost:8080/users/login
```

Body:

```json
{
  "email": "usuario.prueba@test.com",
  "password": "123456"
}
```

### Crear turno

```http
POST http://localhost:8080/turnos
```

Body:

```json
{
  "idUsuario": 1,
  "especialidad": "Medicina general",
  "doctor": "Dra. Camila Torres",
  "fechaHora": "2026-06-01T10:00:00"
}
```

---

## 22. Validación de Liquibase

Liquibase se utiliza para administrar cambios de base de datos en PostgreSQL.

### Verificar tablas en usersdb_main

```powershell
docker exec -it users-db-main psql -U postgres -d usersdb_main -c "\dt"
```

### Verificar cambios ejecutados

```powershell
docker exec -it users-db-main psql -U postgres -d usersdb_main -c "SELECT id, author, filename, dateexecuted, exectype FROM databasechangelog;"
```

### Verificar bloqueo

```powershell
docker exec -it users-db-main psql -U postgres -d usersdb_main -c "SELECT * FROM databasechangeloglock;"
```

El resultado esperado es:

```txt
locked = f
```

---

## 23. Validación de GitHub Actions

El proyecto utiliza GitHub Actions para validar compilación y configuración.

La evidencia se puede revisar en:

```txt
Repositorio -> Actions
```

Se debe verificar que los últimos workflows estén en estado exitoso.

---

## 24. Validación del despliegue

### Frontend

1. Abrir la URL pública.
2. Confirmar que carga la pantalla de login.
3. Iniciar sesión con credenciales de prueba.
4. Validar las funcionalidades principales.

### Backend / Render

1. Abrir la URL del API Gateway desplegado.
2. Probar endpoints de salud o consulta.
3. Confirmar que el frontend consume correctamente el backend desplegado.

---

## 25. Errores comunes y solución

### Error: puerto ocupado

Solución:

```powershell
docker ps
```

Detener contenedores que estén usando el puerto:

```powershell
docker stop NOMBRE_CONTENEDOR
```

---

### Error: contenedor se apaga

Revisar logs:

```powershell
docker logs NOMBRE_CONTENEDOR
```

---

### Error: Liquibase relation already exists

Puede ocurrir cuando la tabla ya existe. Solución:

- Revisar la tabla `databasechangelog`.
- Validar que no se esté recreando una tabla existente.
- Reiniciar el ambiente solo si no se necesitan los datos.

---

### Error: frontend no consume backend

Revisar:

- URL del API Gateway.
- Configuración de CORS.
- Que los servicios estén levantados.
- Que el endpoint exista.

---

## 26. Evidencias recomendadas para entrega

Se recomienda adjuntar capturas de:

- Aplicación desplegada.
- Login exitoso.
- Registro de usuario.
- Solicitud de turno.
- Mis turnos.
- Notificaciones.
- Historial de auditoría.
- Render activo.
- GitHub Actions exitoso.
- Ramas develop, qa y main.
- Acceso para ariel5253.
- Liquibase `databasechangelog`.
- Docker Desktop con contenedores activos.

---

## 27. Conclusión

El proyecto Gestión de Citas Inteligente evidencia una solución distribuida con frontend, API Gateway, microservicios, bases de datos separadas, migraciones con Liquibase, contenedores Docker, flujo Git por ramas, integración continua y despliegue en la nube.

La arquitectura implementada permite separar responsabilidades, facilitar el mantenimiento, organizar el trabajo por ambientes y demostrar conceptos propios de Sistemas Distribuidos.
