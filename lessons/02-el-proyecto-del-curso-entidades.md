# El proyecto del curso: Entidades


# El proyecto: Entidades

Construiremos una aplicación móvil multiplataforma llamada **Entidades**.

Una entidad es una definición de estructura y comportamiento:

```text
Entidad
 ├── nombre: nota | tarea | liga
 ├── schema: JSON Schema
 ├── metadata: título, icono, versión, orden
 └── editor: generado desde el schema
```

Y cada item concreto contiene:

```text
Item
 ├── id
 ├── entityType
 ├── data
 ├── metadata
 ├── createdAt
 ├── updatedAt
 └── version
```

## Requisitos funcionales

- CRUD de items.
- Listado unificado.
- Filtros dinámicos.
- Ordenamiento dinámico.
- Búsqueda.
- Editor generado desde JSON Schema.
- Tres entidades iniciales: `nota`, `tarea`, `liga`.
- Metadatos extensibles.
- Funcionamiento offline-first.
- Sincronización futura sin acoplar el dominio a una API concreta.

## Restricción arquitectónica

El editor no debe contener:

```ts
if (entityType === "nota") ...
if (entityType === "tarea") ...
```

Debe depender de:

```ts
schema + uiSchema + renderer
```

La meta es que agregar una nueva entidad implique principalmente agregar datos declarativos, no duplicar pantallas.

## Criterio senior

El proyecto no busca maximizar cantidad de código. Busca maximizar:

- separación de responsabilidades;
- reversibilidad;
- trazabilidad;
- testabilidad;
- seguridad;
- facilidad para que un agente comprenda el sistema.


## Ejercicio

Abre `schemas/nota.json`, `schemas/tarea.json` y `schemas/liga.json`. Modifica mentalmente la aplicación para añadir `contacto`. ¿Qué debería cambiar y qué no?
