# Tutoría Fácil UTA - Grupo 2 (D), 5to "B"

Examen práctico integrador del primer parcial de Interacción Humano Computador, Carrera de Ingeniería de Software, Universidad Técnica de Ambato.

## Problema
¿Cómo permitir que un estudiante reserve o reprograme una tutoría desde un teléfono, con claridad, bajo esfuerzo cognitivo, prevención de errores y acceso mediante teclado o tecnologías de apoyo?

## Integrantes y roles
| Integrante | Usuario GitHub | Rol | Actividades |
|---|---|---|---|
| Sheyla Pacha | @Zzzheyla | Analista DCU | 1 y 3 |
| Martin Palacios | @killer13233 | Diseño y accesibilidad | 2, 4 y 5 |
| David Pérez | @DavidPe1307 | Prototipado y evaluación | 6 |

## Enlaces
- Enlace del prototipo 1 en Figma: [https://www.figma.com/design/37sG9AKc1SGTBcWSfmxwC9/Prueba_Primer_Parcial_HCI?node-id=0-1&p=f&t=gHSkhbPP9a2L3WDs-0]
- Prototipo interactivo mejorado en Figma: [https://www.figma.com/make/CnMRtLo0OdQPYDI0G6VdBB/Tutor%C3%ADa-F%C3%A1cil-UTA?t=v5cIbykmLDcKw0KK-20&fullscreen=1]


## Estructura del repositorio
- `docs/`
  - `01_matriz_ihc.pdf`: matriz humano-sistema con evidencias E1 a E10
  - `02_usabilidad_accesibilidad.pdf`: indicadores con meta y decisiones POUR
  - `03_dcu_contexto.pdf`: contexto de uso, personas, escenario, journey map y cinco requisitos
  - `04_decisiones_diseno.pdf`: metáforas, affordance, Gestalt, carga cognitiva y guía de estilo
- `prototipo/`
  - `despues_pantalla2.pdf`: enlace al prototipo navegable mejorado y enlace.
  - `capturas/`: capturas de las cuatro pantallas y de las comparaciones antes y después
  - `enlace_prototipo.md`: enlace al prototipo navegable

- `evaluacion/`
  - `prueba_iteracion.md`: tarea, participante, resultado, tiempo, hallazgo, antes y después

## Resumen de la prueba y mejora aplicada

**Prueba cruzada:** [código del participante y su grupo] recibió el prototipo sin explicación previa y realizó la tarea "Reserva una tutoría para el jueves y luego cambia el horario". La completó sin ayuda en 1 min 30 s y valoró la experiencia con 5 de 7.

**Resultados frente a los indicadores (prototipo 1, antes de la mejora):**

| Dimensión | Meta | Resultado | ¿Cumple? |
|---|---|---|---|
| Efectividad | ≥ 80 % completa la reserva sin ayuda | 1 de 1 completó reserva y reprogramación sin ayuda. Solo valida la ruta preestablecida | Sí, con reserva (un participante) |
| Eficiencia: tiempo | ≤ 2 min | 1 min 30 s | Sí |
| Eficiencia: toques | ≤ 8 toques | 6 toques: Reservar tutoría, Continuar, Confirmar, Cambiar horario, Continuar, Confirmar | Sí |
| Satisfacción | Promedio ≥ 5,5 (escala 1 a 7) | 5 | No |
| Aprendizaje y errores | 0 selecciones de horario ocupado; recuperación en ≤ 1 intento | No medible: el prototipo no permitía tocar un horario ocupado | N/A |

**Hallazgo principal:** la pantalla "Elige un horario" mostraba a la vez "Cargando disponibilidad…", "Horario seleccionado" y "Ese horario ya no está disponible", con "Continuar" activo (Nielsen H1, H5 y H9, severidad 3; evidencias E3, E8 y E10). El participante dudó si podía avanzar, lo que es coherente con la satisfacción de 5, por debajo de la meta de 5,5.

**Hallazgo secundario:** "Mis tutorías" no llevaba a una pantalla coherente con el Inicio, que decía "Aún no tienes tutorías reservadas" (H4, severidad 3; evidencia E5).

**Mejora aplicada:**
- Un solo estado por pantalla, con variantes separadas de carga y de error. En el error, el horario ocupado no se puede seleccionar y "Continuar" se deshabilita.
- "Mis tutorías" pasó a ser una pantalla con la lista de tutorías y la opción de cambiar horario.
- Capturas del antes y el después en `prototipo/capturas/`.

**Limitaciones:** la prueba se hizo con un solo participante. El prototipo 1 solo permitía navegar por opciones preestablecidas, por lo que las selecciones de horarios ocupados no se pudieron medir. El prototipo mejorado es interactivo y permite medirlas en una nueva prueba.

## Registro del equipo
Grupo: 2 · Paralelo: 5to "B"

| Integrante y usuario | Issue y rama | PR propio y revisión realizada | Aporte verificable |
|---|---|---|---|
| 1. Sheyla Pacha @Zzzheyla | #1 · `feature/sheyla-analisis-dcu` | PR #5 (revisado por David) · Revisó PR #4 | Matriz IHC y contexto DCU (`docs/01` y `docs/03`) |
| 2. Martin Palacios @killer13233 | #2 · `feature/martin-usabilidad-diseno` | PR #4 (revisado por Sheyla) · Revisó PR #6 | Indicadores, POUR y decisiones de diseño (`docs/02` y `docs/04`) |
| 3. David Pérez @DavidPe1307 | #3 · `feature/david-prototipo-evaluacion` | PR #6 (revisado por Martin) · Revisó PR #5 | Prototipo, prueba cruzada, evaluación y README |

Aporte adicional: Issue #7 y PR #8, creado por Sheyla, revisado y cerrado por David.

## Trazabilidad en GitHub
Issues cerrados y commits:
David Pérez (@DavidPe1307)
Issue: https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/issues/3
Commits:
https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/commit/ff87ca11dc6159bbfcd12662841733f92a8e51b4
https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/commit/b8e6336f1b233f211541ad5b20cd9dee5d61405d

Sheyla Pacha (@Zzzheyla)
Issues:
https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/issues/1
https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/issues/7
Commits:
https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/commit/4ab723230e61363c6c07ca3bb794916ae7f75bda
https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/commit/9631fa3306093640d211ee0c688893d4e8bcecd9

Martin Palacios (@killer13233)
Issue: https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/issues/2
Commits:
https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/commit/b0ea1db63323057b65e15d03a0bfe3e4a3a3b249
https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/commit/68ea4e7d7d13f0290c8a3e19a96f2095ef691c8d

## 4. Pull requests (creados por un integrante, revisados por otro e integrados a main):
- Sheyla (issue #1, rama feature/sheyla-analisis-dcu): https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/pull/5, revisado por David. Revisó el PR #4 de Martin.
- Martin (issue #2, rama feature/martin-usabilidad-diseno): https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/pull/4, revisado por Sheyla. Revisó el PR #6 de David.
- David (issue #3, rama feature/david-prototipo-evaluacion): https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/pull/6, revisado por Martin. Revisó el PR #5 de Sheyla.
- Adicional, de Sheyla (issue #7), revisado y cerrado por David: https://github.com/DavidPe1307/Grupo_2_Tutoria_Facil_UTA/pull/8

## 5. Reflexión grupal:
Distribuimos el trabajo según los roles del examen: Sheyla, como analista DCU, desarrolló la matriz humano-sistema, el contexto, la persona, el journey map y los requisitos; Martin, en diseño y accesibilidad, definió indicadores, POUR, decisiones de diseño y guía de estilo; David construyó el prototipo y la prueba cruzada. Cada uno trabajó con su issue, su rama y su pull request. Las diferencias surgieron al alinear el análisis con las pantallas, por ejemplo qué estados mostraría la cita, y las resolvimos conversando y priorizando lo que el prototipo realmente podía comprobar. Para verificar la coherencia, contrastamos los requisitos R1 a R5 y las decisiones POUR con las cuatro pantallas, confirmamos que cada conclusión citara evidencias E1 a E10 y realizamos revisiones cruzadas en los pull requests antes de fusionar con main.