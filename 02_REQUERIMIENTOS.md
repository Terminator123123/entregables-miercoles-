# REQUERIMIENTOS — ConectaTutor (base de trabajo)
> **Esto es un borrador defendible, no un entregable final.** Revísalo en equipo, recorta lo que no vayan a construir y ajusta redacción. Regla: **si no lo piensan construir en las Entregas 2 y 3, márquenlo Won't.**
>
> Formato final: pasar al `FORMATO FORMULACIÓN REQUISITOS.docx` (Código / Nombre / Descripción / Usuarios).

## Actores
| Actor | Descripción |
|---|---|
| **Estudiante solicitante** | Busca refuerzo académico. Persona representativa: Ana María Quintero. |
| **Estudiante tutor** | Ofrece tutorías en materias que domina. Persona representativa: Daniel Duque. |
| **Administrador** | Verifica tutores y gestiona el catálogo de materias. |

---

## Requerimientos funcionales

| Código | Nombre | Descripción | Usuarios | MoSCoW | Trazabilidad |
|---|---|---|---|:---:|---|
| RQF001 | Registro con correo institucional | El sistema debe permitir crear una cuenta validando que el correo pertenezca al dominio `@urosario.edu.co`. | Solicitante, Tutor | **Must** | Ana: "necesita confiar en que la persona es real" |
| RQF002 | Selección de rol | Durante el registro el usuario debe elegir su rol: solicitante o tutor. | Solicitante, Tutor | **Must** | Dos personas distintas con flujos distintos |
| RQF003 | Inicio y cierre de sesión | El sistema debe autenticar al usuario con correo y contraseña, y permitirle cerrar sesión. | Todos | **Must** | Base de toda la plataforma |
| RQF004 | Almacenamiento seguro de contraseñas | El sistema debe guardar las contraseñas cifradas mediante hashing irreversible. | Sistema | **Must** | Daniel: preocupación por seguridad |
| RQF005 | Perfil del solicitante | El solicitante debe poder registrar nombre, programa académico y semestre. | Solicitante | **Must** | Daniel: "conocer previamente el perfil del solicitante" |
| RQF006 | Perfil del tutor | El tutor debe poder registrar biografía, materias que domina, semestre y tarifa por hora. | Tutor | **Must** | Daniel: "publicar las materias que domina" |
| RQF007 | Disponibilidad horaria del tutor | El tutor debe poder definir su disponibilidad semanal por día y franja horaria. | Tutor | **Must** | Daniel: "definir su disponibilidad" / Ana: "horarios compatibles" |
| RQF008 | Catálogo de materias | El sistema debe ofrecer un listado de materias sobre el cual tutores y solicitantes seleccionan. | Todos | **Must** | Evita texto libre inconsistente |
| RQF009 | Búsqueda de tutores por materia | El solicitante debe poder buscar tutores filtrando por materia. | Solicitante | **Must** | Ana: "buscar tutores por materia" |
| RQF010 | Filtros adicionales de búsqueda | El sistema debe permitir filtrar los resultados por rango de precio, calificación y disponibilidad. | Solicitante | **Should** | Ana: "comparar perfiles de forma rápida" |
| RQF011 | Visualización del perfil público del tutor | El solicitante debe poder ver biografía, materias, tarifa, disponibilidad y calificaciones del tutor. | Solicitante | **Must** | Ana: "revisar experiencia, disponibilidad, precio y calificaciones" |
| RQF012 | Solicitud de sesión de tutoría | El solicitante debe poder solicitar una sesión escogiendo materia, fecha y franja disponible. | Solicitante | **Must** | Requisito inicial de la Línea 2 |
| RQF013 | Descripción del tema a trabajar | Al solicitar una sesión, el solicitante debe poder describir las dudas o temas específicos. | Solicitante | **Should** | Ana: "cargar previamente los temas" / Daniel: "conocer el tema" |
| RQF014 | Confirmación o rechazo de la solicitud | El tutor debe poder aceptar o rechazar las solicitudes recibidas. | Tutor | **Must** | Daniel: "administrar solicitudes" |
| RQF015 | Panel "Mis sesiones" | Cada usuario debe poder ver sus sesiones pendientes, confirmadas y finalizadas. | Solicitante, Tutor | **Must** | Requisito inicial de la Línea 2 |
| RQF016 | Cancelación de sesión | El usuario debe poder cancelar una sesión confirmada indicando un motivo. | Solicitante, Tutor | **Should** | Realidad del contexto académico |
| RQF017 | Calificación y reseña del tutor | Tras finalizar una sesión, el solicitante debe poder calificar de 1 a 5 y dejar una reseña. | Solicitante | **Must** | Requisito inicial de la Línea 2 |
| RQF018 | Cálculo de calificación promedio | El sistema debe calcular y mostrar el promedio de calificaciones de cada tutor. | Sistema | **Must** | Ana: "certeza de que domina el tema" |
| RQF019 | Historial de tutorías realizadas | El perfil del tutor debe mostrar el número de tutorías completadas. | Todos | **Should** | Daniel: "reconocimiento por su experiencia" |
| RQF020 | Protección de datos de contacto | El sistema no debe exponer teléfono ni documento de identidad en perfiles públicos. | Sistema | **Must** | Daniel: "no revelar su número personal" |
| RQF021 | Verificación de tutores por el administrador | El administrador debe poder marcar un tutor como verificado tras revisar su soporte académico. | Administrador | **Should** | Ana: "confiar en que la información es verídica" |
| RQF022 | Notificación de cambios de estado | El sistema debe notificar al usuario cuando su solicitud cambie de estado. | Solicitante, Tutor | **Could** | Reduce incertidumbre |
| RQF023 | Chat interno entre tutor y solicitante | Mensajería dentro de la plataforma sin exponer datos personales. | Solicitante, Tutor | **Won't** (este semestre) | Alcance: se documenta pero no se implementa |
| RQF024 | Pasarela de pagos en línea | Procesamiento de pagos de tutorías dentro de la plataforma. | Todos | **Won't** (este semestre) | Fuera del stack del curso |

