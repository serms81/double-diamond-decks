# Anexo — DDDecks

| Campo | Valor |
|---|---|
| Versión | 0.2 |
| Estado | Draft |
| Creado | 2026-09-10 18:59:43 CEST (Europe/Madrid) |
| Actualizado | 2026-09-10 18:59:43 CEST (Europe/Madrid) |
| Documento relacionado | Anexo detallado del [Framework](framework.md), que contiene la especificación resumida. |

## 1. Propósito y motivación

DDDecks es una propuesta conceptual de *framework de frameworks* para seleccionar y adaptar métodos de producto y software. Parte de una observación: los equipos suelen heredar ceremonias, artefactos y métodos completos aunque la incertidumbre concreta no los justifique. El resultado puede ser *process cargo cult*: actividad visible sin aprendizaje proporcional ni decisiones mejores.

DDDecks no afirma ser académicamente validado ni original. Antes de sostener que es útil o generalizable, debe contrastarse con el estado del arte y con práctica observada. Su aportación provisional es un lenguaje operacional para elegir instrumentos de forma explícita: **pregunta → evidencia → decisión**.

> **Nota de nomenclatura:** DDDecks no debe confundirse con DDD (*Domain-Driven Design*), una disciplina de diseño de software distinta.

## 2. Qué organiza DDDecks

DDDecks distingue dos mapas complementarios:

| Mapa | Finalidad |
|---|---|
| Producto | Expresar dirección y compromiso: roadmap, outcomes, capabilities y milestones. |
| Proceso de producto | Gestionar aprendizaje y decisiones: grafo de Questions y Checkpoints. |

Una capability o milestone puede requerir varias Questions; una Question puede afectar a varias partes del roadmap. DDDecks no convierte el proceso en una cadena lineal ni en Stage-Gate. Las Questions pueden tener dependencias, bifurcarse, quedar latentes o reabrirse cuando cambia el contexto o la evidencia.

## 3. Ontología mínima

```text
Question → Uncertainty → Deck → Card ──instantiated as──► Play ──produces──► Evidence
       ↖──────────────── contexto / metagame ──────────────────────┬───────────┘
Artifact ──input to──► Play; Play ──produces / modifies──► Artifact; Artifact ──may contain──► Evidence
Evidence ──evaluated at──► Checkpoint ──► Decision
```

| Elemento | Definición operativa |
|---|---|
| **Question** | Pregunta cuya respuesta importa para una decisión. Es la unidad que orienta el proceso. |
| **Uncertainty** | Lo que no se sabe —o no se sabe con suficiente confianza— sobre la Question. |
| **Collection / Library** | Universo de técnicas conocidas, accesibles o aprendibles por el equipo. |
| **Context / metagame** | Restricciones y condiciones: objetivo, usuarios, plazo, riesgo, coste, capacidades, regulación, arquitectura y evidencia previa. |
| **Deck** | Pequeño subconjunto contextual de Cards seleccionadas para reducir una incertidumbre. |
| **Card** | Método, técnica o capacidad reutilizable susceptible de ejecutarse. Ejemplos: entrevista, prototipado, analytics, inspección de código, spike, test. |
| **Play** | Instancia concreta de una Card, con participantes, alcance, hipótesis o intención, fecha y criterio de lectura. |
| **Artifact** | Objeto persistente utilizado, producido o modificado por una o varias Plays. Puede ser input de una Play y contener Evidence sin ser necesariamente Evidence. Ejemplos: PRD, Prototype, especificación o informe. |
| **Evidence** | Resultado informativo de una Play: cualitativo, cuantitativo, técnico, operacional o mixto. |
| **Checkpoint** | Momento para evaluar si la evidencia basta para decidir; no es la Question en sí. |
| **Decision** | Continuar, cambiar, investigar más o parar. Debe registrar razonamiento y consecuencias. |

**Card no equivale a Play.** “Entrevista” es una Card. “Entrevistar a Olga mientras prepara un álbum anual” es una Play. Se puede jugar la misma Card muchas veces, o combinar Cards, sin que cada repetición deba crear una fase nueva.

