# Backend Directory Rules & Guidelines

- **Scope**: Código dentro de /backend.
- **Responsable**: Agente Backend.
- **Skills Principales**:
  - backend-workflow: Workflow general de APIs, arquitectura y persistencia.
  - *(Opcional)* Agrega aquí las skills específicas del stack que uses (Node, Go, Python, C#, Java, etc.).
- **Estándares**:
  - Mantener arquitectura limpia y desacoplada (Clean Architecture / Domain-Driven Design / Modular Monolith / Hexagonal).
  - Validar todos los payloads de entrada antes de procesar reglas de negocio.
  - Documentar cambios de endpoints o DTOs/schemas en docs/api-specs.md para coordinar con Frontend y Testing.
  - Cuidar la integridad de datos y evitar problemas de performance (queries N+1, fugas de memoria).
