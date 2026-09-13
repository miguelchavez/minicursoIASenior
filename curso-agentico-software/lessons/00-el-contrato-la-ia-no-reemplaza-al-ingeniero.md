# El contrato: la IA no reemplaza al ingeniero


# El contrato: la IA no reemplaza al ingeniero

Este curso parte de una premisa deliberadamente conservadora:

> **El agente puede escribir código; el ingeniero sigue siendo responsable de decidir qué código merece existir.**

Para un desarrollador senior, el cambio no es aprender a “programar con magia”. Es aprender a **orquestar trabajo de ingeniería con una máquina que puede leer, modificar, ejecutar y revisar un repositorio**.

## El modelo mental

Piensa en un agente como un junior extremadamente rápido que:

- puede trabajar durante mucho tiempo sin cansarse;
- puede explorar miles de líneas;
- puede producir muchas alternativas;
- no conoce tu intención si no la haces explícita;
- puede equivocarse con una seguridad impresionante;
- puede ejecutar acciones con impacto real.

Por eso el flujo sano es:

**intención → plan → evidencia → cambio pequeño → pruebas → revisión → commit**

No es:

**prompt → 2.000 líneas → “parece que funciona”**

## Regla de oro

La IA acelera el *throughput* de decisiones. Por eso el cuello de botella se desplaza hacia:

1. arquitectura;
2. especificación;
3. límites de seguridad;
4. pruebas;
5. revisión.

El objetivo del curso no es que confíes más en la IA. Es que puedas **confiar menos y verificar mejor**.

## Señales de una buena sesión

- El agente puede explicar por qué va a tocar cada archivo.
- Los cambios son pequeños y reversibles.
- Hay pruebas antes o junto al cambio.
- El diff es comprensible.
- Los secretos nunca forman parte del contexto por accidente.
- Un segundo agente puede revisar el trabajo sin necesidad de creerle al primero.


## Ejercicio

Escribe tres tareas de tu trabajo que delegarías a un agente y tres que conservarías bajo control manual. Justifica la diferencia.
