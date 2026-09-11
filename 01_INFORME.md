# ESQUELETO DEL INFORME — ENTREGA 1
> Llena cada sección. Lo que está entre `[...]` lo escribes tú o lo genera ChatGPT con los prompts de `05_PROMPTS_CHATGPT.md`.
> Extensión objetivo: **10–14 páginas** con anexos. Más largo no da más nota; desordenado sí quita.

---

## Portada
- Universidad del Rosario — Escuela de Ingeniería, Ciencia y Tecnología
- Electiva Desarrollo Web (11310046) — Prof. Tatiana Cabrera Vargas
- **Proyecto: ConectaTutor — Banco de tutorías entre estudiantes** (Línea 2)
- Entrega 1 — Fase 1 (Requisitos y Análisis) y Fase 2 (Diseño)
- Integrantes y roles · Fecha: 16 de septiembre de 2026

> ⚠️ **Estructura actualizada** según tus notas de clase (`07_ESTRUCTURA_PROFE.md`). La profesora organiza el informe en **tres fases**: Análisis, Planeación y Diseño. Respeta esos nombres.

## 1. Introducción
`[½ página]` Qué es el documento, qué fases cubre y cómo está organizado.

---

# FASE 1 — ANÁLISIS *(Empatizar)*

## 2. Necesidad y problema
`[1 página]` El problema contado **desde tu evidencia**, no copiado de los lineamientos.

## 3. Metodología
`[½ página]` Design Thinking (empatizar, definir, idear, prototipar, evaluar) articulado con el SDLC.

## 4. Herramienta usada en la fase
`[1 página]` **Los 5 Porqués**: por qué esta técnica y no una encuesta cerrada, a quién entrevistaste, las cadenas de indagación y la causa raíz.

## 5. Stakeholders
`[½ página]` Tabla de interesados con interés e influencia → **tabla lista en `07_ESTRUCTURA_PROFE.md`**

## 6. Usuarios (personas)
`[1.5 páginas]` Ana María Quintero y Daniel Duque → ya escritas en `Apuntes y Notas/ConectaTutor.docx`

---

# FASE 2 — PLANEACIÓN *(Definir + Idear)*

## 7. Herramientas usadas en la fase
`[½ página]` Mapa de empatía · How Might We · lluvia de ideas · priorización MoSCoW.

## 8. Mapas de empatía
`[1 página]` Uno por persona: Piensa y siente / Ve / Oye / Dice y hace / Dolores / Ganancias.

## 9. Definición del problema (HMW)
> **Pregunta general:** ¿Cómo podríamos conectar de manera rápida, segura y confiable a estudiantes de la Universidad del Rosario que necesitan refuerzo académico con estudiantes-tutores calificados, facilitando la búsqueda, la programación, el seguimiento y la evaluación de las tutorías?

## 10. Conclusiones de la fase
`[½ página]` El problema ya acotado y la solución elegida.

## 11. Requisitos
`[3 páginas]` → **contenido en `02_REQUERIMIENTOS.md`**
### 11.1 Actores · 11.2 Funcionales (RQF0XX) · 11.3 No funcionales (RQNF0XX)
### 11.4 Priorización MoSCoW
### 11.5 **Matriz de trazabilidad** ← lo que separa nivel medio de nivel alto
### 11.6 Restricciones

## 12. Historias de usuario
`[2 páginas]` HU-001 a HU-005 completas con los 7 elementos → `03_HISTORIAS_USUARIO.md`
### 12.1 Backlog priorizado (HU-006 a HU-008, una línea cada una)

## 13. Diagrama de solución
`[½ página]` Los módulos M1–M6 y sus relaciones → **estructura en `07_ESTRUCTURA_PROFE.md`**

## 14. Diagrama de flujo de la solución
`[½ página]` El proceso con decisiones, desde el ingreso hasta la calificación.

---

# FASE 3 — DISEÑO *(Prototipar)*

## 15. Prototipos de baja fidelidad
`[1 página]` Fotos de tus wireframes a mano del sábado.

## 16. UI Kit — Atomic Design
`[1 página]` Átomos, moléculas y organismos, con la captura de la página "UI Kit" de Figma.
> Recuerda: **el botón es un átomo.**

## 17. Guía de estilo
`[½ página]` Paleta, tipografía, espaciado.

## 18. Mapa de navegación
`[½ página]` Estructura jerárquica del sitio.

## 19. User flow
`[½ página]` El camino para conseguir una tutoría, con decisiones. **No es lo mismo que el mapa de navegación.**

## 20. Prototipos de alta fidelidad
`[2–3 páginas]` Capturas de las 9 pantallas móviles + 3 de escritorio + **enlace público a Figma**.
### 20.1 Cobertura de módulos
`[Tabla: cada módulo M1–M6 → qué pantalla lo representa. Demuestra que NO falta ninguno.]`
### 20.2 Enfoque mobile first
`[Justifícalo: Ana busca tutor desde el celular entre clases.]`
### 20.3 Decisiones de UX justificadas
`[Cada decisión → a qué necesidad de Ana o Daniel responde. Oro para la sustentación.]`

## 21. Diagrama de clases
`[½ página]` Del módulo **M4 Sesiones**: Usuario, Solicitante, Tutor, Sesion, Calificacion, Materia.

## 22. Arquitectura de base de datos
`[1 página]` ⚠️ **NoSQL, no relacional.** Modelo de documentos de MongoDB → colecciones en `07_ESTRUCTURA_PROFE.md`.
Justifica por qué NoSQL: esquema flexible, estructuras anidadas (disponibilidad del tutor), y es el stack del curso.

## 23. Evaluación de usabilidad
`[1.5 páginas]` → **contenido en `08_METRICAS_SUS.md`**
### 23.1 Métricas definidas
Tasa de éxito · tiempo por tarea · tasa de error y clics perdidos · tiempo de respuesta · mapa de calor
### 23.2 Test SUS — instrumento y método
### 23.3 Resultados con 3 participantes
### 23.4 **Hallazgos y cambios aplicados al prototipo** ← lo más valioso de todo el informe

---

## 24. Gestión del proyecto
`[½ página]`
- **Modalidad:** desarrollo individual. Asumo los roles de análisis, diseño UX/UI, desarrollo y QA. *(Decláralo, no lo escondas.)*
- **Justificación del alcance:** la priorización MoSCoW responde a la capacidad de un desarrollador. Preséntalo como gestión, no como limitación.
- Tablero Kanban (Backlog / En progreso / Revisión / Terminadas) + enlace y capturas de GitHub

## 25. Conclusiones y próximos pasos
`[½ página]` Lo que sigue: **codificar → testear → implementar** (Fases 3, 4 y 5 del SDLC).

## Anexos
- Anexo 1 — Requisitos funcionales (formato oficial del profe)
- Anexo 2 — Requisitos no funcionales (formato oficial del profe)
- Anexo 3 — Evidencia del levantamiento (5 Porqués)
- Anexo 4 — Capturas del prototipo

---

## Checklist de entrega en e-aulas
- [ ] Informe en **PDF** (no .docx suelto)
- [ ] **Enlace al prototipo de Figma** con permiso de visualización público
- [ ] **Enlace al repositorio de GitHub**
- [ ] Todo cargado en el enlace de e-aulas, antes de la hora límite