**Card, Play, Artifact y Evidence no son una cadena lineal.** Un Artifact puede preceder a una Play como input, persistir y cambiar entre varias Plays. Una Play puede producir Evidence directamente, producir o modificar un Artifact, o ambas cosas. El Artifact puede contener Evidence, pero no es Evidence automáticamente. En particular: `Prototyping → Card`, una ejecución concreta de prototipado → Play, `Prototype → Artifact`; un PRD es Artifact, no Card.

## 4. Ciclo operativo

1. Relacionar una Question con una decisión posible, el outcome o capability afectado y la incertidumbre relevante.
2. Hacer explícito el contexto y la evidencia disponible; decidir si conviene exploración, validación o ambas.
3. Divergir: considerar Cards de la Collection, procedentes de cualquier disciplina o framework útil.
4. Converger: construir un Deck pequeño, secuenciado solo cuando convenga, y definir Plays iniciales con señales de lectura.
5. Ejecutar Plays; usar, producir o modificar Artifacts cuando corresponda; capturar Evidence, incluyendo calidad, límites y contradicciones.
6. Convocar un Checkpoint cuando haya nueva evidencia relevante, una fecha de decisión, un umbral acordado o un cambio de contexto.
7. Decidir: continuar, cambiar, investigar más o parar. Actualizar el grafo de Questions y adaptar el Deck.

No todas las Questions requieren el mismo número de Plays, ni todos los Checkpoints necesitan una ceremonia formal.

## 5. Construcción y adaptación de Decks

Un Deck no es una plantilla fija ni un backlog de actividades. Es una apuesta temporal sobre qué Cards producirán evidencia suficiente con un coste aceptable. Puede contener una sola Card o varias; por ejemplo, prospección, prototipado y analítica posterior. Los Artifacts pueden ser inputs, resultados o soportes durables de esas Plays, pero no sustituyen la justificación de una Card.

Para elegir Cards, el equipo puede ponderar los siguientes criterios; no constituyen una fórmula obligatoria:

| Criterio | Pregunta orientativa |
|---|---|
| Coste | ¿Qué consume en tiempo, dinero, atención y oportunidad? |
| Velocidad | ¿Cuándo estará disponible una señal útil? |
| Calidad y relevancia | ¿La evidencia responde realmente a esta Question? |
| Riesgo | ¿Qué daño puede causar una respuesta falsa, una exposición o un fallo? |
| Reversibilidad | ¿Podemos corregir la decisión si la evidencia resulta insuficiente? |

Un Deck debe revisarse tras evidencia nueva. Persistir en una Card por costumbre, o congelar el Deck para “cumplir el plan”, son señales de cargo cult.

## 6. Evidencia, exploración y validación

La evidencia puede ser:

- Cualitativa: entrevistas, observación, diarios, soporte.
- Cuantitativa: analítica de comportamiento, experimentos, cohortes, métricas de calidad.
- Técnica: resultados de spikes, benchmarks, tests automatizados e inspección de código.
- Operacional: simulación de soporte, ensayo de despliegue, SLO, observabilidad, DORA.
- Documental o estratégica: contenido relevante de un PRD, análisis de restricciones o investigación de mercado.

Un PRD, un Prototype o un informe pueden contener Evidence, pero su existencia no demuestra por sí misma que haya aprendizaje o una decisión mejor fundamentada.

La **prospección exploratoria** busca descubrir lenguaje, necesidades, posibilidades o Questions que aún no existen. Puede preceder a una hipótesis. La **validación** contrasta una hipótesis o una afirmación definida. Confundirlas lleva a pedir “validación” antes de saber qué merece ser validado, o a presentar hallazgos exploratorios como prueba concluyente.

La evidencia no es automáticamente buena por ser numérica, técnica o abundante. Debe juzgarse por su relevancia, trazabilidad, calidad, sesgos, límites y por la decisión que puede soportar.

