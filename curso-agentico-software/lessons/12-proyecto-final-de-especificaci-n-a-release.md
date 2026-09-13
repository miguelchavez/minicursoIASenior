# Proyecto final: de especificación a release


# Proyecto final

Entrega una versión funcional de **Entidades**.

## Definition of Done

### Producto

- [ ] CRUD de nota.
- [ ] CRUD de tarea.
- [ ] CRUD de liga.
- [ ] Listado unificado.
- [ ] Filtros.
- [ ] Ordenamiento.
- [ ] Búsqueda.
- [ ] Editor basado en schema.
- [ ] Validación.
- [ ] Persistencia local.
- [ ] UI adaptada a móvil y web.

### Arquitectura

- [ ] Domain no importa UI.
- [ ] Application no conoce React.
- [ ] Adapters implementan ports.
- [ ] Schemas versionados.
- [ ] No hay `if entityType` repartidos por toda la UI.

### Seguridad

- [ ] `.env` fuera del contexto.
- [ ] permisos mínimos para agentes.
- [ ] comandos destructivos protegidos.
- [ ] dependencias revisadas.
- [ ] inputs validados.
- [ ] URLs tratadas como datos no confiables.

### Calidad

- [ ] tests unitarios.
- [ ] tests de integración.
- [ ] lint.
- [ ] typecheck.
- [ ] diff revisado.
- [ ] ADRs relevantes.
- [ ] commits pequeños.

## Reto final de agencia

Realiza una feature nueva:

> `bookmark` como entidad que guarda una URL y genera/almacena metadata.

No escribas el código tú primero.

Haz:

```text
spec → plan → agent → tests → review → diff → commit
```

Al terminar, escribe una retrospectiva:

1. ¿Qué delegaste?
2. ¿Qué rechazaste?
3. ¿Qué error cometió el agente?
4. ¿Qué guardrail evitó un problema?
5. ¿Qué decisión arquitectónica sigue siendo tuya?


## Ejercicio

Publica tu propio scorecard de la sesión: velocidad, calidad, errores, reversibilidad y confianza. La confianza es un resultado, no una premisa.
