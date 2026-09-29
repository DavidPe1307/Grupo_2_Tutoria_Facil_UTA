# Evaluación heurística: Tutoría Fácil UTA

Grupo: ______D______  Paralelo: ______5to "B"______

Evaluación a Prototipo 1 (ANTES)

## 1. Método y alcance

- **Base:** guía de evaluación heurística de Nielsen (Semana6), guía de estilo de la Actividad 4 y rúbrica del examen.
- **Evaluadores:** un solo inspector.
- **Material inspeccionado:** las 4 pantallas del prototipo (Inicio, Elige un horario, Revisa tu tutoría, Reserva confirmada).
- **Flujo evaluado:** Reservar tutoría → Elige un horario → Continuar → Revisa tu tutoría → Confirmar → Reserva confirmada. Desde la última pantalla, "Cambiar horario" lleva a Elige un horario y "Volver al inicio" a Inicio. "Mis tutorías" lleva a Reserva confirmada.
- **Escala de severidad (Nielsen):** 0 = no es un problema, 1 = cosmético, 2 = menor, 3 = mayor, 4 = catástrofe.

### Limitación del prototipo

El prototipo es de fidelidad baja a media y **solo permite navegar por las opciones preestablecidas**. No es interactivo el cambio de horario (el 10:00 ya viene seleccionado), los días, los estados de carga y error (imágenes fijas) ni el desplegable de modalidad. Por eso, los criterios que dependen de comportamiento real quedan marcados como "No verificable" y no se evalúan como fallo.

## 2. Aspectos positivos

- El flujo completa la tarea: reservar, confirmar y llegar a "Cambiar horario".
- Los tres estados de horario (Disponible, Seleccionado, Ocupado) usan texto e icono además del color (POUR perceptible).
- Los mensajes de estado coinciden con los definidos en la Actividad 4.
- "Paso 1 de 2 / 2 de 2", "Completado" y "Volver" arriba a la izquierda orientan al usuario.
- La pantalla 3 permite revisar antes de confirmar (E10) y la pantalla 4 deja la confirmación inequívoca (E5).

## 3. Lista de chequeo (H1 a H10)

| ID | Heurística | Estado | Sev. | Observación |
|---|---|---|---|---|
| H1 | Visibilidad del estado del sistema | Fallo | 3 | La pantalla 2 mezcla carga, selección y error a la vez (ERR-P2-01) |
| H1.2 | Visibilidad del estado del sistema | Cumple | 0 | "Paso 1 de 2", "Paso 2 de 2" y "Completado" |
| H2 | Relación entre sistema y mundo real | Cumple | 1 | "Sin cupos" en los días frente a "Ocupado" en las horas: dos términos para lo mismo |
| H2.2 | Relación entre sistema y mundo real | Cumple | 0 | Días y horas en orden natural |
| H3 | Control y libertad del usuario | Cumple | 0 | "Volver" en las pantallas 2 y 3 |
| H3.2 | Control y libertad del usuario | No verificable | – | No se puede comprobar si el 10:00 sigue seleccionado al volver de la pantalla 3 |
| H4 | Consistencia y estándares | Fallo | 3 | "Mis tutorías" contradice el texto de Home (ERR-P1-01) |
| H4.2 | Consistencia y estándares | Parcial | 1 | Solo hay "Volver al inicio" en la pantalla 4; no hay otra ruta a Inicio |
| H5 | Prevención de errores | Fallo | 3 | "Continuar" queda activo con un error visible. Los horarios ocupados sí son no seleccionables (bien) |
| H5.2 | Prevención de errores | No verificable | – | El desplegable de modalidad no se puede abrir en el prototipo |
| H6 | Reconocimiento antes que recuerdo | Parcial | 2 | La fecha muestra solo "Jueves", sin número de día ni mes |
| H6.2 | Reconocimiento antes que recuerdo | Cumple | 0 | Todos los iconos llevan etiqueta de texto (E9) |
| H7 | Flexibilidad y eficiencia de uso | NA | – | Fuera del alcance móvil del caso |
| H8 | Diseño estético y minimalista | Parcial | 1 | "UTA" y "Completado" flotan arriba a la derecha sin función clara |
| H8.2 | Diseño estético y minimalista | Cumple | 0 | Horarios agrupados bajo cada día (Proximidad) |
| H8.3 | Diseño estético y minimalista | NA | – | No hay modales |
| H9 | Ayuda en errores | Parcial | 3 | El texto del error está bien redactado, pero mal ubicado (ERR-P2-01) |
| H10 | Ayuda y documentación | Cumple | 1 | Ayuda bajo el campo Modalidad; en el resto no hay |

