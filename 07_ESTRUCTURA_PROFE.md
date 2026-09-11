# ESTRUCTURA QUE PIDE LA PROFESORA — tus notas de clase, ordenadas

> Reconstruido de tus apuntes. **Esto manda sobre los lineamientos en PDF**: es más específico y es lo que ella va a buscar.
> Marca ✅ lo que ya tienes, ⬜ lo que falta.

---

## FASE 1 — ANÁLISIS *(Design Thinking: Empatizar)*

| Entregable | Estado | Dónde está / qué hacer |
|---|---|---|
| Necesidad y problema | ⬜ | Sección 2 del informe |
| Metodología | ⬜ | Declarar: Design Thinking + SDLC |
| **Herramienta usada en la fase** | ✅ | **5 Porqués** — ya la aplicaste (`Empatizar_5Porques...docx`) |
| **Stakeholders** | ⬜ | **Te falta.** Ver tabla abajo |
| Personas / usuarios | ✅ | Ana María y Daniel, en `ConectaTutor.docx` |

### Stakeholders de ConectaTutor (borrador para que ajustes)
| Stakeholder | Interés | Influencia |
|---|---|---|
| Estudiante solicitante | Encontrar apoyo académico confiable y a tiempo | Alta — usuario final |
| Estudiante tutor | Ingresos, visibilidad y seguridad | Alta — usuario final |
| Universidad del Rosario | Retención académica, calidad educativa | Media — valida el uso institucional |
| Decanatura / Bienestar | Complemento a las monitorías oficiales | Media |
| Administrador de la plataforma | Verificar tutores, moderar contenido | Alta — operación |
| Docentes | Referencia de apoyo para sus estudiantes | Baja |

---

## FASE 2 — PLANEACIÓN *(Design Thinking: Definir + Idear)*

| Entregable | Estado | Nota |
|---|---|---|
| Herramientas usadas en la fase | ⬜ | Mapa de empatía, HMW (*How Might We*), lluvia de ideas, MoSCoW |
| Conclusiones de la fase | ⬜ | Cierre de Definir: cuál es el problema ya acotado |
| Usuarios | ✅ | Ana María + Daniel |
| **Requisitos funcionales** | ✅ | `02_REQUERIMIENTOS.md` |
| **Historias de usuario** | 🟡 | `03_HISTORIAS_USUARIO.md` — falta escribirlas |
| **Diagrama de solución** | ⬜ | **Te falta.** Ver abajo |
| **Diagrama de flujo de la solución** | ⬜ | **Te falta.** Ver abajo |

### Diagrama de solución (qué es)
Vista de **módulos**: las cajas de tu sistema y cómo se relacionan. No es código, es arquitectura funcional.
```
                    ┌─────────────────────┐
                    │   M1 Autenticación  │
                    │  (registro, login)  │
                    └──────────┬──────────┘
                               │
        ┌──────────────────────┼──────────────────────┐
        │                      │                      │
┌───────▼────────┐   ┌─────────▼────────┐   ┌─────────▼────────┐
│  M2 Perfiles   │   │ M3 Búsqueda y    │   │ M6 Administración│
│ (solicitante / │◄──┤    catálogo      │   │ (verificar tutor)│
│     tutor)     │   └─────────┬────────┘   └──────────────────┘
└───────┬────────┘             │
        │              ┌───────▼────────┐
        └─────────────►│  M4 Sesiones   │
                       │ (solicitar,    │
                       │  confirmar)    │
                       └───────┬────────┘
                               │
                       ┌───────▼────────┐
                       │M5 Calificaciones│
                       └────────────────┘
```
Pásalo a limpio en **draw.io o Figma**. Este ASCII es solo para que entiendas la forma.

