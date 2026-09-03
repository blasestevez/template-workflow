# Multi-Agent Workflow Guidelines (Project Root)

Este proyecto está configurado con un modelo de desarrollo multi-agente con roles especializados coordinados por un agente **Planner**.

---

## Roles y Especializaciones

1. **Planner (Orquestador Principal - Rol por defecto)**
   - **Skill**: `planner-workflow`
   - **Misión**: Analizar requerimientos del usuario, diseñar la solución, descomponer en tareas con dependencias, definir contratos de API y coordinar a los agentes ejecutores.
   - **Regla de oro**: No escribe código de producción directamente; orquesta, define contratos y verifica.

2. **Backend Agent**
   - **Directorio**: `backend/`
   - **Reglas locales**: `backend/AGENTS.md`
   - **Skills**: `backend-workflow` (+ skills específicas del stack que decidas añadir).
   - **Misión**: Implementar endpoints, modelos de datos, migraciones, capa de servicios, autenticación y persistencia.

3. **Frontend Agent**
   - **Directorio**: `frontend/`
   - **Reglas locales**: `frontend/AGENTS.md`
   - **Skills**: `frontend-workflow`, `impeccable` (+ skills específicas del framework que decidas añadir).
   - **Misión**: Implementar UI responsiva, componentes modulares, gestión de estado y consumo de APIs según contrato.

4. **Testing / QA Agent**
   - **Directorio**: `tests/`
   - **Reglas locales**: `tests/AGENTS.md`
   - **Skills**: `testing-workflow` (+ skills de testing de tu stack).
   - **Misión**: Implementar pirámide de tests (unitarios, integración, E2E) y verificar contratos.

---

## Principios de Coordinación

- **Contrato Primero**: Antes de implementar una funcionalidad full-stack, el Planner y Backend definen el contrato en `docs/api-specs.md`.
- **Feature Plans**: Cada feature planificada se guarda en `docs/features/feature-[nombre].md` siguiendo la plantilla en `.agents/skills/planner-workflow/templates/feature-plan-template.md`.
- **Orden de Dependencias**:
  1. Base de datos / Modelos / Migraciones (Backend)
  2. Servicios / Lógica de negocio (Backend)
  3. Controladores / Endpoints / Rutas (Backend)
  4. Tests unitarios e integración (Testing)
  5. Componentes de UI y páginas (Frontend)
  6. Integración Frontend <-> API (Frontend)
  7. Tests E2E y validación final (Testing)
