# Sesión agentica: OpenCode


# Sesión agéntica: OpenCode

OpenCode es un agente de coding para terminal, escritorio o extensión de IDE y permite trabajar con distintos proveedores de modelos. Su documentación actual distingue agentes primarios como Build y Plan, además de subagentes especializados. citeturn0search2turn0search4

## Primera sesión

```bash
cd entidades
opencode
```

Inicializa el contexto del proyecto:

```text
/init
```

La documentación de OpenCode indica que esto puede generar `AGENTS.md`; recomienda versionarlo para conservar las convenciones del proyecto. citeturn0search2

## Patrón Plan → Build → Review

### Plan

```text
Analiza el issue #12.

No edites archivos.

Entrega:
1. archivos que cambiarías;
2. invariantes;
3. riesgos;
4. tests necesarios;
5. plan en pasos pequeños.
```

### Build

```text
Implementa únicamente el paso 1 del plan.

Restricciones:
- no cambies dependencias;
- no modifiques el schema;
- agrega tests;
- detente al terminar el paso.
```

### Review

```text
Revisa el diff actual como auditor independiente.

Busca:
- regresiones;
- violaciones de arquitectura;
- validación insuficiente;
- datos sensibles;
- tests engañosos.

No edites.
Reporta severidad y evidencia.
```

## Permisos

La idea de Plan como agente restringido es valiosa: primero se analiza y luego se habilitan acciones. OpenCode permite configurar permisos y crear agentes especializados. citeturn0search4

**Principio:** permiso amplio + contexto ambiguo = riesgo amplio.


## Ejercicio

Ejecuta una sesión Plan → Build → Review sobre una sola función. Guarda los tres resultados como artefactos de la sesión.
