# PROTOTIPO FIGMA — plan de ataque (el 35%, y ahora más exigente)

> ⚠️ **El alcance cambió** con tus notas de clase: la profesora pide que **todos los módulos estén en los prototipos de alta fidelidad**, con **UI Kit en Atomic Design** y **mobile first**. Ya no bastan 5 pantallas.

---

## 1. Los módulos que tienen que estar

| Módulo | Pantalla(s) que lo cubre |
|---|---|
| M1 Autenticación | P1 Registro · P2 Login |
| M2 Perfiles | P8 Perfil y disponibilidad del tutor |
| M3 Búsqueda y catálogo | P3 Búsqueda · P4 Perfil público del tutor |
| M4 Sesiones | P5 Solicitud · P6 Mis sesiones |
| M5 Calificaciones | P7 Calificación *(modal sobre P6)* |
| M6 Administración | P9 Verificación de tutores |

**9 pantallas en móvil + 3 en escritorio.** Es mucho, pero con el UI Kit bien hecho las últimas 4 salen en 20 minutos cada una.

> Regla que anotaste: *"en los prototipos de alta, desde que me registro hasta..."* — el recorrido tiene que empezar en el registro y llegar hasta la calificación. **Sin huecos.**

---

## 2. UI Kit con Atomic Design (constrúyelo PRIMERO)

Esta es la hora mejor invertida del martes. Sáltatela y pagas el doble después.

### Átomos — la mínima unidad indivisible
Botón (primario / secundario / deshabilitado) · Input · Label · Ícono · Estrella de calificación · Chip de estado · Avatar · Etiqueta de materia

### Moléculas — varios átomos con una función conjunta
Campo de formulario (label + input + mensaje de error) · Barra de búsqueda (input + botón) · Selector de franja horaria · Bloque de calificación (5 estrellas + promedio + conteo) · Ítem de lista de sesión

### Organismos — secciones completas y autónomas
Navbar · Tarjeta de tutor completa · Listado de resultados · Formulario de solicitud de sesión · Calendario de disponibilidad · Modal de calificación

> **Un botón es un ÁTOMO.** En tus apuntes quedó una línea diciendo que podría ser molécula — es el error más fácil de que te corrijan en la sustentación.

Monta una página aparte en Figma llamada **"UI Kit"** con los tres niveles rotulados. Exporta esa página como imagen para el informe: es evidencia directa de un entregable que la profesora pidió por nombre.

---

## 3. Mobile first, en ese orden

Diseña **primero en móvil (375px)**, luego adaptas. No al revés.

| Prioridad | Tamaño | Qué |
|---|---|---|
| 1 | **Móvil 375px** | Las 9 pantallas |
| 2 | **Escritorio 1440px** | Solo Búsqueda, Perfil del tutor, Mis sesiones |
| 3 | Tablet 768px | Solo si sobra tiempo — es lo primero que se sacrifica |

Justifica el *mobile first* en el informe: Ana busca tutor desde el celular entre clases, no sentada en un computador.

---

## 4. Mapa de navegación ≠ User flow

Son dos entregables distintos y la profesora los pidió por separado.

**Mapa de navegación** — la estructura jerárquica del sitio. Qué cuelga de qué.
```
Inicio
├── Registro
├── Login
└── (autenticado)
    ├── Búsqueda de tutores
    │   └── Perfil del tutor
    │       └── Solicitud de sesión
    ├── Mis sesiones
    │   └── Calificar
    ├── Mi perfil / Disponibilidad
    └── Admin › Verificación de tutores
```

**User flow** — el camino para lograr UNA tarea, con decisiones. Haz el de "conseguir una tutoría":
`Entra → ¿tiene cuenta? → (no) Registro / (sí) Login → Busca materia → ¿hay tutores? → (no) estado vacío / (sí) Compara → Abre perfil → Solicita → ¿tutor acepta? → Confirmada → Sesión → Califica`

---

## 5. Los 2 flujos navegables en Prototype

**Flujo A — Ana consigue una tutoría** *(el que vas a demostrar)*
`P1 Registro → P2 Login → P3 Búsqueda "Cálculo" → P4 Perfil de Daniel → P5 Solicitud → Confirmación → P6 Mis sesiones`

**Flujo B — Ana califica**
`P6 Mis sesiones (finalizada) → P7 modal de calificación → vuelve a P4 con la calificación reflejada`

**Prueba de fuego:** que se recorra de punta a punta con el mouse, sin que tú digas una palabra.

---

## 6. Orden de construcción del martes

1. **UI Kit** (1h) — átomos, moléculas, organismos
2. **Pantallas core en móvil** (3h) — P1, P2, P3, P4
3. **Pantallas restantes** (1.5h) — P5, P6, P7, P8, P9
4. **Desktop de las 3 clave** (45 min)
5. **Conectar + mapa de navegación + user flow** (45 min)
6. **Test SUS con 3 personas** (1h, en la noche) → `08_METRICAS_SUS.md`

---

## 7. Contenido realista

Nada de "Lorem ipsum" ni "Tutor 1". Usa datos coherentes con tus personas:
- **Tutores:** Daniel Duque (Cálculo Diferencial, 8º sem, $35.000/h, ★4.8, 23 tutorías) · Laura Mejía (Estadística, 7º sem, $30.000/h, ★4.6, 11 tutorías) · Andrés Rincón (Programación, 9º sem, $40.000/h, ★4.9, 34 tutorías)
- **Materias:** Cálculo Diferencial, Estadística, Programación, Álgebra Lineal, Contabilidad
- **Solicitante:** Ana María Quintero, 2º semestre

---

## 8. Detalles que se te van a olvidar
- [ ] **Estados vacíos**: "Aún no hay tutores para esta materia", "No tienes sesiones". Cuestan 5 minutos y se notan mucho.
- [ ] **Estados de error**: correo no institucional, franja ya ocupada.
- [ ] El perfil público **no** muestra teléfono ni documento (es tu RQF020 y te lo pueden preguntar).
- [ ] Permisos del archivo: **"Cualquier persona con el enlace → puede ver"**.
- [ ] Exporta capturas en PNG para el informe **y un PDF con todas las pantallas como plan B** por si falla el internet en la sustentación.
- [ ] Exporta la página del **UI Kit** aparte.

---

## 9. Material de apoyo que ya tienes
- `Etapa 1 Diseño/prototipos web/Guía UI Kit — Sistemas de componentes en Figma · Desarrollo Web.html` ← **léela el martes antes de empezar, es exactamente el paso 1**
- `Etapa 1 Diseño/prototipos web/Prototipos de baja y alta fidelidad con Figma · Material de apoyo.html`
- `Etapa 1 Diseño/3. RECURSO_Diseño_UX_UI.pdf` · `4. JERARQUIAS DE LA INFORMACION.pdf`
