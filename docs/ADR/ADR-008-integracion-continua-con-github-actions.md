# ADR-008: Integración continua con GitHub Actions

## Estado
Aceptado

## Fecha
2026-05-18

## Contexto
El proyecto Gestión de Citas Inteligente está compuesto por varios componentes: frontend, API Gateway, microservicios, bases de datos y archivos Docker. Al trabajar en equipo, cada integrante puede subir cambios que afecten la compilación o el funcionamiento general del sistema.

Por esta razón, se necesita una forma de validar automáticamente que el proyecto mantenga una estructura correcta y que los cambios subidos al repositorio no rompan el avance del equipo.

## Decisión
Se decidió utilizar GitHub Actions como herramienta de integración continua del proyecto.

GitHub Actions permite ejecutar validaciones automáticas cuando se suben cambios al repositorio, por ejemplo:

- Verificar que el código se pueda compilar.
- Revisar errores básicos antes de integrar cambios.
- Apoyar el flujo de trabajo con ramas como develop, QA y main.
- Mantener mayor control sobre los cambios realizados por el equipo.

## Alternativas consideradas
- Revisar manualmente cada cambio antes de subirlo.
- Compilar el proyecto solo en el computador de cada integrante.
- No usar integración continua.
- Usar otra herramienta externa de CI/CD.

## Consecuencias positivas
- Ayuda a detectar errores antes de integrar cambios importantes.
- Mejora el trabajo colaborativo del equipo.
- Permite tener mayor confianza al hacer pull requests.
- Facilita mantener estable la rama principal de desarrollo.
- Deja evidencia de buenas prácticas DevOps en el proyecto.

## Consecuencias negativas o riesgos
- Requiere configurar correctamente el archivo del workflow.
- Si el workflow está mal configurado, puede fallar aunque el código esté bien.
- Puede aumentar el tiempo de validación antes de aceptar cambios.
- El equipo debe aprender a interpretar los errores que muestre GitHub Actions.

## Relación con el proyecto
Esta decisión se evidencia en:

- .github/workflows/ci.yml
- backend/api-gateway/
- backend/users-service/
- backend/turnos-service/
- backend/notifications-service/
- backend/audit-service/
- frontend/gestion-citas-frontend/
