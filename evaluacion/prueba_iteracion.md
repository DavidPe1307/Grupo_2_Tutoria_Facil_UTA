# Prueba cruzada e iteración: Tutoría Fácil UTA

Grupo: _____D______  Paralelo: _____5to "B"______
Issue relacionado: #__3__  Pull request: #__4__

## 1. Alcance y limitaciones del prototipo probado

El prototipo es de fidelidad baja a media y **solo permite navegar por opciones preestablecidas**. No es un sistema funcional. Esto condiciona qué se puede observar y medir.

| Desde | Acción | Lleva a |
|---|---|---|
| 1. Inicio | Reservar tutoría | 2. Elige un horario |
| 1. Inicio | Mis tutorías | 4. Reserva confirmada |
| 2. Elige un horario | Continuar | 3. Revisa tu tutoría |
| 2. Elige un horario | Volver | 1. Inicio |
| 3. Revisa tu tutoría | Confirmar | 4. Reserva confirmada |
| 3. Revisa tu tutoría | Volver | 2. Elige un horario |
| 4. Reserva confirmada | Cambiar horario | 2. Elige un horario |
| 4. Reserva confirmada | Volver al inicio | 1. Inicio |

No es interactivo: la selección de otro horario (10:00 ya viene seleccionado), los días, los estados de carga y error (imágenes fijas), el desplegable de modalidad y cualquier validación.

Consecuencia: la prueba mide la claridad de la ruta, no una reserva real. El indicador "0 selecciones de horario ocupado" **no se puede medir**, porque no permite tocar un horario ocupado.

## 2. Datos de la prueba

| Campo | Registro |
|---|---|
| Tarea entregada | "Reserve una tutoría para el jueves y luego cambie el horario." |
| Evaluador | Sheyla Pacha
| Método | Recorrido completo del prototipo sin explicación previa, registrando cada pantalla y contrastando con la lista de chequeo heurística de Nielsen |
| Prototipo probado | Enlace en `prototipo/enlace_prototipo.md` (4 pantallas conectadas) |

## 3. Registro del recorrido

| Paso | Pantalla | Acción | Lo observado | Duda o problema |
|---|---|---|---|---|
| 1 | Inicio | Lee el objetivo y toca "Reservar tutoría" | El mensaje "Reserva o cambia tu tutoría desde tu teléfono" es claro y el botón lleva a la pantalla 2 | "Reservar tutoría" y "Mis tutorías" tienen el mismo peso visual |
| 2 | Elige un horario | Lee el título y el docente | Aparece "Cargando disponibilidad…" junto a días ya cargados | Duda si la carga terminó |
| 3 | Elige un horario | Revisa el horario | El 10:00 ya está seleccionado sin haberlo tocado. Debajo dice "Horario seleccionado: jueves 10:00" y, a la vez, "Ese horario ya no está disponible. Elige otro." | Duda si puede continuar. Al tocar otros horarios o días no ocurre nada (limitación) |
| 4 | Elige un horario | Toca "Continuar" | Avanza a la pantalla 3 | El botón siguió activo pese al mensaje de error |
| 5 | Revisa tu tutoría | Revisa docente, fecha y hora | El resumen es claro. Solo dice "Jueves", sin número de día ni mes | El desplegable de modalidad no se abre (limitación) |
| 6 | Revisa tu tutoría | Toca "Confirmar" | Avanza a la pantalla 4 | Ninguna |
| 7 | Reserva confirmada | Lee el estado | "Reserva confirmada", el sello "Confirmada" y la tarjeta se entienden de inmediato | Ninguna |
| 8 | Reserva confirmada | Toca "Cambiar horario" | Vuelve a la pantalla 2 | No indica que es una reprogramación ni muestra la cita actual |
| 9 | Elige un horario → Revisa → Reserva confirmada | Repite Continuar y Confirmar | Completa la reprogramación | Misma duda del paso 3 |
| Extra | Inicio | Toca "Mis tutorías" | Lleva a la pantalla 4 (reserva confirmada) | Home dice "Aún no tienes tutorías reservadas", lo que contradice el destino |