**Resumen MoSCoW:** Must 14 · Should 6 · Could 1 · Won't 2 (ajusten los números si recortan).

---

## Requerimientos no funcionales

| Código | Nombre | Descripción | MoSCoW |
|---|---|---|:---:|
| RQNF001 | Diseño responsivo | La aplicación debe visualizarse correctamente en móvil, tablet y escritorio. | **Must** |
| RQNF002 | Tiempo de respuesta | Las vistas principales deben cargar en menos de 3 segundos con conexión normal. | **Should** |
| RQNF003 | Usabilidad | Un usuario nuevo debe poder solicitar su primera tutoría en máximo 5 pasos. | **Must** |
| RQNF004 | Accesibilidad básica | Contraste de texto suficiente, textos alternativos en imágenes y navegación por teclado. | **Should** |
| RQNF005 | Seguridad de sesión | El acceso a vistas privadas debe requerir sesión activa y expirar por inactividad. | **Must** |
| RQNF006 | Compatibilidad de navegadores | Debe funcionar en las versiones recientes de Chrome, Firefox y Edge. | **Should** |
| RQNF007 | Mantenibilidad del código | El código debe seguir convenciones de nombres, estar comentado y versionado en GitHub. | **Must** |
| RQNF008 | Disponibilidad | La aplicación desplegada debe estar accesible en línea mediante una URL pública. | **Must** |

---

## Cómo verificar la trazabilidad (lo que sube la nota de 30%)
Antes de entregar, respondan estas tres preguntas por escrito:
1. ¿Hay algún RF **Must** que no responda a una necesidad de Ana o Daniel? → Bájenlo a Should o bórrenlo.
2. ¿Hay alguna necesidad de Ana o Daniel sin ningún RF que la cubra? → Falta un requerimiento.
3. ¿Cada RF **Must** tiene una historia de usuario en `03_HISTORIAS_USUARIO.md`? → Si no, o sobra el RF o falta la historia.