## 7. Questions y Checkpoints

No existe una lista universal obligatoria de Checkpoints. Puede existir una biblioteca de Questions por familias para facilitar el descubrimiento:

| Familia | Ejemplos |
|---|---|
| Desirability | ¿Para quién es importante este problema? |
| Viability | ¿El valor y el modelo sostienen la inversión? |
| Feasibility | ¿Podemos construirlo con seguridad, coste y plazo aceptables? |
| Usability | ¿Las personas lo entienden y completan la tarea? |
| Evidence / measurement | ¿Qué señal indicará avance o daño? |
| Delivery / operations | ¿Podemos lanzar, operar, mantener y soportar el cambio? |

Las familias no son ceremonias ni una lista de cumplimiento. Un Checkpoint evalúa, para una decisión concreta: qué evidencia tenemos, qué evidencia falta, qué umbral de confianza o riesgo es aceptable, y qué coste tiene esperar o actuar.

## 8. Relación con otros frameworks

DDDecks puede tomar Cards de JTBD, Design Thinking, Double Diamond, Lean Startup, Continuous Discovery, Scrum, Kanban, DORA y prácticas de ingeniería. No obliga a adoptar la gobernanza, cadencia, vocabulario o todas las prácticas del framework de origen.

El Double Diamond aporta la idea de divergir y convergir al elegir métodos. La metáfora del Deck aporta selección contextual, combinatoria y adaptación basada en Evidence. DDDecks no reemplaza esos marcos: sirve para razonar cuándo y cómo usar partes de ellos.

## 9. Ejemplos

### Album Planner (ilustrativo)

Una capability del producto podría ser ayudar a familias a convertir fotos dispersas en un álbum anual. La Question inicial no tiene por qué ser “¿construimos el editor?”, sino: **¿qué momento del proceso de crear un álbum genera más abandono y para quién?**

Un primer Deck podría incluir Cards de observación contextual, entrevista y prototipado. Una Play sería entrevistar a Olga mientras prepara su álbum anual, observando decisiones, interrupciones y material que descarta. La evidencia puede revelar que la selección de fotos, no el diseño, es el principal bloqueo. Una Play posterior de prototipado puede producir un Prototype de selección asistida como Artifact; las observaciones sobre su uso serían Evidence. En un Checkpoint, el equipo puede decidir investigar más segmentos, cambiar la capability priorizada o adaptar el Deck. No se ha convertido esta secuencia en una especificación de Album Planner: solo ilustra la unidad Question–Evidence–Decision.

### Riesgo técnico

Para la Question “¿puede el motor de sincronización soportar edición sin conexión sin degradar datos?”, un Deck podría contener un spike, tests de conflicto y revisión de arquitectura. Las Plays pueden producir una POC como Artifact y Evidence técnica sobre sus límites. El Checkpoint evalúa cobertura de escenarios, límites conocidos y reversibilidad antes de comprometer una milestone; no exige hacer entrevistas ni un PRD si no añaden evidencia útil.

## 10. Anti-patrones y cargo cult

| Anti-patrón | Corrección DDDecks |
|---|---|
| Ceremonia heredada sin pregunta | Identificar la Question y decisión; eliminar o rediseñar la actividad si no las sirve. |
| Artefacto como señal de progreso | Evaluar reducción de incertidumbre y decisión habilitada. |
| “Cinco entrevistas” como receta | Justificar cada Play y determinar suficiencia por evidencia, no por cuota. |
| Deck fijo | Revisarlo tras nueva evidencia o cambio de contexto. |
| Todas las familias como checklist | Usar solo Questions pertinentes. |
| Convertir Checkpoints en gates universales | Mantenerlos contextuales, reversibles cuando sea posible y orientados a decisiones reales. |
| Adoptar un framework entero para usar una técnica | Tomar la Card necesaria y conservar el criterio contextual. |

## 11. Gobernanza mínima

