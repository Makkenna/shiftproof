# Cómo contribuir

El trabajo se divide en pasos pequeños y revisables. Antes de programar, confirme que el paso anterior y sus contratos están aprobados.

## Comenzar una tarea

```bash
git switch main
git pull origin main
git switch -c feat/pXX-descripcion
```

Reemplace `pXX-descripcion` por el número y un nombre breve, por ejemplo `p07-contratos`.

## Durante el trabajo

- Mantenga el cambio limitado al paso asignado.
- Acuerde nombres, entradas y salidas antes de modificar contratos compartidos.
- No suba contraseñas, tokens, datos personales, archivos `.env.local` ni credenciales de demostración.
- Use solo datos ficticios en pruebas, capturas y documentación pública.
- Añada o actualice la comprobación reproducible del cambio.

## Proponer un cambio

```bash
git status
git add RUTA_DE_LOS_ARCHIVOS
git commit -m "feat: describir el cambio"
git push -u origin HEAD
```

El pull request debe indicar:

- Paso al que corresponde.
- Qué se construyó.
- Archivos principales.
- Cómo repetir la comprobación.
- Limitaciones o trabajo pendiente.

La persona revisora repetirá el caso descrito. Edison integrará el cambio cuando la comprobación termine correctamente.

## Convención de ramas

- `feat/pXX-descripcion`: función o paso nuevo.
- `fix/pXX-descripcion`: corrección.
- `docs/pXX-descripcion`: documentación.
- `test/pXX-descripcion`: pruebas.

No se trabaja directamente sobre `main` después del primer commit.
