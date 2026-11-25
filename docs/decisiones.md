# Decisiones del proyecto

Este archivo registra decisiones que afectan el alcance, la arquitectura, la seguridad o la demostración. Las decisiones iniciales se ratificarán con Edison y Angeles al revisar el Paso 01.

Cada nueva decisión debe indicar fecha, responsable, estado, motivo y evidencia necesaria.

## D001: plataforma inicial

- Fecha: 24 de noviembre de 2026
- Responsable: Equipo Relevo de Turno
- Estado: Propuesta para ratificación
- Decisión: Construir primero una aplicación web para Chrome.
- Motivo: Permite demostrar Gemini Nano 4 mediante Firebase AI Logic y ofrecer una URL de prueba al jurado.
- Evidencia: Una solicitud nueva ejecutada en el dispositivo y otra mediante el respaldo en la nube.

## D002: inferencia híbrida

- Fecha: 24 de noviembre de 2026
- Responsable: Makena Reyes
- Estado: Propuesta para ratificación
- Decisión: Usar `firebase/ai` con `PREFER_ON_DEVICE`.
- Motivo: Mantiene la preparación del relevo sin conexión cuando el modelo local está disponible y usa la nube como respaldo.
- Evidencia: Registrar `ON_DEVICE` e `IN_CLOUD` desde `inferenceSource`.

## D003: revisión humana

- Fecha: 24 de noviembre de 2026
- Responsable: Equipo Relevo de Turno
- Estado: Propuesta para ratificación
- Decisión: Ninguna sugerencia de IA se publica automáticamente.
- Motivo: La persona saliente debe comprobar el fragmento, corregir los campos y vincular la tarea.
- Evidencia: La interfaz permite editar, eliminar y crear un pendiente manual.

## D004: datos del prototipo

- Fecha: 24 de noviembre de 2026
- Responsable: Equipo Relevo de Turno
- Estado: Propuesta para ratificación
- Decisión: Usar únicamente cuentas, tareas y notas ficticias.
- Motivo: El repositorio, Devpost y las instrucciones de prueba no deben contener datos personales ni secretos.
- Evidencia: Revisión de seguridad antes de cada publicación.

## D005: alcance inicial

- Fecha: 24 de noviembre de 2026
- Responsable: Makena Reyes
- Estado: Propuesta para ratificación
- Decisión: Priorizar editor, inferencia híbrida, revisión, publicación, recepción y una discrepancia demostrable.
- Motivo: Ese recorrido aporta evidencia para los cuatro criterios de evaluación.
- Evidencia: Prueba completa con dos cuentas y dos reportes incompatibles del mismo corte.

## Lista antes de fusionar

- [ ] El cambio pertenece al alcance aprobado.
- [ ] No contiene secretos, tokens, contraseñas ni datos personales.
- [ ] La función puede probarse de forma reproducible.
- [ ] La documentación indica qué se construyó durante el concurso.
- [ ] Las dependencias y el código previo incorporado están declarados.