Comentario final del evaluador: la ruta principal es corta y se entiende sin explicación, y la pantalla de confirmación deja claro que la reserva quedó hecha. Lo que más confunde es la pantalla 2, que muestra tres mensajes a la vez, y el botón "Mis tutorías", que contradice el mensaje del Home. Por las limitaciones del prototipo no fue posible elegir otro horario ni cambiar la modalidad.

## 4. Matriz de resultados frente a los indicadores (Zona 3)

| Dimensión | Meta definida | Resultado | ¿Cumple? |
|---|---|---|---|
| Efectividad | ≥ 80 % completa la reserva sin ayuda | Reserva y reprogramación completadas sin ayuda en el recorrido (1 de 1). Solo valida la ruta preestablecida | Sí, con reserva |
| Eficiencia: tiempo | ≤ 2 min | ____ (cronometrar el recorrido) | ____ |
| Eficiencia: toques | ≤ 8 toques | 6 toques: Reservar tutoría, Continuar, Confirmar, Cambiar horario, Continuar, Confirmar | Sí |
| Satisfacción | Promedio ≥ 5,5 (escala 1 a 7) | ____ (pedir la nota al terminar) | ____ |
| Aprendizaje y errores | 0 selecciones de horario ocupado; recuperación en ≤ 1 intento | No medible: no se puede tocar un horario ocupado. El mensaje "Elige otro" indica qué hacer, pero no hay otro horario interactivo | N/A |

## 5. Hallazgo

- Origen: inspección heurística (Nielsen) sobre el recorrido completo
- Pantalla: 2. Elige un horario
- Descripción: muestra a la vez "Cargando disponibilidad…", "Horario seleccionado: jueves 10:00" y "Ese horario ya no está disponible. Elige otro.", con el 10:00 seleccionado y "Continuar" activo. El evaluador no pudo saber en qué estado estaba el sistema ni si su selección era válida.
- Heurísticas: H1 (visibilidad del estado), H5 (prevención de errores), H9 (ayuda en errores). Severidad 3.
- Evidencias del caso: E3, E8 y E10.
- Hallazgo secundario: el Home dice "Aún no tienes tutorías reservadas", pero "Mis tutorías" lleva a una reserva confirmada (H4, severidad 3).

## 6. Mejora aplicada (antes y después)

| | Antes | Después |
|---|---|---|
| Descripción del cambio | Un solo cuadro con los tres mensajes y "Continuar" activo | La pantalla 2 principal muestra solo el estado "Horario seleccionado: jueves 10:00" y "Continuar". La carga y el error pasan a variantes separadas (2a: cargando, 2b: horario ya no disponible con el 10:00 marcado "Ocupado" y "Continuar" deshabilitado) |
| Captura | `prototipo/capturas/antes_pantalla2.png` | `prototipo/capturas/despues_pantalla2.png` |

Las variantes 2a y 2b documentan los estados definidos en la Actividad 4 (Retroalimentación), pero quedan fuera del recorrido navegable principal por la limitación de la sección 1.

## 7. Otros hallazgos 

| ID | Pantalla | Problema | Sev. |
|---|---|---|---|
| ERR-P1-01 | 1 y 4 | Home dice "Aún no tienes tutorías reservadas", pero "Mis tutorías" lleva a una reserva confirmada | 3 |
| ERR-P4-01 | 4 → 2 | "Cambiar horario" no muestra la cita actual ni aclara que reemplaza la anterior | 2 |
| ERR-GEN-01 | 2, 3, 4 | La fecha solo dice "Jueves", sin número de día ni mes | 2 |
| ERR-P3-01 | 3 | Modalidad en desplegable: "Virtual" queda oculta | 2 |
| ERR-P2-02 | 2 | "Sin cupos" frente a "Ocupado"; el día abierto no muestra que es expandible; posible bajo contraste | 2 |
| ERR-ACC-01 | 2 a 4 | No se ven en el prototipo el foco visible ni los nombres accesibles | 2 |
| ERR-P4-02 | 4 | Aviso del correo sin respaldo en E1–E10 y de tamaño pequeño | 1 |
| ERR-P1-02 | 1 y 4 | Jerarquía de botones; "UTA" y "Completado" sueltos | 1 |

## 8. Trazabilidad en GitHub

- Commit con el hallazgo y la mejora: ____________
- Issue / PR vinculado: ____________
