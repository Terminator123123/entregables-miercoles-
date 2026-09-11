# LOS 6 DIAGRAMAS — listos en Mermaid

> **Cómo usarlos:** entra a **https://mermaid.live**, pega el bloque y exporta como PNG o SVG.
> Si prefieres draw.io: *Extras → Edit Diagram* también acepta Mermaid.
> Después ajusta colores y tipografía para que combinen con tu guía de estilo.

**Esto te ahorra la mayor parte de las 2h del martes en la tarde.** Revisa que cada uno refleje TU proyecto antes de pegarlo en el informe: en la sustentación te preguntan por lo que dibujaste.

---

## 1. Diagrama de solución *(Fase 2 — Planeación)*

Los módulos del sistema y cómo se relacionan.

```mermaid
graph TD
    subgraph CLIENTE
        UI[Interfaz web responsiva<br/>React + Bootstrap]
    end

    subgraph MODULOS[Modulos del sistema]
        M1[M1 · Autenticacion<br/>registro, login, roles]
        M2[M2 · Perfiles<br/>solicitante y tutor]
        M3[M3 · Busqueda y catalogo<br/>materias, filtros]
        M4[M4 · Sesiones<br/>solicitar, confirmar, cancelar]
        M5[M5 · Calificaciones<br/>puntaje y resenas]
        M6[M6 · Administracion<br/>verificacion de tutores]
    end

    subgraph DATOS[Persistencia]
        DB[(MongoDB Atlas<br/>NoSQL)]
    end

    UI --> M1
    M1 --> M2
    M2 --> M3
    M3 --> M4
    M4 --> M5
    M5 -.actualiza promedio.-> M2
    M6 -.verifica.-> M2
    M1 --> DB
    M2 --> DB
    M3 --> DB
    M4 --> DB
    M5 --> DB
    M6 --> DB
```

---

## 2. Diagrama de flujo de la solución *(Fase 2 — Planeación)*

El proceso con decisiones. **Distinto del anterior:** aquí importan el orden y las bifurcaciones.

```mermaid
flowchart TD
    A([Inicio]) --> B{Tiene cuenta?}
    B -- No --> C[Registro con<br/>correo institucional]
    C --> D{Correo valido<br/>urosario.edu.co?}
    D -- No --> E[Error: correo<br/>no institucional]
    E --> C
    D -- Si --> F[Selecciona rol]
    B -- Si --> G[Inicio de sesion]
    F --> G
    G --> H{Rol?}

    H -- Tutor --> I[Configura perfil,<br/>materias y disponibilidad]
    I --> J[Espera solicitudes]

    H -- Solicitante --> K[Busca tutor<br/>por materia]
    K --> L{Hay tutores<br/>disponibles?}
    L -- No --> M[Estado vacio:<br/>sugerir materias afines]
    M --> K
    L -- Si --> N[Compara perfiles:<br/>precio, horario, calificacion]
    N --> O[Abre perfil del tutor]
    O --> P[Solicita sesion:<br/>fecha, franja y tema]

    P --> J
    J --> Q{Tutor acepta?}
    Q -- No --> R[Solicitud rechazada<br/>se notifica]
    R --> K
    Q -- Si --> S[Sesion confirmada]
    S --> T[Se realiza la tutoria]
    T --> U[Solicitante califica<br/>1 a 5 mas resena]
    U --> V[Se recalcula el<br/>promedio del tutor]
    V --> W([Fin])
```

---

## 3. Mapa de navegación *(Fase 3 — Diseño)*

Estructura jerárquica del sitio: qué pantalla cuelga de cuál.

```mermaid
graph TD
    ROOT[ConectaTutor]
    ROOT --> PUB[Publico]
    ROOT --> PRIV[Autenticado]

    PUB --> P1[P1 · Registro]
    PUB --> P2[P2 · Login]

    PRIV --> BUS[Busqueda]
    PRIV --> SES[Sesiones]
    PRIV --> PER[Mi cuenta]
    PRIV --> ADM[Administracion]

    BUS --> P3[P3 · Busqueda de tutores]
    P3 --> P4[P4 · Perfil del tutor]
    P4 --> P5[P5 · Solicitud de sesion]

    SES --> P6[P6 · Mis sesiones]
    P6 --> P7[P7 · Calificar - modal]

    PER --> P8[P8 · Perfil y disponibilidad]

    ADM --> P9[P9 · Verificacion de tutores]
```

---

## 4. User flow *(Fase 3 — Diseño)*

⚠️ **No es lo mismo que el mapa de navegación.** Aquí es el camino para lograr **una tarea**: conseguir una tutoría.

