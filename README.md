# Terra PSCJ · Sitio web publicado con GitHub

GitHub es el **hosting** (GitHub Pages), la **base de datos** (archivos JSON en `data/`) y el **historial** de cambios.
No necesitas servidor propio.

```
index.html            página pública          data/propiedades.json   propiedades (base de datos)
admin.html            panel de administración data/config.json        WhatsApp, teléfono y redes
imagenes/  video/     multimedia              datos/Registro_Terra_PSCJ.xlsx   Excel (se actualiza solo)
scripts/ + .github/   generador del Excel (GitHub Actions)
```

## 1. Publicar (una sola vez)
1. Crea una cuenta en github.com y un repositorio **público** llamado `terra-pscj` (GitHub Pages gratis requiere repositorio público).
2. Sube esta carpeta:
   - **Con GitHub Desktop:** File → Add local repository (elige esta carpeta; si pide, “create a repository”) → Commit → **Publish repository** (desmarca “Keep this code private”).
   - **Desde la web:** en el repositorio, Add file → Upload files y arrastra todo el contenido. La carpeta oculta `.github` puede no subirse: crea el archivo con Add file → Create new file, nombre `.github/workflows/excel.yml`, y pega el contenido de `scripts/workflow-excel.yml`.
3. Settings → **Pages** → Source: “Deploy from a branch” → Branch: `main` / `(root)` → Save.
4. En 1–2 minutos tu sitio estará en `https://TU-USUARIO.github.io/terra-pscj/`.

## 2. Entrar como administrador
1. GitHub → tu foto → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate new token.
2. Repository access: *Only select repositories* → `terra-pscj`. Permissions → Repository permissions → **Contents: Read and write**. Genera y copia el token.
3. Abre `https://TU-USUARIO.github.io/terra-pscj/admin.html`, escribe `TU-USUARIO/terra-pscj` y pega el token.

El token es tu contraseña: no lo compartas ni lo pegues en el repositorio. Se guarda solo mientras la pestaña está abierta.
**Más administradores:** pestaña Administradores → Invitar (se añaden como colaboradores de GitHub; cada uno crea su propio token).

## 3. Qué puedes hacer en el panel
Crear, editar y borrar propiedades (con foto, precio, área, estado), cambiar WhatsApp, teléfono e Instagram/Facebook/TikTok, ver el historial de quién cambió qué y descargar el Excel.
Cada guardado es un commit y la página se actualiza sola en 1–2 minutos.

## 4. Excel
`datos/Registro_Terra_PSCJ.xlsx` se regenera automáticamente con cada cambio en `data/` (pestaña Actions del repositorio). También puedes descargarlo desde el panel.

## Importante
- El repositorio es público: **no guardes datos personales de clientes** en él. Las consultas del formulario se envían por WhatsApp.
- Con un dominio propio: Settings → Pages → Custom domain.
