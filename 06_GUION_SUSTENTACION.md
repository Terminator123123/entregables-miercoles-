# GUION DE SUSTENTACIÓN — 10 minutos, individual (20% de la entrega)

> La rúbrica premia *"explicación clara y articulada"*. El criterio de "participación de todo el equipo" no te aplica siendo uno solo — **confírmalo con la profesora**, pero a cambio toda la carga de claridad recae en ti.
>
> **Ventaja de ir solo:** no hay cortes, no hay integrante que se trabe, no hay que coordinar. Una sustentación individual bien ensayada se ve más sólida que tres personas mal repartidas. Aprovéchalo.

---

## Estructura de los 10 minutos

| Bloque | Tiempo | Contenido |
|---|---|---|
| 1. Problemática y levantamiento | 2 min | Qué problema, cómo lo investigaste, qué encontraste |
| 2. Personas y requerimientos | 2.5 min | Ana y Daniel, RF/RNF, MoSCoW, trazabilidad |
| 3. **Demo del prototipo en vivo** | 4 min | Flujo A completo, luego Flujo B |
| 4. Cierre y próximos pasos | 1.5 min | Qué sigue en la Fase 3 y cómo organizaste el trabajo |

Guarda 30 segundos de colchón. Siempre se va algo.

---

## Bloque 1 — Problemática (2 min)
- Abre con **una frase concreta de la evidencia**, no con una generalidad: *"Ana nos contó que cuando se acerca un parcial y todavía tiene dudas, lo que siente es ansiedad."*
- Explica la técnica: **5 Porqués**, y por qué esa y no una encuesta cerrada.
- Cierra con la causa raíz y la pregunta HMW general.

## Bloque 2 — Requerimientos (2.5 min)
- Las dos personas en 30 segundos cada una. No leas la ficha completa.
- Muestra la tabla en pantalla y explica **3 ejemplos**, no los 24.
- **Lo que importa:** por qué esos son *Must*. Ejemplo: *"RQF020, proteger los datos de contacto, es Must porque el miedo de Daniel a compartir su número fue lo que apareció en la entrevista. Si no lo resuelvo, no hay tutores en la plataforma."*
- Menciona qué dejaste en **Won't** (chat interno, pagos) y por qué. Eso demuestra criterio, no falta de trabajo — y siendo uno solo, demostrar criterio de alcance juega a tu favor.

## Bloque 3 — Demo (4 min) ← el bloque que define la nota
- **Prototipo ya abierto en modo Presentación antes de empezar.** No busques el link en vivo.
- Narra como usuario, no como diseñador: *"Ana entra, busca Cálculo Diferencial, compara tres tutores..."*
- Recorre el **Flujo A completo** sin saltarte pantallas.
- Muestra **un estado vacío o de error**. Es lo que separa un prototipo pensado de uno bonito.
- Termina con el **Flujo B** (calificación).
- **Plan B obligatorio:** capturas de las 5 pantallas en un PDF, por si falla el internet o el proyector.

## Bloque 4 — Cierre (1.5 min)
- Qué sigue: maquetación HTML/CSS de estas pantallas → JavaScript → React → API Express y MongoDB.
- **Di cómo te organizaste solo:** tablero Kanban, repositorio, y qué recortaste conscientemente para que el alcance fuera viable. No lo presentes como excusa; preséntalo como decisión de gestión.

---

## Preguntas que probablemente te hagan

| Pregunta | Cómo responderla |
|---|---|
| **¿Vas a poder solo con todo el semestre?** | *(La más probable.)* Responde con el plan, no con optimismo: qué recortaste, qué priorizaste con MoSCoW, y cuál es el mínimo funcional que garantizas para las Entregas 2 y 3. Ten un número: "5 pantallas, 14 requerimientos Must, un CRUD principal". |
| ¿Por qué esta priorización? | Porque los Must son los que hacen funcionar el ciclo básico: buscar → solicitar → confirmar → calificar. Sin uno de ellos el producto no resuelve el problema. |
| ¿Cómo sabes que este problema existe? | Por la entrevista con los 5 Porqués y por las necesidades que aparecieron en ambas personas. *(Ten la evidencia a mano.)* |
| ¿Por qué solo 5 pantallas? | Porque cubren los dos flujos centrales. Los demás requerimientos están documentados y priorizados para fases siguientes. |
| ¿Qué pasa si un tutor no responde una solicitud? | **Define la respuesta ANTES de la sustentación.** Es el hueco más probable de tu diseño. |
| ¿Por qué dejaste el pago fuera? | Está fuera del stack del curso y no es necesario para validar el problema central: la conexión entre estudiante y tutor. |
| ¿Cómo proteges los datos del tutor? | RQF020 y RQNF005: el perfil público no expone teléfono ni documento, y las vistas privadas requieren sesión activa. |

---

## Reglas
1. **Ensaya cronometrado el martes.** No "repasar": de pie, en voz alta, con reloj. Solo, el ensayo es lo único que te da fluidez.
2. Nada de leer diapositivas. Las diapositivas son imágenes y títulos.
3. Ten el informe abierto en otra pestaña para poder señalar tablas cuando te pregunten.
4. Llega 10 minutos antes y prueba proyector y link de Figma.
5. Si algo del prototipo no quedó, **dilo tú antes de que lo pregunten** y explica por qué lo priorizaste así. Suena a criterio; que te lo descubran suena a descuido.
