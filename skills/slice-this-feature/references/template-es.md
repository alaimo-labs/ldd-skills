# Plan de exposición — [Nombre de la feature]

## Hipótesis del spec

Una oración. Si la spec declara explícitamente una "Hypothesis" o "Bet", se reproduce aquí. Si no, se infiere desde el Overview y los Success Criteria, en una sola oración, y se señala que es una inferencia.

## Mecanismo de exposición

**Recomendación:** [Exposición progresiva (feature flags) | Desarrollo incremental]

**Por qué:** [una o dos señales que justifican la elección — por ejemplo, "Los niveles 1–2 apuntan a cohortes específicas de estudiantes, lo que requiere targeting por feature flag" o "Todos los niveles se exponen a toda la base de usuarios; asumiendo que el agente de código mantiene contexto entre iteraciones, las capas se pueden desplegar a medida que se construyen"]

Solo una sugerencia — el equipo de ingeniería decide la implementación final.

## Niveles

Cada nivel acumula sobre el anterior. El Nivel 2 incluye todo lo del Nivel 1. El Nivel 3 incluye los Niveles 1 y 2. Se construye la feature completa; se revelan las capas según este plan.

### Nivel 1 — [Nombre desde la perspectiva del usuario]

Lo que se revela: [qué está visible en este nivel — lista concreta; qué queda deliberadamente oculto todavía]

**Belief:** [una claim falsable en términos de usuario/negocio]

**Audiencia:** [caracterizada por comportamiento o rol, no por porcentaje de tráfico]

**Duración:** [tiempo antes de decidir]

**Validation:**
- **Avanzar si:** [umbral o patrón concreto]
- **Detener si:** [umbral o patrón concreto]

### Nivel 2 — [Nombre]

Lo que se revela: [nuevo layer que se suma a lo anterior]

**Belief:** [...]

**Audiencia:** [...]

**Duración:** [...]

**Validation:**
- **Avanzar si:** [...]
- **Detener si:** [...]

[...continuar según el scope del spec. Un solo nivel si la feature es muy pequeña. Hasta 5 niveles si es muy grande. Típicamente 2–4.]

## Validaciones en paralelo

Riesgos que no se validan revelando una capa del producto, pero que corren el mismo reloj:

- **[Título corto]:** [1–2 oraciones — qué investigar, por qué importa]
- **[Título corto]:** [...]

## Preguntas abiertas para el equipo de producto

- [Restricción, dato, o decisión que el plan no puede resolver solo]
- [...]
