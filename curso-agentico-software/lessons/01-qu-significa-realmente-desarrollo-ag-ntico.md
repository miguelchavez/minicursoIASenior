# Qué significa realmente desarrollo agéntico


# Qué significa realmente desarrollo agéntico

Un asistente de chat responde texto. Un copiloto propone cambios. Un **agente de coding** puede cerrar un ciclo operativo:

```text
leer → razonar → editar → ejecutar → observar → corregir
```

La diferencia importante no es el modelo. Es el **bucle de herramientas**.

## Cuatro niveles

| Nivel | Acción principal | Riesgo |
|---|---|---|
| Chat | Responder | Bajo |
| Copilot | Sugerir | Medio |
| Agent | Ejecutar tareas | Alto |
| Agent + automatización | Ejecutar procesos | Muy alto |

En este curso utilizaremos agentes, pero con una filosofía de *bounded autonomy*:

> **Más autonomía solamente cuando la evidencia y los controles también aumentan.**

## El ciclo AGENT

### A — Acordar
Define objetivo, alcance, no-objetivos y criterios de aceptación.

### G — Guiar
Entrega arquitectura, convenciones, restricciones y archivos relevantes.

### E — Ejecutar
Permite al agente modificar un área acotada.

### N — Notar evidencia
Tests, lint, typecheck, diff, logs y comportamiento observado.

### T — Terminar
Revisión, commit pequeño y registro de decisiones.

## La pregunta senior

No preguntes:

> “¿Qué prompt hace que la IA programe mejor?”

Pregunta:

> “¿Qué sistema hace que una mala decisión de la IA sea barata de detectar y revertir?”


## Ejercicio

Toma una feature real y redacta objetivo, no-objetivos, criterios de aceptación y comandos de verificación antes de pedir código.
