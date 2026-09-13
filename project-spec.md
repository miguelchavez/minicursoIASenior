# Entidades — especificación del proyecto

## Objetivo

Aplicación móvil multiplataforma (iOS/Android) y web para gestionar tres clases de items: `nota`, `tarea`, `liga`.

## Modelo

```ts
type Item = {
  id: string;
  entityType: "nota" | "tarea" | "liga" | string;
  data: Record<string, unknown>;
  metadata: {
    createdAt: string;
    updatedAt: string;
    version: number;
  };
};
```

## Arquitectura propuesta

```text
src/
  domain/
  application/
  ports/
  adapters/
  entities/
  ui/
  navigation/
  infrastructure/
tests/
docs/
schemas/
```

## Restricciones

1. Domain no importa React Native.
2. Application no importa UI.
3. Los adapters implementan ports.
4. Los schemas son versionados.
5. La UI no genera consultas de almacenamiento arbitrarias.
6. Los filtros se representan como AST seguro.
7. Toda entrada externa se valida.
8. Los agentes deben trabajar en cambios pequeños y verificables.
9. No se almacenan secretos en el repositorio.
10. Los artefactos generados por herramientas se controlan explícitamente con Git.

## Definition of Done

Ver `course.md` y la lección final.
