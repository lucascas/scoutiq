# Estrategia de Defensa — ScoutIQ PM Interview

## Preguntas difíciles y cómo responderlas

---

### "¿Por qué el Director Deportivo y no el entrenador?"

**Respuesta:** El entrenador tiene un JTBD valioso, pero difuso — sus necesidades van desde alineaciones hasta microdecisiones de entrenamiento. El Director Deportivo tiene un job-to-be-done concreto: evaluar candidatos de fichaje con rapidez y confianza. Además, en el contexto B2B, el Director Deportivo es quien tiene presupuesto de decisión. Si logramos que él vea valor, tenemos el contrato. Al entrenador lo consideramos en V2, cuando ya tenemos validación del modelo central.

---

### "¿Cómo calculas el Fit Score? ¿No es arbitrario?"

**Respuesta:** En el MVP, es un score ponderado configurable en base a 4 dimensiones tácticas (presión, combinativo, ofensivo, adaptabilidad). El peso de cada dimensión puede ser ajustado por el club. No es perfecto — y lo decimos explícitamente. El objetivo del MVP no es tener el algoritmo final sino validar que la capa de interpretación tática genera más valor que los datos crudos. Si el Director Deportivo dice "este score no refleja lo que necesito", eso es exactamente el learning que buscamos en el mes 1 post-MVP.

---

### "¿Qué pasa si el primer cliente pide algo que no está en el MVP?"

**Respuesta:** Depende de qué piden. Si es algo que valida la dirección estratégica (ej: comparación entre dos jugadores de la misma posición), lo priorizamos en el sprint siguiente. Si es algo tácticamente interesante pero que afectaría a un solo cliente, lo documentamos como feedback y lo sopesamos contra otros inputs. Lo que no hacemos es customizar el producto para un solo cliente sin señal de que otros lo necesiten también.

---

### "¿Cómo validan que los clubes van a pagar por esto?"

**Respuesta:** Tenemos dos señales en el MVP. Primera: el tiempo de evaluación baja de días a minutos — eso tiene ROI calculable cuando un fichaje puede costar €5-15M. Segunda: el modelo B2B SaaS (precio por usuario/club) es el estándar en el mercado (InStat, Wyscout). No inventamos el modelo de negocio, lo aplicamos a un segmento desatendido: clubes Tier 2-3 que no tienen presupuesto para equipos internos de data.

---

### "¿Por qué no integrar video en el MVP?"

**Respuesta:** Las licencias de video de fútbol profesional (ChyronHego, Stats Perform, clubes directamente) son costosas y tienen procesos de negociación largos. Con 6 meses de runway, el riesgo es alto. En el MVP, nuestra propuesta de valor es contextualizar stats existentes con encaje táctico — eso ya diferencia. Video es V2 o V3, cuando tengamos ingresos que justifiquen la inversión.

---

### "¿Cómo priorizás el backlog con 5 ingenieros en 6 meses?"

**Respuesta:** El criterio de priorización tiene tres capas. Primero, ¿esto bloquea el core journey? Si sí, es crítico. Segundo, ¿esto diferencia ScoutIQ de un simple agregador de stats? Si sí, es estratégico. Tercero, ¿esto genera evidencia para la siguiente ronda de funding o el próximo cliente? Si sí, es táctico. Todo lo que no cae en ninguna de las tres categorías no entra al MVP.

---

## Step 2 — Posibles sorpresas y cómo reaccionar

El business case da un ejemplo: **"Queremos benchmarking comparativo entre ligas para identificar jugadores infravalorados."** Aquí está el framework de respuesta live:

### Framework para cualquier sorpresa:

1. **Clarificar antes de construir.** Preguntar: "¿Quién usa esto, en qué contexto, y qué decisión toma con ello?" 30 segundos de claridad evitan 2 horas de trabajo equivocado.

2. **Definir el scope mínimo.** Identificar el caso de uso más estrecho que valida la hipótesis. No construir la feature completa — construir el "walking skeleton".

3. **Mostrar, no describir.** Abrir el prototipo y agregar la pantalla en vivo. Incluso si es simple, el impacto de ver algo funcional es enorme.

4. **Defender los trade-offs.** Explicar qué sacrificás al hacer esto ahora (velocidad, complejidad, deuda técnica) y si vale la pena.

---

### Respuesta al ejemplo: "Benchmarking comparativo entre ligas"

**Clarificación:** ¿Comparamos jugadores de distintas ligas para hacer más justo el Fit Score? ¿O queremos identificar jugadores que están en ligas de menor nivel pero rinden a nivel de liga superior?

**Scope mínimo para el prototipo:** Agregar una pantalla de "Comparación" que permita poner dos jugadores side-by-side con sus radares superpuestos y sus stats normalizadas por liga (con un disclaimer de que la normalización es v0).

**Trade-off honesto:** La normalización estadística real entre ligas requiere meses de data science. Lo que podemos mostrar hoy es una aproximación visual. Eso ya genera valor para el Director Deportivo que necesita comparar un mediocampista de Ligue 1 con uno de La Liga.

**Cómo agregarlo al prototipo en vivo:** En el perfil del jugador, agregar un botón "Comparar con…" que abre un modal con el radar de ambos superpuesto. Simple, funcional, defendible.

---

### Otros escenarios posibles:

| Sorpresa posible | Pregunta de clarificación | Scope mínimo en prototipo |
|---|---|---|
| "El cliente quiere alertas de lesiones" | ¿Para gestión de riesgo de fichaje o tracking del equipo propio? | Panel de "riesgo físico" en perfil del jugador (historial de lesiones) |
| "Queremos integrar datos de GPS/tracking" | ¿El cliente tiene acceso a esa data? ¿Proveniente de qué proveedor? | Pantalla de "métricas físicas" en perfil, con campos vacíos y nota "requires integration" |
| "El entrenador también quiere acceso" | ¿Qué decisiones específicas tomaría el entrenador con esto? | Segunda vista del mismo perfil con métricas enfocadas en rendimiento semanal |
| "Quieren un módulo de valoración económica" | ¿Valoración propia o comparada con mercado? | Campo "valor estimado ScoutIQ" en perfil basado en comparables del mismo percentil |

---

## Lo que NO hacer en la presentación

- **No improvisar sin clarificar.** Siempre preguntar antes de construir.
- **No prometer sin acotar.** "Podemos hacerlo en V2 con más información" es una respuesta válida y honesta.
- **No sobre-justificar.** Si tomaste una decisión razonable, defenderla en una oración. Los largos monólogos de justificación comunican inseguridad.
- **No construir en vivo sin pensar primero.** Tomarse 60 segundos de silencio para diseñar el approach antes de abrir el editor. El pensamiento visible es parte de la evaluación.
