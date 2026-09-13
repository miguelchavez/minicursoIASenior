# Sesión agentica: Pi


# Sesión agéntica: Pi

Pi se presenta como un *minimal terminal coding harness*, con un núcleo pequeño que puede extenderse mediante TypeScript, skills, plantillas de prompt, temas y paquetes. citeturn0search8

La lección importante para un senior no es memorizar comandos. Es aprender a distinguir:

```text
runtime del agente
        +
modelo
        +
herramientas
        +
políticas
        +
contexto del proyecto
```

## Sesión segura

Empieza con lectura:

```text
Inspecciona la arquitectura de `src/`.

No edites.

Devuelve:
- mapa de módulos;
- dependencias;
- puntos de entrada;
- deuda arquitectónica;
- preguntas abiertas.
```

Luego acota:

```text
Implementa solamente `listItems`.

No cambies interfaces públicas.
No agregues dependencias.
Agrega tests.
No toques UI.
```

## Cuándo preferir Pi

- quieres un harness minimalista;
- deseas construir tu propio workflow;
- quieres extensiones TypeScript;
- quieres reducir “magia” del entorno.

## Cuándo preferir OpenCode

- quieres agentes primarios/subagentes listos;
- permisos configurables;
- workflows orientados a repo;
- integración cómoda con distintos proveedores.

No existe un “mejor agente” universal. El curso evalúa el **sistema de trabajo**, no la marca.


## Ejercicio

Repite la misma tarea pequeña con OpenCode y Pi. Compara diff, tiempo, número de iteraciones y errores.