### Diagrama de flujo de la solución (qué es)
El **recorrido del proceso** con decisiones (rombos). Distinto del diagrama de solución. Hazlo del proceso central:
`Ingreso → ¿tiene cuenta? → Buscar tutor → ¿hay resultados? → Ver perfil → Solicitar sesión → ¿tutor acepta? → Sesión realizada → Calificar → Fin`

---

## FASE 3 — DISEÑO *(Design Thinking: Prototipar)*

**Herramienta: Figma.**

| Entregable | Estado | Nota |
|---|---|---|
| Prototipos de **baja** fidelidad | ⬜ | Wireframes |
| Prototipos de **alta** fidelidad | ⬜ | **Deben cubrir TODOS los módulos** ← crítico |
| **Mapa de navegación** | ⬜ | Estructura jerárquica del sitio: qué pantalla cuelga de cuál |
| **User flow** | ⬜ | El camino del usuario para lograr una tarea. **No es lo mismo que el mapa de navegación** |
| **UI Kit con Atomic Design** | ⬜ | Átomos, moléculas, organismos |
| **Diagrama de clases** | ⬜ | Un módulo del sistema modelado en clases |
| **Diagrama de arquitectura de BD** | ⬜ | ⚠️ Ver aviso abajo |
| Mobile → tablet → desktop | ⬜ | **Mobile first** |

### ⚠️ Atomic Design — una corrección a tus apuntes
Anotaste dos versiones distintas. La correcta es:

| Nivel | Qué es | Ejemplo en ConectaTutor |
|---|---|---|
| **Átomo** | La mínima unidad indivisible | Botón, input, label, ícono, estrella |
| **Molécula** | Varios átomos juntos con una función | Barra de búsqueda (input + botón), campo de formulario (label + input + mensaje de error) |
| **Organismo** | Sección completa y autónoma | Navbar, tarjeta de tutor completa, listado de resultados, formulario de solicitud |

**Un botón es un átomo, no una molécula.** Lo tienes al revés en una línea de los apuntes; si lo dices así en la sustentación te lo corrigen.

### ⚠️ Base de datos: NO relacional
Tus apuntes dicen "diagrama de arquitectura de BD relacional" y luego "la sugerencia es NO usar relacional". La segunda es la que manda: el curso usa **MongoDB**, que es **NoSQL orientada a documentos**.

Lo que debes entregar es un **modelo de documentos**, no un entidad-relación:
```
usuarios          { _id, nombre, correo, rol, passwordHash, semestre, programa }
perfilesTutor     { _id, usuarioId, bio, materias[], tarifaHora, disponibilidad{}, verificado }
materias          { _id, nombre, codigo }
sesiones          { _id, solicitanteId, tutorId, materiaId, fecha, franja, tema, estado }
calificaciones    { _id, sesionId, solicitanteId, tutorId, puntaje, resena, fecha }
```
Justifica en el informe **por qué NoSQL**: esquema flexible (la disponibilidad del tutor es una estructura anidada), documentos embebidos, y es el stack del curso.

### Diagrama de clases
Es **un módulo**, no todo el sistema. Modela el más rico: **M4 Sesiones**.
Clases sugeridas: `Usuario` → heredan `Solicitante` y `Tutor`; `Sesion`; `Calificacion`; `Materia`. Con atributos, métodos y cardinalidades.

---

## MÉTRICAS DE USABILIDAD *(ver `08_METRICAS_SUS.md`)*

| Métrica | Estado |
|---|---|
| Tasa de éxito de una tarea | ⬜ |
| Tiempo resolviendo una tarea | ⬜ |
| Tasa de error / clics perdidos | ⬜ |
| Mapa de calor | ⬜ *(opcional, difícil sin herramienta)* |
| **Test SUS (10 preguntas)** | ⬜ |

---

## Lo que viene DESPUÉS (no es de esta entrega)
`Codificar → Testear → Implementar` — Fases 3, 4 y 5 del SDLC, Entregas 2 y 3. Menciónalo en las conclusiones para mostrar que sabes hacia dónde va.