DDDecks requiere menos burocracia, no ausencia de disciplina. Como mínimo, cada iniciativa relevante debería poder hacer trazable: Question, decisión afectada, contexto, Deck inicial, Cards, Plays, Artifacts relevantes, Evidence, Checkpoints y Decision. Deben estar claras las personas responsables de decidir y de aceptar el riesgo.

La Collection necesita mantenimiento ligero: documentar Cards conocidas, condiciones de uso, costes aproximados, limitaciones y ejemplos. No debe transformarse en una taxonomía exhaustiva que frene el trabajo. Conviene revisar periódicamente decisiones pasadas para aprender qué Cards aportaron señal útil y dónde se produjeron sesgos o desperdicio.

## 12. Qué no prescribe DDDecks

DDDecks no prescribe:

- fases, sprints, ceremonias, roles, cadencias o artefactos obligatorios;
- número universal de entrevistas, tests, métricas, prototipos o Checkpoints;
- una secuencia lineal entre desirability, viability, feasibility, usability y operations;
- umbrales de evidencia idénticos para decisiones reversibles e irreversibles;
- un catálogo cerrado de Cards ni la adopción completa de frameworks de origen;
- la estrategia de producto, la responsabilidad ejecutiva ni el juicio profesional.

**Regla constitucional:** ningún método, artefacto, ceremonia o técnica es obligatorio meramente porque DDDecks u otro framework lo contenga. Su uso debe justificarse por la Question, el contexto, el coste y la decisión que permitirá tomar.

## 13. Límites del modelo

DDDecks puede introducir sobreanálisis, lenguaje excesivo o una falsa sensación de rigor. No elimina desacuerdos de poder, falta de acceso a usuarios, restricciones legales, dependencia de terceros ni incertidumbre irreducible. Un equipo sin experiencia puede seleccionar Cards débiles o interpretar mal la Evidence. En emergencias, la velocidad puede obligar a decisiones con evidencia limitada; DDDecks debe hacer explícito ese riesgo, no pretender que desaparece.

## 14. Hipótesis de DDDecks que deben validarse

Antes de proclamar DDDecks útil o generalizable, deberían someterse a contraste al menos estas hipótesis:

1. Organizar trabajo por Questions y decisiones mejora la calidad o trazabilidad de decisiones frente a organizarlo solo por actividades o entregables.
2. Construir Decks pequeños y adaptables reduce esfuerzo desperdiciado sin aumentar riesgos relevantes.
3. Separar Cards de Plays evita recetas mecánicas y mejora la elección de técnicas.
4. La distinción exploración–validación reduce hipótesis prematuras y mejora el descubrimiento de problemas reales.
5. El modelo puede convivir con distintos contextos —producto nuevo, plataforma, mantenimiento, organizaciones reguladas— sin convertirse en otra capa burocrática.
6. Las mejoras observadas no se explican únicamente por equipos más maduros, más tiempo o mayor atención de liderazgo.

El contraste debería incluir revisión de literatura y marcos existentes, estudios de caso comparables, definición de señales de éxito y aprendizaje sobre casos donde DDDecks no aporte valor.

## 15. Preguntas abiertas para v0.2

1. ¿Qué representación mínima del grafo de Questions permite trazabilidad sin burocracia?
2. ¿Cómo expresar confianza, coste de error y reversibilidad sin crear una puntuación engañosamente precisa?
3. ¿Qué metadatos mínimos debe tener una Card en la Collection y cómo distinguirlos de los de un Artifact?
4. ¿Cuándo una Decision debe ser explícita y registrada, y cuándo basta una decisión tácita de bajo riesgo?
5. ¿Qué patrones de Deck funcionan en discovery, delivery, operaciones y deuda técnica?
6. ¿Cómo medir “reducción de incertidumbre relevante” de forma útil y resistente al gaming?
7. ¿Dónde se solapa DDDecks con marcos existentes y qué terminología conviene conservar o cambiar tras el contraste?

---

Este anexo es un borrador de trabajo. Su evolución debe basarse en evidencia, no en la defensa del propio modelo.