## 4. Hallazgos

### ERR-P2-01. Estados contradictorios en la pantalla 2

- **Pantalla / módulo:** 2. Elige un horario
- **Heurística violada:** H1, H5, H9
- **Descripción:** se ven a la vez "Cargando disponibilidad…", "Horario seleccionado: jueves 10:00" y "Ese horario ya no está disponible. Elige otro.", con el 10:00 marcado como Seleccionado y "Continuar" activo. El usuario no sabe si puede avanzar.
- **Severidad:** 3 (problema mayor)
- **Principio de factor humano afectado:** carga cognitiva y visibilidad del estado.
- **Recomendación:** un estado por pantalla (cargando, seleccionado, error). En el estado de error, el 10:00 pasa a "Ocupado", se deselecciona y "Continuar" se deshabilita.
- **Evidencias del caso:** E3, E8, E10

### ERR-P1-01. "Mis tutorías" contradice el Home

- **Pantalla / módulo:** 1. Inicio y 4. Reserva confirmada
- **Heurística violada:** H4, H1
- **Descripción:** la pantalla 1 dice "Aún no tienes tutorías reservadas", pero "Mis tutorías" lleva a una reserva confirmada. Tras reservar, el Home seguiría diciendo lo mismo.
- **Severidad:** 3 (problema mayor)
- **Principio de factor humano afectado:** modelo mental del usuario.
- **Recomendación:** variante de Home con tarjeta "Próxima tutoría: Dra. Mónica Vega, jueves 10:00" y "Cambiar horario". "Mis tutorías" debe llevar a esa tarjeta o lista, no a "Reserva confirmada".
- **Evidencias del caso:** E5

### ERR-P4-01. "Cambiar horario" sin contexto de reprogramación

- **Pantalla / módulo:** 4 → 2
- **Heurística violada:** H1, H3, H5
- **Descripción:** "Cambiar horario" abre la misma pantalla de una reserva nueva. No muestra la cita actual ni aclara que reemplaza a la anterior.
- **Severidad:** 2 (problema menor)
- **Principio de factor humano afectado:** visibilidad del estado y reversibilidad.
- **Recomendación:** título "Cambiar horario", línea "Cita actual: jueves 10:00" y cambio de texto en el botón final.
- **Evidencias del caso:** E7, E10

### ERR-GEN-01. Fecha sin número de día

- **Pantalla / módulo:** 2, 3 y 4
- **Heurística violada:** H6, H2
- **Descripción:** solo dice "Jueves", sin número de día ni mes. E5 muestra que los estudiantes olvidan la fecha.
- **Severidad:** 2 (problema menor)
- **Principio de factor humano afectado:** memoria de trabajo.
- **Recomendación:** mostrar la fecha completa, por ejemplo "Jueves 2 de octubre".
- **Evidencias del caso:** E5

### ERR-P3-01. Modalidad en desplegable

- **Pantalla / módulo:** 3. Revisa tu tutoría
- **Heurística violada:** H6, H5
- **Descripción:** "Virtual" queda oculta dentro del desplegable y solo se explica en texto pequeño.
- **Severidad:** 2 (problema menor)
- **Principio de factor humano afectado:** reconocimiento antes que recuerdo.
- **Recomendación:** dos opciones visibles ("Presencial" / "Virtual") en selector segmentado o radios.

