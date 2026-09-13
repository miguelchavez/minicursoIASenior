# JSON Schema como contrato ejecutable


# JSON Schema como contrato ejecutable

El JSON Schema será una pieza central del proyecto.

No lo trataremos como documentación. Lo trataremos como **contrato ejecutable**.

## Separación importante

```text
Entity Definition
  ├── identity
  ├── JSON Schema      ← estructura y validación
  └── UI metadata      ← presentación y orden de campos

Item
  ├── entityType
  └── data             ← instancia validable
```

## Ejemplo

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "entity://nota/v1",
  "title": "Nota",
  "type": "object",
  "required": ["title", "body"],
  "properties": {
    "title": { "type": "string", "minLength": 1, "maxLength": 200 },
    "body": { "type": "string", "maxLength": 20000 },
    "tags": {
      "type": "array",
      "items": { "type": "string", "maxLength": 40 },
      "maxItems": 30
    }
  },
  "additionalProperties": false
}
```

## Invariante

El renderer no debe convertirse en un bypass de validación.

Validar en:

1. UI — feedback inmediato;
2. application/domain — regla real;
3. persistencia/entrada externa — última barrera.

Nunca confíes solamente en el cliente.

## Evolución de schema

Cada schema tiene versión.

```text
entity://nota/v1
entity://nota/v2
```

Una migración es explícita:

```text
v1 → migrator → v2
```

No dejes que el agente “arregle” datos históricos implícitamente.


## Ejercicio

Agrega un campo opcional a `nota`. Diseña la migración v1→v2 antes de tocar el renderer.
