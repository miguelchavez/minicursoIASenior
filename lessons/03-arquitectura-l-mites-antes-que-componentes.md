# Arquitectura: límites antes que componentes


# Arquitectura: límites antes que componentes

Usaremos una arquitectura pragmática inspirada en Hexagonal/Clean Architecture.

```text
UI / Expo
   │
   ▼
Application ───────► Domain
   │                   ▲
   ▼                   │
Ports ◄──────── Adapters
   │
   ├── storage
   ├── URL metadata
   └── future sync
```

## Capas

### Domain
Entidades, invariantes, tipos y reglas.

### Application
Casos de uso:

```ts
createItem()
updateItem()
deleteItem()
listItems()
filterItems()
sortItems()
```

### Ports
Interfaces que describen dependencias externas.

```ts
export interface ItemRepository {
  create(item: Item): Promise<Item>;
  update(id: string, patch: ItemPatch): Promise<Item>;
  delete(id: string): Promise<void>;
  list(query: ItemQuery): Promise<Item[]>;
}
```

### Adapters
Implementaciones concretas: SQLite, AsyncStorage, API remota, etc.

### UI
Pantallas, componentes, navegación y formularios.

## Regla contra el agente

Nunca pidas:

> “Implementa todo el CRUD.”

Pide:

> “Implementa `createItem` dentro de Application. No modifiques Domain, adapters ni UI. Agrega tests unitarios para las invariantes X e Y.”

El alcance pequeño es una **herramienta de control de calidad**.

## ADRs

Cada decisión que pueda afectar futuras sesiones debe quedar documentada.

```md
# ADR-004: Items almacenan entityType + data

## Decisión
...

## Contexto
...

## Consecuencias
...
```


## Ejercicio

Dibuja tus límites en una hoja. Luego compara el diagrama con la estructura de carpetas que propone el agente. El agente no gana por defecto: gana si sus límites son mejores.
