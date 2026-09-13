# Gentle-AI: memoria, contexto y CodeGraph


# Gentle-AI: memoria, contexto y CodeGraph

Gentle-AI configura agentes existentes en vez de instalar un agente por ti. Su ecosistema actual incluye Engram, skills, SDD, Context7, permisos y herramientas opcionales; también documenta integración con Pi y CodeGraph. citeturn1search0turn1search3

## Engram

Engram conserva decisiones, descubrimientos y contexto entre sesiones. La documentación indica que la memoria puede inspeccionarse y sincronizarse al proyecto con:

```bash
engram tui
engram search "auth refactor"
engram sync
```

citeturn0search11

Esto es especialmente útil para un programador solitario: reduce la necesidad de reconstruir el contexto al día siguiente.

## CodeGraph

La idea de CodeGraph es cambiar:

```text
grep → leer muchos archivos → inferir relaciones
```

por:

```text
pregunta estructural → grafo → explorar impacto
```

Gentle-AI documenta integración con CodeGraph y, para Pi, una ruta de exploración de solo lectura mediante MCP. citeturn1search3

## Pero cuidado

Memoria no significa verdad.

Grafo no significa arquitectura correcta.

El agente debe usar estas herramientas como **evidencia auxiliar**, no como sustituto de:

- lectura del contrato;
- tests;
- revisión del diff;
- documentación oficial;
- criterio humano.

## Regla de seguridad

Los artefactos generados por herramientas deben tener límites claros.

Por ejemplo, si `.codegraph/` se genera en el workspace, decide explícitamente si debe estar en Git o en `.gitignore`. Una herramienta de exploración no debe contaminar el historial del producto por accidente.


## Ejercicio

Registra una decisión arquitectónica en memoria. Cierra la sesión. En la siguiente sesión, recupera la decisión y verifica que sigue siendo válida leyendo el código, no solo la memoria.
