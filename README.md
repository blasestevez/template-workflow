# Template Workflow Multi-Agente (Stack-Agnostic)

Esta plantilla contiene la arquitectura base de desarrollo colaborativo multi-agente con roles especializados (Planner, Backend, Frontend, Testing), skills agnósticos de tecnología, documentación de contratos y plantillas de features.

---

## 📁 Estructura del Template

```text
template-workflow/
├── .agents/
│   └── skills/
│       ├── planner-workflow/       # Orquestador: análisis, división de tareas y contratos
│       ├── backend-workflow/       # Principios generales de arquitectura y APIs
│       ├── frontend-workflow/      # Componentes, estado y flujos de UI
│       ├── testing-workflow/       # Pirámide de pruebas, verificación y QA
│       └── impeccable/             # Pulido de UI, microinteracciones, accesibilidad y UX
├── backend/
│   └── AGENTS.md                   # Reglas y contexto para el agente de Backend
├── frontend/
│   └── AGENTS.md                   # Reglas y contexto para el agente de Frontend
├── tests/
│   └── AGENTS.md                   # Reglas y contexto para el agente de Testing
├── docs/
│   ├── workflow-agents.md          # Arquitectura y flujo multi-agente explicado
│   ├── api-specs.md                # Plantilla centralizada de contratos de endpoints y DTOs
│   └── features/                   # Directorio donde se guardan los planes de cada feature
├── AGENTS.md                       # Reglas globales del proyecto (activa al Planner por defecto)
├── skills-lock.json                # Lock de skills instaladas
└── README.md                       # Esta guía
```

---

## 🚀 Cómo Usar este Template en un Nuevo Proyecto

1. **Copiar la plantilla**:
   Copia el contenido de `template-workflow` en la carpeta de tu nuevo proyecto:
   ```bash
   cp -r template-workflow mi-nuevo-proyecto
   cd mi-nuevo-proyecto
   git init
   ```

2. **(Opcional) Agregar skills de tu stack específico**:
   Si tu proyecto usa un stack particular (por ejemplo: .NET, Next.js, FastAPI, Spring Boot, Go, Flutter, etc.), puedes colocar sus skills en `.agents/skills/[mi-stack-skill]` y mencionarlas en el `AGENTS.md` correspondiente (`backend/AGENTS.md` o `frontend/AGENTS.md`).

3. **Abrir en tu entorno con IA (Antigravity CLI / IDE)**:
   Al iniciar, el asistente detectará automáticamente `AGENTS.md` y operará como **Planner**.

---

## 💬 Prompts para Usar este Workflow en Nuevos Proyectos

### 1. Inicializar el Proyecto o Arquitectura Inicial
> *"Actúa como el **Agente Planner** bajo las directrices de `AGENTS.md` y `planner-workflow`. Quiero crear un nuevo proyecto llamado `[Nombre]` con el siguiente objetivo: `[descripción de la app]`.
> Stack previsto: Backend en `[ej: Node / Go / Python / C# / Rust]`, Frontend en `[ej: React / Vue / Svelte / Flutter]` y BD `[ej: PostgreSQL / MongoDB / SQLite]`.
> Define la arquitectura inicial, la estructura de carpetas y la primera lista de tareas de scaffolding en `docs/features/feature-01-scaffold.md`."*

---

### 2. Planificar una Nueva Feature
> *"Como **Agente Planner**, quiero diseñar la feature `[ej: Autenticación / Checkout / Dashboard / Notificaciones]`.
> Por favor:
> 1. Analiza los requerimientos y hazme preguntas si hay dudas.
> 2. Diseña los contratos de API y regístralos en `docs/api-specs.md`.
> 3. Crea el plan detallado con tareas ordenadas por dependencias en `docs/features/feature-[nombre].md` siguiendo la plantilla de `planner-workflow`."*

---

### 3. Ejecutar Tareas de Backend
> *"Adopta el rol de **Agente Backend** siguiendo `backend-workflow` y las directivas de `backend/AGENTS.md`. Implementa la tarea `[TASK-001]` del plan `[docs/features/feature-xxx.md]`. Asegúrate de respetar el contrato definido en `docs/api-specs.md`."*

---

### 4. Ejecutar Tareas de Frontend
> *"Adopta el rol de **Agente Frontend** usando `frontend-workflow` e `impeccable`, respetando `frontend/AGENTS.md`. Desarrolla la tarea `[TASK-006]` conectando los componentes con el endpoint según el contrato de `docs/api-specs.md`. Cuida la accesibilidad, estados de carga/error y consistencia visual."*

---

### 5. Ejecutar Tareas de Testing / QA
> *"Adopta el rol de **Agente Testing** bajo `testing-workflow` y `tests/AGENTS.md`. Diseña y ejecuta las pruebas correspondientes a la tarea `[TASK-004]`: tests unitarios y de integración para verificar los endpoints implementados y validar los casos de error (400, 401, 404)."*

---

### 6. Verificación, Integración y Cierre de Feature
> *"Como **Agente Planner**, revisa el progreso de la feature `[nombre]`:
> - Verifica que todas las tareas del plan estén completadas.
> - Comprueba que los tests pasen exitosamente.
> - Confirma la coherencia entre el contrato en `docs/api-specs.md`, la implementación en `backend/` y el consumo en `frontend/`."*
