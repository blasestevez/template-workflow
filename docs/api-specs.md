# Project API Specs & Contracts

Base URL: `http://localhost:5000/api` (ajustar según entorno)

Autenticación: `Bearer <token>` en header `Authorization` (o el mecanismo acordado).

---

## Convenciones de Respuestas

### Éxito
```json
{
  "success": true,
  "data": {},
  "message": "Operación exitosa"
}
```

### Error
```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Descripción detallada del error",
    "details": []
  }
}
```

---

## Módulos y Endpoints

### 1. Auth Module
- `POST /api/auth/register` - Registro de usuario
- `POST /api/auth/login` - Inicio de sesión
- `GET /api/auth/me` - Perfil de usuario actual

### 2. [Nombre del Recurso] Module
- `GET /api/resources` - Lista de recursos
- `POST /api/resources` - Crear recurso
- `GET /api/resources/{id}` - Obtener recurso por ID
- `PUT /api/resources/{id}` - Actualizar recurso
- `DELETE /api/resources/{id}` - Eliminar recurso

#### POST /api/resources
**Request Body:**
```json
{
  "name": "string",
  "description": "string"
}
```

**Response Body (201 Created):**
```json
{
  "id": "string",
  "name": "string",
  "description": "string",
  "createdAt": "2026-01-01T00:00:00Z"
}
```
