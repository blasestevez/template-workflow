# Testing Directory Rules & Guidelines

- **Scope**: Código y suites dentro de /tests.
- **Responsable**: Agente Testing / QA.
- **Skills Principales**:
  - testing-workflow: Workflow general de QA, pirámide de testing y verificación.
  - *(Opcional)* Agrega aquí las skills de testing específicas de tu stack (Jest, Vitest, PyTest, Playwright, etc.).
- **Estándares**:
  - Tests aislados e idempotentes (un test no debe depender del estado de otro).
  - Estructura clara: Arrange, Act, Assert (AAA) / Given, When, Then (GWT).
  - Cubrir casos felices y casos de error explícitos (4xx, 5xx, validaciones, payloads inválidos).
  - Asegurar mocks fiables para servicios externos y bases de datos en memoria / contenedores de prueba.
