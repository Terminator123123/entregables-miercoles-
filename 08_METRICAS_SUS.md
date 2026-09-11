# MÉTRICAS DE USABILIDAD Y TEST SUS

> De tus apuntes. Esto casi nadie lo entrega bien, así que **es donde más fácil te diferencias**.
> Y tiene una ventaja enorme: se hace **sobre el prototipo de Figma**, no sobre código. Ya lo puedes ejecutar esta semana.

---

## 1. Las métricas que anotaste

| Métrica | Cómo se mide | Meta que puedes declarar |
|---|---|---|
| **Tasa de éxito de la tarea** | % de usuarios que completan la tarea sin ayuda | ≥ 80% |
| **Tiempo resolviendo la tarea** | Cronómetro desde que empieza hasta que termina | ≤ 90 s para solicitar una tutoría |
| **Tasa de error / clics perdidos** | Clics en zonas que no llevan a ningún lado ÷ clics totales | ≤ 20% |
| **Tiempo de respuesta** | Cuánto tarda la interfaz en reaccionar | < 3 s *(se medirá en Entrega 2, aquí solo se declara)* |
| **Mapa de calor** | Dónde se concentran los clics | Opcional — ver nota abajo |

> **Mapa de calor:** sin herramienta de analítica no lo puedes generar de verdad. Dos opciones honestas: (a) hazlo **manual** marcando sobre una captura dónde hizo clic cada persona que probaste, o (b) decláralo como métrica **planificada para la Entrega 2**. No inventes uno.

---

## 2. Test de usabilidad SUS — las 10 preguntas

El SUS (*System Usability Scale*) es estándar. Escala de 1 (muy en desacuerdo) a 5 (muy de acuerdo).

1. Creo que usaría este sistema con frecuencia.
2. Encuentro este sistema innecesariamente complejo.
3. Creo que el sistema es fácil de usar.
4. Creo que necesitaría ayuda de alguien con conocimientos técnicos para usar este sistema.
5. Las funciones del sistema están bien integradas.
6. Creo que el sistema es demasiado inconsistente.
7. Imagino que la mayoría de la gente aprendería a usar este sistema muy rápidamente.
8. Encuentro el sistema muy incómodo de usar.
9. Me he sentido muy seguro usando el sistema.
10. Necesité aprender muchas cosas antes de poder usar este sistema.

### Cómo se calcula el puntaje
- **Preguntas impares (1,3,5,7,9):** resta 1 a la respuesta → `valor - 1`
- **Preguntas pares (2,4,6,8,10):** resta la respuesta a 5 → `5 - valor`
- Suma los 10 resultados y **multiplica por 2.5**
- Resultado entre 0 y 100

### Cómo se interpreta
| Puntaje | Lectura |
|---|---|
| > 80.3 | Excelente |
| 68 – 80.3 | Bueno |
| **68** | **Promedio de la industria** — este es el número que hay que citar |
| 51 – 68 | Aceptable, con problemas |
| < 51 | Deficiente |

---

## 3. Cómo ejecutarlo esta semana (45 minutos reales)

**Cuándo:** martes en la noche, después de conectar los flujos. O miércoles temprano.
**Con quién:** 3 personas. Compañeros, amigos, familia. Con 3 ya tienes datos reales y defendibles.
**Con qué:** el prototipo de Figma en modo Presentación, en el celular.

### Guion (15 min por persona)

**Antes:** *"Te voy a pedir que hagas dos tareas en una app. No te voy a ayudar. Si te trabas, dime qué estás pensando. No te estoy evaluando a ti, estoy evaluando el diseño."*

**Tarea 1 — Encontrar y solicitar una tutoría**
> *"Necesitas ayuda en Cálculo Diferencial. Busca un tutor y solicítale una sesión."*
- [ ] ¿Lo completó? Sí / No
- [ ] Tiempo: ____ s
- [ ] Clics perdidos: ____
- [ ] Dónde dudó: ____________

**Tarea 2 — Calificar una sesión**
> *"Ya tuviste la tutoría. Califícala."*
- [ ] ¿Lo completó? Sí / No
- [ ] Tiempo: ____ s
- [ ] Clics perdidos: ____

**Después:** pásale las 10 preguntas del SUS.

---

## 4. Tabla de resultados para el informe

| Participante | Tarea 1 éxito | Tarea 1 tiempo | Tarea 2 éxito | Tarea 2 tiempo | Clics perdidos | SUS |
|---|---|---|---|---|---|---|
| P1 | | | | | | |
| P2 | | | | | | |
| P3 | | | | | | |
| **Promedio** | **__%** | **__s** | **__%** | **__s** | **__%** | **__** |

**Hallazgos y acciones** *(esta tabla es la que impresiona)*

| # | Problema observado | Frecuencia | Acción tomada en el prototipo |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## 5. Por qué esto te conviene tanto

La rúbrica premia el prototipo "coherente, con flujos completos". Si además llegas con **evidencia de que lo probaste con usuarios reales, con números, y con los cambios que hiciste a partir de eso**, estás cerrando el ciclo completo de Design Thinking: *empatizar → definir → idear → prototipar → **evaluar***.

Y en la sustentación tienes una frase que casi nadie va a poder decir:
> *"Probé el prototipo con tres usuarios. El SUS dio 76, por encima del promedio de la industria. Dos de los tres se trabaron en el mismo punto, así que cambié esto."*

Eso vale más que una pantalla extra bonita.
