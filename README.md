# Relevo de Turno

Aplicación web para preparar, publicar y recibir relevos verificables entre equipos que trabajan por turnos.

La persona saliente escribe una nota como lo hace habitualmente. Firebase AI Logic con Gemini Nano 4 propone pendientes y conserva el fragmento que respalda cada sugerencia. Antes de publicar, la persona revisa y corrige el resultado. Si dos reportes del mismo corte describen una tarea con estados incompatibles, coordinación consulta ambas fuentes y registra qué estado debe quedar vigente y por qué.

Proyecto en desarrollo para **#BuildHybridAI 2026**.

## Estado actual

**Paso 01 listo para validación del equipo: definición del caso y los datos del piloto.**

Ya están documentados:

- El puesto, los turnos y los momentos de corte.
- Las tareas y notas canónicas de las pruebas.
- Los roles de quien entrega, recibe y resuelve una discrepancia.
- El recorrido obligatorio y los límites del MVP.
- Las comparaciones que deben generar o evitar una discrepancia.

Responsable del paso: **Makena Reyes**. Revisa: **Edison Cárdenas**.

Todavía no existe una versión funcional. El equipo debe confirmar este caso antes de comenzar la implementación compartida.

## Caso inicial

El piloto representa el puesto **Acceso norte** de un evento universitario.

- Turnos: `Saliente` y `Entrante`
- Corte inicial: `16:30`
- Corte posterior: `17:30`
- Tarea principal: `AC-07 Entregar credenciales del acceso norte`
- Conflicto de prueba: un reporte indica que quedan 20 credenciales y otro, del mismo corte, que todas fueron entregadas.
- Resolución: coordinación conserva ambas fuentes y registra el estado confirmado y su motivo.

Los detalles están en [alcance del piloto](docs/alcance.md) y [casos de demostración](docs/casos-demo.md).

## Recorrido del MVP

1. La persona saliente abre un borrador y escribe una nota.
2. Firebase AI Logic propone pendientes y conserva el fragmento de respaldo.
3. La persona revisa, corrige o completa manualmente las sugerencias.
4. El relevo se publica y el turno entrante registra su recepción.
5. Si dos reportes de la misma tarea y corte se contradicen, coordinación revisa las fuentes y registra una decisión.

## Evidencia que debe producir el prototipo

- Una solicitud nueva ejecutada `ON_DEVICE`.
- Una solicitud nueva ejecutada `IN_CLOUD`.
- Un borrador recuperado después de recargar sin conexión.
- Una sugerencia corregida antes de publicar.
- Un relevo publicado y recibido por otra cuenta.
- Una contradicción que conserva las dos fuentes.
- Una decisión con autor, motivo y hora.
- El recorrido central disponible en inglés.

## Tecnologías previstas

- React, TypeScript y Vite
- Firebase AI Logic y Gemini Nano 4
- Firebase Authentication, Cloud Firestore, App Check y Hosting
- IndexedDB, Zod y Vitest
- Firebase Emulator Suite

La selección podrá ajustarse después de completar la primera prueba de inferencia híbrida.

## Equipo

- **Edison Cárdenas:** Firebase, datos compartidos, permisos, despliegue e integración en `main`.
- **Angeles Bernal:** interfaz, sesión, borradores, revisión, bandeja, funcionamiento sin conexión y video.
- **Makena Reyes:** flujo de producto, contratos, IA híbrida, detección de discrepancias, pruebas y piloto.

Cada cambio tendrá una persona responsable y otra que repita la comprobación antes de integrarlo.

## Cómo colaborar

Lea [CONTRIBUTING.md](CONTRIBUTING.md) antes de comenzar una tarea. Nunca publique contraseñas, tokens, archivos `.env.local`, datos personales ni credenciales de demostración.

## Próximos pasos

1. Edison y Angeles revisan y confirman el Paso 01.
2. El equipo completa sus accesos de GitHub y Devpost.
3. Se crea la base de React y Firebase.
4. Makena propone los contratos compartidos del Paso 07.
5. El equipo comprueba una solicitud nueva en dispositivo y otra en nube.

## Documentación

- [Alcance del piloto](docs/alcance.md)
- [Casos de demostración](docs/casos-demo.md)
- [Decisiones del proyecto](docs/decisiones.md)
- [Política de seguridad](SECURITY.md)

## Trabajo previo

No se incorpora código previo al período del concurso en este primer commit. Si se añade posteriormente, se declarará aquí y en la documentación de la entrega.

## Idioma de la entrega

Este README inicial está en español para coordinar el trabajo del equipo. Antes de la entrega se publicará un README principal en inglés con instalación, configuración, recorrido de prueba, arquitectura, resultados del piloto y uso de Firebase AI Logic.

## Licencia

Este proyecto se distribuye bajo Apache License 2.0. Consulte [LICENSE](LICENSE).
