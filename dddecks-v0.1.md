# DDDecks

| Campo | Valor |
|---|---|
| Versión | 0.1 |
| Estado | Draft |
| Creado | 2026-09-10 10:24:51 CEST (Europe/Madrid) |
| Actualizado | 2026-09-10 15:30:55 CEST (Europe/Madrid) |
| Documento relacionado | Especificación resumida. Véase [Anexo DDDecks v0.1](dddecks-v0.1-annex.md) para el desarrollo completo. |

## Propuesta

**DDDecks** es un *framework de frameworks*: un meta-framework adaptativo para elegir métodos de producto y software según una **pregunta**, su incertidumbre, el contexto y la evidencia disponible. Es una propuesta conceptual pendiente de contraste con el estado del arte; no se presenta como académicamente validada ni como original.

> **Nota de nomenclatura:** DDDecks no debe confundirse con DDD (*Domain-Driven Design*), una disciplina de diseño de software distinta.

DDDecks evita el *process cargo cult*: no prescribe una secuencia fija de fases, ceremonias, técnicas ni artefactos. Su pregunta guía es: **¿qué necesitamos saber para tomar la siguiente decisión con mejor fundamento?**

## Dos mapas, dos objetos

| Objeto | Cómo se orienta |
|---|---|
| Producto | Roadmap, outcomes, capabilities y milestones. |
| Proceso de producto | Mapa o grafo de Questions y Checkpoints de decisión. |

La **Question** es la unidad que orienta el proceso. Un **Checkpoint** no es una pregunta: es el momento explícito de evaluar si la evidencia reunida basta para decidir. Las Questions pueden formar un grafo, depender unas de otras y reabrirse; esto no convierte DDDecks en un modelo Stage-Gate.

## Modelo operativo

Ante una Question o incertidumbre relevante, el equipo diverge entre técnicas posibles de diversas disciplinas y converge en un **Deck** pequeño y contextual. Juega una o varias técnicas, interpreta la evidencia y vuelve a decidir: continuar, cambiar, investigar más o parar. El Deck puede modificarse durante la partida.

El **Double Diamond** explica la divergencia y convergencia al seleccionar métodos. El **Deck** explica la selección contextual y la adaptación secuencial en función de la evidencia.

```text
Question → incertidumbre → divergir técnicas → Deck → Plays → Evidence
                                                       ↓
                                      Checkpoint → Decision → siguiente pregunta/acción
```

## Vocabulario

| Término | Significado |
|---|---|
| Collection / Library | Todas las técnicas conocidas por el equipo o la organización. |
| Deck | Subconjunto de técnicas apropiado para un reto y contexto concretos. |
| Card | Tipo de técnica: entrevista, prototipo, POC, spike, test, analítica… |
| Play | Ejecución concreta de una Card. |
| Evidence | Resultado informativo de una Play. |
| Checkpoint | Evaluación de la suficiencia de evidencia para una decisión. |
| Decision | Continuar, cambiar, investigar más o parar. |

**Card ≠ Play.** “Entrevista” es una Card; “entrevistar a Olga mientras prepara un álbum” es una Play. Una misma Card puede jugarse varias veces y distintas Cards pueden combinarse hasta alcanzar evidencia suficiente.

## Principios constitucionales

1. **Progreso = reducción de incertidumbre relevante y mejor capacidad de decisión**, no producción de artefactos.
2. **Ningún método, artefacto, ceremonia o técnica es obligatorio meramente porque DDDecks u otro framework lo contenga.** Debe justificarse por la Question, el contexto y la decisión que habilita.
3. La prospección exploratoria puede preceder a una hipótesis; descubrir no es lo mismo que validar.
4. POC, PRD, entrevistas, analytics, inspección de código, spikes y tests son Cards, Plays o artefactos potenciales; no fases obligatorias.
5. DDDecks puede coexistir con JTBD, Design Thinking, Double Diamond, Lean Startup, Continuous Discovery, Scrum, Kanban, DORA y prácticas de ingeniería, sin exigir adoptar ninguno entero.

## Límites y protección contra el cargo cult

DDDecks no sustituye criterio profesional, estrategia, responsabilidad de decisión ni investigación rigurosa. No ofrece una lista universal de checkpoints ni un catálogo definitivo de técnicas. Rechaza como anti-patrones: rituales sin pregunta, métricas sin decisión, artefactos como prueba de progreso, Decks inmutables, convertir toda incertidumbre en una ceremonia y declarar éxito por aplicar el proceso.

Las familias de Questions —desirability, viability, feasibility, usability, evidence/measurement y delivery/operations— pueden ayudar a explorar, pero ninguna debe ser obligatoria por ceremonia.

---

Este documento es la especificación de una página conceptual. Para definiciones operativas, ejemplos, gobernanza, riesgos e hipótesis a validar, consulte el [Anexo DDDecks v0.1](dddecks-v0.1-annex.md).