```mermaid
flowchart LR
    A([Ana necesita<br/>ayuda en Calculo]) --> B[Abre la app<br/>en el celular]
    B --> C[Inicia sesion]
    C --> D[Escribe<br/>Calculo Diferencial]
    D --> E[Ve 3 tutores<br/>con precio y estrellas]
    E --> F{Alguno le sirve?}
    F -- No --> G[Ajusta filtros:<br/>precio y horario]
    G --> E
    F -- Si --> H[Abre el perfil<br/>de Daniel]
    H --> I{Le convence<br/>el perfil?}
    I -- No --> E
    I -- Si --> J[Elige franja<br/>del martes 3 pm]
    J --> K[Describe su duda:<br/>derivadas implicitas]
    K --> L[Envia la solicitud]
    L --> M([Confirmacion:<br/>espera respuesta])

    style A fill:#e8f4f8
    style M fill:#e8f8ec
```

---

## 5. Diagrama de clases *(módulo M4 — Sesiones)*

Recuerda: la profesora pidió **un módulo**, no todo el sistema.

```mermaid
classDiagram
    class Usuario {
        -String id
        -String nombre
        -String correo
        -String passwordHash
        -String rol
        +registrar() bool
        +iniciarSesion() Token
        +cerrarSesion() void
    }

    class Solicitante {
        -String programa
        -int semestre
        +buscarTutor(materia) List
        +solicitarSesion(tutor, fecha) Sesion
        +calificar(sesion, puntaje) Calificacion
    }

    class Tutor {
        -String biografia
        -double tarifaHora
        -bool verificado
        -double promedioCalificacion
        +definirDisponibilidad(franjas) void
        +aceptarSolicitud(sesion) bool
        +rechazarSolicitud(sesion, motivo) void
    }

    class Sesion {
        -String id
        -Date fecha
        -String franja
        -String tema
        -String estado
        +confirmar() void
        +cancelar(motivo) void
        +finalizar() void
    }

    class Calificacion {
        -String id
        -int puntaje
        -String resena
        -Date fecha
        +registrar() void
    }

    class Materia {
        -String id
        -String nombre
        -String codigo
    }

    Usuario <|-- Solicitante : hereda
    Usuario <|-- Tutor : hereda
    Solicitante "1" --> "0..*" Sesion : solicita
    Tutor "1" --> "0..*" Sesion : atiende
    Sesion "1" --> "1" Materia : trata sobre
    Sesion "1" --> "0..1" Calificacion : genera
    Tutor "1" --> "0..*" Materia : ofrece
```

---

## 6. Arquitectura de base de datos *(NoSQL — modelo de documentos)*

⚠️ **No es un entidad-relación.** Es MongoDB: colecciones de documentos con referencias y objetos embebidos.

```mermaid
graph LR
    subgraph U[coleccion usuarios]
        U1["_id<br/>nombre<br/>correo<br/>passwordHash<br/>rol<br/>programa<br/>semestre"]
    end

    subgraph PT[coleccion perfilesTutor]
        PT1["_id<br/>usuarioId (ref)<br/>biografia<br/>materias[] (ref)<br/>tarifaHora<br/>disponibilidad{} (embebido)<br/>verificado<br/>promedioCalificacion"]
    end

    subgraph MA[coleccion materias]
        MA1["_id<br/>nombre<br/>codigo"]
    end

    subgraph SE[coleccion sesiones]
        SE1["_id<br/>solicitanteId (ref)<br/>tutorId (ref)<br/>materiaId (ref)<br/>fecha<br/>franja<br/>tema<br/>estado"]
    end

    subgraph CA[coleccion calificaciones]
        CA1["_id<br/>sesionId (ref)<br/>tutorId (ref)<br/>puntaje<br/>resena<br/>fecha"]
    end

    PT1 -.referencia.-> U1
    PT1 -.referencia.-> MA1
    SE1 -.referencia.-> U1
    SE1 -.referencia.-> MA1
    CA1 -.referencia.-> SE1
    CA1 -.referencia.-> PT1
```

**Convención:** `(ref)` referencia a otra colección · `(embebido)` objeto anidado dentro del documento · `[]` arreglo

### Justificación de NoSQL (va en el informe, sección 22)
- **Esquema flexible:** la disponibilidad del tutor es una estructura anidada por día y franja que no encaja bien en tablas.
- **Documentos embebidos:** la disponibilidad vive dentro del perfil y se lee en una sola consulta.
- **Lecturas dominantes:** la operación más frecuente es buscar tutores por materia, que se resuelve con un índice sobre `materias[]`.
- **Stack del curso:** MongoDB Atlas es la base definida en los lineamientos.

---

## Antes de pegarlos en el informe

- [ ] Verifica que los 6 módulos del diagrama de solución coincidan con las 9 pantallas de tu Figma
- [ ] Verifica que los estados de `Sesion` sean los mismos que usas en el prototipo (pendiente / confirmada / finalizada / cancelada)
- [ ] Exporta cada uno en PNG a buena resolución: en el proyector se ven borrosos si los sacas pequeños
- [ ] Ponle pie a cada figura (*"Figura N. Diagrama de..."*) y referéncialas en el texto
