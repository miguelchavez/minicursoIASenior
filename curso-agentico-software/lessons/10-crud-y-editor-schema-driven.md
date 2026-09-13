# CRUD y editor schema-driven


# CRUD y editor schema-driven

El CRUD se implementa como casos de uso, no como botones que escriben directamente en la base.

```text
Screen
  ↓
useCreateItem()
  ↓
CreateItem
  ↓
ItemRepository
  ↓
StorageAdapter
```

## Query

El listado debe aceptar una consulta declarativa:

```ts
type ItemQuery = {
  entityTypes?: string[];
  search?: string;
  filters?: Filter[];
  sort?: SortSpec[];
  limit?: number;
  cursor?: string;
};
```

## Filtros

No conviertas filtros en SQL/SQLite arbitrario generado desde la UI.

Define un AST seguro:

```ts
type Filter =
  | { field: string; op: "eq" | "contains" | "gte" | "lte"; value: unknown }
  | { and: Filter[] }
  | { or: Filter[] };
```

Luego el adapter traduce ese AST a su mecanismo de almacenamiento.

## Editor

El renderer recibe:

```ts
type EntityEditorProps = {
  schema: JSONSchema;
  value: unknown;
  onChange(value: unknown): void;
  errors: ValidationError[];
};
```

No conoce `nota`, `tarea` o `liga`.

## Regla de validación

```text
form state
  ↓
schema validation
  ↓
domain validation
  ↓
use case
  ↓
repository
```

El servidor futuro debe repetir las validaciones relevantes.

## Extensibilidad

Agregar `contacto.json` debería requerir:

```text
schema + metadata + registro de entidad
```

y no:

```text
ContactScreen.tsx
ContactForm.tsx
ContactService.ts
ContactRepository.ts
...
```

salvo que el nuevo tipo tenga comportamiento realmente excepcional.


## Ejercicio

Implementa primero `listItems`, después `createItem`, y solo entonces el renderer. Mantén cada commit pequeño.
