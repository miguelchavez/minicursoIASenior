# Testing, revisión y Git para el programador solitario


# Testing, revisión y Git

Trabajar solo no significa trabajar sin revisión. Significa que debes **industrializar la revisión**.

## Pirámide

```text
        E2E
       /   \
   integration
      /     \
 unit / domain
```

El agente debe ayudarte a producir tests, pero tú debes juzgar si los tests prueban algo real.

## Test que engaña

```ts
expect(result).toBeDefined();
```

puede pasar aunque la lógica esté rota.

Prefiere:

```ts
expect(result.entityType).toBe("nota");
expect(result.data.title).toBe("Comprar leche");
```

## Review en dos pasadas

### Pasada mecánica

```bash
npm test
npm run lint
npm run typecheck
```

### Pasada semántica

Pregunta:

```text
¿Este cambio conserva las invariantes?
¿Puede aceptar datos no válidos?
¿Rompe una frontera arquitectónica?
¿Introduce una dependencia innecesaria?
¿Hace una operación irreversible?
```

## Git

Para trabajo agentico:

```text
1 feature = varios commits pequeños
```

Ejemplo:

```text
feat(domain): define Item
feat(app): add createItem use case
test(app): cover createItem invariants
feat(ui): render entity editor
```

No mezcles:

```text
refactor + feature + prettier + dependency update
```

en el mismo commit generado por un agente.

## Pull requests remotas

Aunque seas principalmente solitario, una PR debe poder explicar:

- qué cambió;
- por qué;
- qué evidencia existe;
- qué riesgos quedan.


## Ejercicio

Pide al agente que revise un diff y luego intenta refutar al agente. La meta no es demostrar que la IA funciona; es encontrar lo que se le escapó.
