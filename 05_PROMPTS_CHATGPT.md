# PROMPTS PARA CHATGPT — uso dirigido
> Estrategia: **la IA redacta a partir de TU material, nunca inventa el contenido.**
> Si ChatGPT se inventa una entrevista o unos hallazgos, no vas a poder defenderlo el miércoles y se nota en la sustentación.

## Regla de oro
Cada vez que uses un prompt, **pega tu material real** donde dice `[PEGA AQUÍ...]`. Si no tienes material, no uses el prompt: ve y levanta el dato.

---

## PROMPT 0 — Contexto (pégalo al inicio de la conversación, una sola vez)

```
Eres mi asistente de redacción académica. Estoy en la electiva Desarrollo Web de la
Universidad del Rosario (2 créditos). Desarrollo "ConectaTutor" de forma INDIVIDUAL:
una plataforma web que conecta estudiantes que necesitan refuerzo académico con
estudiantes-tutores de semestres avanzados. Al ser un solo desarrollador, el alcance
está deliberadamente recortado y priorizado con MoSCoW.

Estamos en la Entrega 1, que cubre la Fase 1 del SDLC (Requisitos y Análisis) y la
Fase 2 (Diseño). Se evalúa con esta rúbrica:
- Requerimientos 30% (completos, priorizados con MoSCoW y trazables a la problemática)
- Prototipo UX/UI 35% (alta fidelidad navegable en Figma)
- Sustentación oral 20%
- Informe escrito 15%

Reglas para todas tus respuestas:
1. NO inventes datos, entrevistas, cifras ni hallazgos. Si te falta información, pregúntame.
2. Escribe en español, registro académico pero directo. Sin relleno ni frases motivacionales.
3. Nada de listas de tres elementos por costumbre ni de adjetivos promocionales.
4. Cuando redactes, usa exclusivamente el material que yo te pegue.

Confirma que entendiste y espera mi primer encargo.
```

---

## PROMPT 1 — Sección de problemática

```
Redacta la sección "2. Problemática" de mi informe (máximo 1 página).

Material real de mi proyecto:
[PEGA AQUÍ las dos personas (Ana María Quintero y Daniel Duque) del archivo ConectaTutor.docx]

Estructura que quiero:
a) Contexto del problema en la universidad
b) Por qué las alternativas actuales (monitorías grupales, IA, voz a voz) no lo resuelven
c) Consecuencias para ambos actores

No repitas el enunciado oficial de la línea de proyecto: reescríbelo desde la evidencia
de mis personas.
```

---

## PROMPT 2 — Mapas de empatía

```
A partir de esta descripción de mi persona, construye su mapa de empatía en formato de
tabla con los cuadrantes: Piensa y siente / Ve / Oye / Dice y hace / Dolores / Ganancias.

Usa SOLO lo que está en el texto. Si un cuadrante no tiene respaldo en el material,
escribe "sin evidencia levantada" en lugar de inventar.

[PEGA AQUÍ la persona]
```

---

## PROMPT 3 — Pulir requerimientos (no generarlos)

```
Te voy a pasar mi tabla de requerimientos funcionales. Tu trabajo es:
1. Revisar que cada descripción esté redactada como especificación técnica en tercera
   persona ("El sistema debe...") y sea verificable.
2. Señalar requerimientos ambiguos, duplicados o que en realidad sean dos requerimientos.
3. Señalar si alguna prioridad MoSCoW está mal asignada y por qué.
4. Señalar necesidades de mis personas que NO estén cubiertas por ningún requerimiento.

NO agregues requerimientos nuevos por tu cuenta: solo repórtame los huecos y yo decido.

Mis personas:
[PEGA AQUÍ]

Mi tabla:
[PEGA AQUÍ el contenido de 02_REQUERIMIENTOS.md]
```

---

## PROMPT 4 — Historias de usuario (una por una, no todas de golpe)

```
Ayúdame a completar esta historia de usuario siguiendo los 7 elementos obligatorios de
mi curso: código identificador, nombre, descripción (Como/Quiero/Para), criterios de
aceptación en formato Dado-Cuando-Entonces, prioridad MoSCoW, estimación y alcance
técnico separado en Frontend / Backend / Persistencia.

Aquí tienes una historia YA RESUELTA como modelo de estilo y nivel de detalle:
[PEGA AQUÍ la HU-001 completa del archivo 03_HISTORIAS_USUARIO.md]

Ahora completa esta:
[PEGA AQUÍ la historia que te toca, con lo que ya escribiste tú]

Incluye mínimo un escenario de éxito y dos de error o borde.
```

---

## PROMPT 5 — Matriz de trazabilidad

```
Construye una tabla de trazabilidad con estas columnas:
Necesidad detectada | Persona que la expresa | Requerimiento(s) que la cubren | Historia de usuario

Fuentes:
[PEGA AQUÍ las personas]
[PEGA AQUÍ tu tabla final de requerimientos]
[PEGA AQUÍ tus historias de usuario]

Al final, lístame por separado:
- Necesidades sin requerimiento asociado
- Requerimientos que no responden a ninguna necesidad
```

---

## PROMPT 6 — Revisión final del informe

```
Revisa mi informe como si fueras la profesora que lo va a calificar con esta rúbrica:
- Requerimientos 30%: ¿completos, priorizados con MoSCoW, trazables a la problemática?
- Prototipo 35%: ¿la sección de diseño evidencia alta fidelidad y flujos completos?
- Informe escrito 15%: ¿completo, claro y bien estructurado?

Dime, en orden de gravedad:
1. Qué le falta para nivel alto en cada criterio
2. Qué párrafos están confusos o son relleno
3. Qué 3 preguntas incómodas me haría en la sustentación

No reescribas nada todavía. Solo diagnostica.

[PEGA AQUÍ tu informe]
```

---

## PROMPT 7 — Preparar la sustentación

```
Simula que eres la profesora evaluando mi sustentación de 10 minutos. Hazme 8 preguntas
difíciles sobre las decisiones de mi proyecto, una por una, esperando mi respuesta antes
de la siguiente. Después de cada respuesta dime si fue convincente y qué le faltó.

Enfócate en: por qué prioricé así, por qué estas pantallas y no otras, cómo sé que el
problema existe, qué pasa en los casos de error, y si voy a poder sostener el proyecto
solo durante todo el semestre.

Mi proyecto:
[PEGA AQUÍ el resumen de tu informe]
```

---

## Lo que NO le debes pedir a ChatGPT
- Que invente la entrevista o los hallazgos del levantamiento.
- Que genere 100 requerimientos "para que se vea completo".
- Que escriba las conclusiones sin haberle dado el informe.
- Que diseñe el prototipo. Ese trabajo es tuyo y es el 35%.
