# HISTORIAS DE USUARIO — ConectaTutor
> Plantilla según la guía de clase (`Apuntes y Notas/clase 1 y 2.docx`): **7 elementos obligatorios**.
> Te dejo **HU-001 completamente resuelta como modelo** y las otras 7 con la estructura marcada.
>
> **Versión individual: escribe solo HU-001 a HU-005.** Las HU-006 a HU-008 déjalas listadas como *backlog priorizado* en el informe, con una línea cada una. Cinco historias bien hechas valen más que ocho a medias, y declarar el backlog demuestra gestión de alcance.

## Los 7 elementos obligatorios
1. **Código identificador** (vincula con el RF de origen y la prioridad)
2. **Nombre**
3. **Descripción**: Como [rol] / Quiero [acción] / Para [beneficio]
4. **Criterios de aceptación** (formato Dado–Cuando–Entonces)
5. **Prioridad** (MoSCoW)
6. **Estimación** (puntos de historia o tallas S/M/L)
7. **Alcance técnico**: Frontend / Backend / Persistencia

---

## HU-001 — Búsqueda de tutores por materia ✅ *(modelo resuelto)*

**Código:** HU-001 · **RF de origen:** RQF009 · **Prioridad:** Must · **Estimación:** M

**Descripción**
> **Como** estudiante solicitante,
> **quiero** buscar tutores filtrando por la materia en la que tengo dificultades,
> **para** encontrar rápidamente a alguien que pueda ayudarme sin depender del voz a voz.

**Criterios de aceptación**

*Escenario 1 — Búsqueda con resultados*
> **Dado que** el solicitante ha iniciado sesión,
> **y** existen tutores activos que ofrecen la materia "Cálculo Diferencial",
> **cuando** selecciona esa materia en el buscador,
> **entonces** el sistema muestra la lista de tutores disponibles,
> **y** cada resultado presenta nombre, tarifa por hora y calificación promedio.

*Escenario 2 — Búsqueda sin resultados*
> **Dado que** el solicitante busca una materia sin tutores registrados,
> **cuando** ejecuta la búsqueda,
> **entonces** el sistema muestra el mensaje "Aún no hay tutores disponibles para esta materia",
> **y** ofrece la opción de explorar materias relacionadas.

*Escenario 3 — Sin sesión iniciada*
> **Dado que** un visitante no ha iniciado sesión,
> **cuando** intenta buscar tutores,
> **entonces** el sistema lo redirige a la pantalla de inicio de sesión.

**Alcance técnico**
- *Frontend:* componente de búsqueda con selector de materia y lista de tarjetas de tutor.
- *Backend:* endpoint `GET /api/tutores?materia=` con filtrado.
- *Persistencia:* consulta a la colección de tutores por materia y estado activo.

---

## HU-002 — Registro con correo institucional
**Código:** HU-002 · **RF:** RQF001, RQF002 · **Prioridad:** Must · **Estimación:** `[ ]`
> **Como** `[ ]`, **quiero** `[ ]`, **para** `[ ]`

**Criterios de aceptación** — piensa al menos 3 escenarios: registro exitoso · correo de dominio no institucional · correo ya registrado.
**Alcance técnico:** Frontend `[ ]` · Backend `[ ]` · Persistencia `[ ]`

---

## HU-003 — Configuración de disponibilidad del tutor
**Código:** HU-003 · **RF:** RQF007 · **Prioridad:** Must
> Escenarios sugeridos: guardar disponibilidad · franja solapada · sin disponibilidad definida (no aparece en búsquedas).

---

## HU-004 — Visualización del perfil público del tutor
**Código:** HU-004 · **RF:** RQF011, RQF018, RQF020 · **Prioridad:** Must
> Escenarios sugeridos: perfil con calificaciones · tutor sin calificaciones aún · datos sensibles ocultos.

---

## HU-005 — Solicitud de sesión de tutoría
**Código:** HU-005 · **RF:** RQF012, RQF013 · **Prioridad:** Must
> Escenarios sugeridos: solicitud exitosa · franja ya ocupada · solicitud sin describir el tema.

---

## HU-006 — Confirmación o rechazo de solicitud por el tutor
**Código:** HU-006 · **RF:** RQF014 · **Prioridad:** Must
> Escenarios sugeridos: aceptación · rechazo con motivo · solicitud expirada.

---

## HU-007 — Consulta de "Mis sesiones"
**Código:** HU-007 · **RF:** RQF015 · **Prioridad:** Must
> Escenarios sugeridos: sesiones en cada estado · usuario sin sesiones · filtro por estado.

---

## HU-008 — Calificación del tutor tras la sesión
**Código:** HU-008 · **RF:** RQF017, RQF018 · **Prioridad:** Must
> Escenarios sugeridos: calificación exitosa y recálculo del promedio · intento de calificar una sesión no finalizada · intento de calificar dos veces la misma sesión.

---

## Consejo de sustentación
Las historias que **más se preguntan** son las de los casos de error. Ten muy claro qué pasa cuando algo sale mal en HU-001, HU-005 y HU-008 — es la diferencia entre "explicación clara" y "explicación confusa" en la rúbrica.
