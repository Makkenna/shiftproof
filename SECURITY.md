# Seguridad

## Datos que nunca deben publicarse

No incluya en este repositorio:

- claves API de producción;
- secretos o credenciales de Google Cloud;
- tokens de depuración de Firebase App Check;
- contraseñas de cuentas de demostración;
- datos personales o notas operativas reales;
- archivos `.env` con valores;
- exportaciones de emuladores que contengan datos sensibles.

Use cuentas, nombres y notas ficticias en los casos de demostración.

## Configuración local

Cuando exista `web/.env.example`, cópielo como `web/.env.local` y complete los valores únicamente en su equipo. `.env.local` no debe añadirse a Git.

Los tokens de depuración de App Check se registran en Firebase Console y permanecen fuera del código, las capturas, los registros y la documentación pública.

## Reportar un problema

No publique vulnerabilidades, credenciales o datos sensibles en un issue.

Use la función de reporte privado de vulnerabilidades de GitHub cuando esté habilitada. Si no está disponible, contacte en privado al representante del equipo mediante el canal registrado en Devpost.

## Respuesta inmediata ante una filtración

1. Retire el dato del repositorio y de cualquier instrucción pública.
2. Revoque o rote la credencial afectada.
3. Revise el historial de uso y App Check.
4. Informe al equipo.
5. Documente la corrección sin reproducir el secreto.
