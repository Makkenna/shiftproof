# Casos de demostración Relevo de Turno

## Datos compartidos

### Evento y puesto

| Campo | Valor |
| --- | --- |
| Evento | Evento universitario |
| Puesto principal | Acceso norte |
| Turno que entrega | Saliente |
| Turno que recibe | Entrante |
| Corte inicial | 16:30 |
| Corte posterior | 17:30 |

### Tareas

| ID | Tarea | Zona |
| --- | --- | --- |
| AC-07 | Entregar credenciales del acceso norte | Acceso norte |
| AC-08 | Recoger la caja de gafetes | Acceso norte |
| AC-09 | Preparar listado del acceso sur | Acceso sur |

Los identificadores, nombres y zonas deben mantenerse iguales en la aplicación, las pruebas y el video.

## Notas canónicas

### N01: pendiente del corte inicial

- Autor de prueba: Saliente
- Turno: Saliente
- Corte: 16:30
- Tarea vinculada: AC-07

> Al corte de las 16:30, quedan 20 credenciales del acceso norte por entregar.

| Campo | Valor esperado |
| --- | --- |
| Título | Entregar credenciales del acceso norte |
| Estado reportado | pendiente |
| Responsable mencionado | vacío |
| Hora mencionada | 16:30 |
| Fragmento | quedan 20 credenciales del acceso norte por entregar |

### N02: versión opuesta del mismo corte

- Autor de prueba: Coordinación
- Turno: Entrante
- Corte: 16:30
- Tarea vinculada: AC-07

> Al corte de las 16:30, se entregaron todas las credenciales del acceso norte.

| Campo | Valor esperado |
| --- | --- |
| Título | Entregar credenciales del acceso norte |
| Estado reportado | completada |
| Responsable mencionado | vacío |
| Hora mencionada | 16:30 |
| Fragmento | se entregaron todas las credenciales del acceso norte |

N01 y N02 deben producir una discrepancia porque describen la misma tarea y el mismo corte con estados incompatibles.

### N03: actualización del corte posterior

- Autor de prueba: Saliente
- Turno: Saliente
- Corte: 17:30
- Tarea vinculada: AC-07

> Al corte de las 17:30, se entregaron las 20 credenciales que quedaban en el acceso norte.

| Campo | Valor esperado |
| --- | --- |
| Título | Entregar credenciales del acceso norte |
| Estado reportado | completada |
| Responsable mencionado | vacío |
| Hora mencionada | 17:30 |
| Fragmento | se entregaron las 20 credenciales que quedaban |

N03 representa progreso posterior. No debe incorporarse a la discrepancia de las 16:30.

### N04: tarea de otra zona

- Autor de prueba: Saliente
- Turno: Saliente
- Corte: 16:30
- Tarea vinculada: AC-09

> Al corte de las 16:30, falta preparar el listado del acceso sur para el siguiente turno.

| Campo | Valor esperado |
| --- | --- |
| Título | Preparar listado del acceso sur |
| Estado reportado | pendiente |
| Responsable mencionado | vacío |
| Hora mencionada | 16:30 |
| Fragmento | falta preparar el listado del acceso sur |

N04 no debe producir una discrepancia con N01 o N02 porque corresponde a otra tarea y otra zona.

## Comparaciones esperadas

| Comparación | Resultado esperado | Motivo |
| --- | --- | --- |
| N01 con N02 | Discrepancia | Misma tarea y corte; estados pendiente y completada |
| N01 con N03 | Sin la misma alerta | Misma tarea, pero corte posterior |
| N02 con N03 | Sin la misma alerta | Misma tarea, pero corte posterior |
| N01 con N04 | Sin discrepancia | Tareas y zonas diferentes |
| N02 con N04 | Sin discrepancia | Tareas y zonas diferentes |
| Dos reportes pendientes de AC-07 a las 16:30 | Sin discrepancia | Estados compatibles |

## Decisión de demostración

Para resolver la discrepancia entre N01 y N02, coordinación registra:

| Campo | Valor |
| --- | --- |
| Tarea | AC-07 |
| Corte | 16:30 |
| Estado confirmado | pendiente |
| Reportes revisados | N01 y N02 |
| Motivo | Verifiqué el registro de recepción y quedan 20 credenciales. Coordinación retoma la entrega. |

La decisión debe conservar ambas notas como fuentes. N03 permanece como una actualización posterior y puede confirmar que la tarea se completó a las 17:30.

## Casos de control

- Nota ambigua: `Creo que ya quedó.`  
  Resultado esperado: `sin_dato` o revisión manual.
- Nota sin responsable: `Faltan credenciales por entregar.`  
  Resultado esperado: responsable vacío.
- Nota sin hora: `Quedan 20 credenciales del acceso norte por entregar.`  
  Resultado esperado: hora mencionada vacía; el corte se selecciona por separado.
- Respuesta sin fragmento literal.  
  Resultado esperado: rechazar la sugerencia y conservar la nota para captura manual.
- Reintento del mismo borrador.  
  Resultado esperado: devolver el relevo existente y no crear un duplicado.
