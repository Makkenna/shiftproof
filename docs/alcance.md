# Alcance del piloto Relevo de Turno

## Propósito

El piloto comprobará si una aplicación puede ayudar a preparar, recibir y verificar un relevo entre dos turnos de un puesto de acreditación. La aplicación convierte notas breves en pendientes revisables, conserva el fragmento que respalda cada sugerencia y permite resolver reportes contradictorios sin ocultar sus fuentes.

La IA propone información, pero no decide el estado de una tarea. La persona saliente revisa qué publica y la coordinación confirma el estado aplicable cuando existen versiones incompatibles.

## Contexto de demostración

- Evento: evento universitario de demostración
- Puesto principal: Acceso norte
- Turnos: Saliente y Entrante
- Corte inicial: 16:30
- Corte posterior: 17:30
- Perfiles: persona que entrega, persona que recibe y coordinación
- Tareas de referencia: AC-07, AC-08 y AC-09

El corte identifica el momento descrito por cada reporte. Dos notas solo se comparan como posibles versiones contradictorias cuando están vinculadas a la misma tarea y al mismo corte.

## Recorrido obligatorio

1. La persona saliente abre un borrador para el puesto y el corte activo.
2. Escribe una nota con sus propias palabras.
3. La aplicación propone hasta cinco pendientes y conserva el fragmento que respalda cada uno.
4. La persona revisa los campos, corrige lo necesario y vincula cada ítem a una tarea.
5. El relevo se publica una sola vez y queda visible para el turno entrante.
6. La persona que recibe abre el relevo y registra su recepción.
7. Si dos reportes de la misma tarea y corte indican estados incompatibles, la aplicación muestra ambas versiones.
8. La coordinación consulta las fuentes, elige el estado aplicable y registra un motivo.
9. Una actualización de un corte posterior permanece separada de la decisión anterior.

## Reglas del piloto

- Los estados reportados son `pendiente`, `completada` y `sin_dato`.
- Un estado solo se infiere cuando la nota lo expresa de manera comprobable.
- Si falta responsable u hora, el campo permanece vacío.
- Cada sugerencia debe incluir un fragmento literal de la nota.
- La persona puede corregir, eliminar o añadir ítems antes de publicar.
- Publicar y recibir son acciones diferentes.
- Recibir confirma lectura; no confirma que la tarea esté completada.
- Solo coordinación puede confirmar el estado de una tarea.
- Los reportes publicados no se sobrescriben.
- Una corrección posterior se registra como un nuevo reporte.
- Una tarea distinta o un corte distinto no debe producir la misma alerta.
- Los borradores y credenciales de prueba no se publican en el repositorio.

## Alcance incluido

- Acceso con cuentas de demostración
- Borrador local recuperable
- Generación híbrida con origen visible
- Revisión y captura manual
- Publicación y recepción
- Comparación por tarea y corte
- Resolución con motivo e historial
- Recorrido central en español e inglés

## Fuera del alcance inicial

- Notificaciones automáticas
- Turnos configurables por administradores
- Plantillas para varias actividades
- Aplicación móvil nativa
- Integraciones con sistemas externos
- Uso de datos reales o información personal
- Automatización de la decisión final

Estas funciones solo se considerarán después de completar y probar el recorrido obligatorio.

## Criterios de aceptación

El piloto se considera completo cuando:

- Dos cuentas acceden al mismo espacio y una cuenta ajena no puede leerlo.
- Un borrador conserva su identificador y texto después de recargar.
- Una solicitud nueva funciona en el dispositivo sin internet.
- Otra solicitud nueva utiliza el respaldo en la nube.
- La interfaz muestra `ON_DEVICE` o `IN_CLOUD` según la respuesta real.
- La persona puede revisar, corregir y completar a mano las sugerencias.
- Un reintento de publicación no crea un segundo relevo.
- El turno entrante puede registrar la recepción.
- Los reportes opuestos de AC-07 a las 16:30 generan una discrepancia.
- El reporte de AC-07 a las 17:30 no se mezcla con el corte anterior.
- El reporte de AC-09 no genera una alerta para AC-07.
- Coordinación registra una decisión con estado, motivo, autor y hora.