### ERR-P2-02. Días con apariencia ambigua

- **Pantalla / módulo:** 2. Elige un horario
- **Heurística violada:** H4, H2, H8
- **Descripción:** "Sin cupos" parece un botón deshabilitado, el día abierto no muestra que es expandible y el texto gris pequeño puede no llegar a 4.5:1.
- **Severidad:** 2 (problema menor)
- **Principio de factor humano afectado:** affordance y semejanza.
- **Recomendación:** chevron en los días, mismo término para lo no disponible ("Ocupado" o "Sin horarios") y contraste comprobado.

### ERR-ACC-01. Accesibilidad no visible en el prototipo

- **Pantalla / módulo:** 2 a 4
- **Heurística violada:** POUR (rúbrica de accesibilidad)
- **Descripción:** no se ven en las capturas el foco visible, el orden de teclado ni los nombres accesibles. La rúbrica marca "la accesibilidad no se observa en el prototipo" como logro insuficiente.
- **Severidad:** 2 (problema menor)
- **Principio de factor humano afectado:** operabilidad y robustez.
- **Recomendación:** versión con foco visible de 3 px #1D3A8A y anotaciones de nombres accesibles, por ejemplo "Jueves 10:00, disponible".
- **Evidencias del caso:** E2

### ERR-P4-02. Aviso de correo sin respaldo

- **Pantalla / módulo:** 4. Reserva confirmada
- **Heurística violada:** H4
- **Descripción:** el aviso del correo electrónico no está respaldado por E1–E10 y parece menor a los 14 px de la guía de estilo.
- **Severidad:** 1 (cosmético)
- **Recomendación:** quitarlo o justificarlo con evidencia, y subir el tamaño.

### ERR-P1-02. Jerarquía de botones y textos sueltos

- **Pantalla / módulo:** 1 y 4
- **Heurística violada:** H8, H4
- **Descripción:** en Inicio, "Reservar tutoría" y "Mis tutorías" pesan igual. En la pantalla 4, "Volver al inicio" pesa más que "Cambiar horario". "UTA" y "Completado" flotan arriba a la derecha sin función clara.
- **Severidad:** 1 (cosmético)
- **Recomendación:** "Mis tutorías" y "Cambiar horario" como secundarios; "UTA" al logo o fuera; "Completado" como indicador de paso.

## 5. Cumplimiento de la guía de estilo (Actividad 4)

| Elemento de la guía | Estado | Nota |
|---|---|---|
| Horario disponible (borde azul, "10:00 · Disponible") | Cumple | |
| Horario seleccionado (fondo azul, check, "Seleccionado") | Cumple | |
| Horario ocupado (gris, sin borde, "13:00 · Ocupado") | Cumple | Añade un icono de candado |
| Botón principal 48 px, ancho completo, y secundario | Cumple | |
| Mensajes de estado exactos | Cumple | Los cuatro aparecen |
| Términos consistentes | Parcial | "Continuar" no está en la lista de términos; "Sin cupos" frente a "Ocupado" |
| "Volver" siempre arriba a la izquierda | Parcial | Falta en las pantallas 1 y 4; en la 3 además hay un "Volver" abajo |
| Texto auxiliar de 14 px | A verificar | El aviso del correo parece menor |

## 6. Prioridad de corrección

1. **ERR-P2-01 y ERR-P1-01** (severidad 3): son los que un compañero notaría en la prueba cruzada.
2. Usar uno de ellos (o ERR-GEN-01) como hallazgo y mejora aplicada de la iteración, con capturas antes y después, documentado en `evaluacion/prueba_iteracion.md`.
3. **ERR-ACC-01:** añadir una captura o anotación de accesibilidad para que POUR sea visible en el prototipo.
4. El resto (severidad 1 y 2) se documenta como pendiente para una siguiente iteración.

