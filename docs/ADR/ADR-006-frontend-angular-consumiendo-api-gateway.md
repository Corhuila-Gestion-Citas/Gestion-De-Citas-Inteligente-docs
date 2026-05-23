# ADR-006: Frontend Angular consumiendo el API Gateway

## Estado
Aceptado

## Fecha
2026-05-18

## Contexto
El proyecto requiere una interfaz web para que los usuarios puedan iniciar sesión, registrarse, solicitar turnos, consultar sus citas, ver notificaciones y editar su perfil.

El frontend no debe conectarse directamente a cada microservicio porque eso haría más difícil cambiar puertos, rutas o nombres de contenedores.

## Decisión
Se decidió crear un frontend en Angular que consuma el backend a través del API Gateway.

El frontend usa una configuración central donde se define la URL del gateway:

- http://localhost:8080

Desde ahí consume rutas como:

- /users
- /turnos
- /notifications
- /audit

## Alternativas consideradas
- Crear el frontend con React.
- Crear páginas HTML estáticas.
- Conectar Angular directamente a cada microservicio.
- No crear frontend y probar solo con Postman.

## Consecuencias positivas
- El usuario tiene una interfaz visual para usar el sistema.
- El frontend solo necesita conocer una URL principal.
- Se mantiene mejor separación entre presentación y backend.
- Facilita cambiar rutas internas sin modificar todas las pantallas.
- Permite probar el flujo completo desde navegador.

## Consecuencias negativas o riesgos
- Si el API Gateway no está activo, el frontend no puede consumir los servicios.
- Se debe configurar correctamente CORS.
- Se deben mantener sincronizados los modelos del frontend con los DTO del backend.
- Puede haber errores si las rutas del frontend no coinciden con las rutas reales del backend.

## Relación con el proyecto
Esta decisión se evidencia en:

- frontend/gestion-citas-frontend/
- src/app/config/api.config.ts
- src/app/services/usuario.service.ts
- src/app/services/notificaciones.ts
- src/app/services/audit.service.ts
- src/app/pages/
