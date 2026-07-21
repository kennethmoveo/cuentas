# Cuentas

App personal de ingresos, gastos fijos y variables, ahorros e inversiones.
Un solo archivo (`index.html`), sin backend, sin cuentas. Los datos viven en tu teléfono.
Precargada con tu histórico Ene–Jul 2026 y tu reparto real (GF 27.5% · GV 30% · Ahorro 30% · Inv 12.5%).

## Archivos

```
index.html        La app completa (HTML + CSS + JS)
manifest.json     Metadatos de la PWA (nombre, colores, iconos)
sw.js             Service worker: funciona sin internet una vez instalada
icons/            Iconos de la app (192, 512, 180 apple-touch, 32 favicon)
.nojekyll         Evita que GitHub Pages procese los archivos
```

## Ponerla en tu iPhone (GitHub Pages, gratis)

1. Crea un repo nuevo en GitHub, por ejemplo `cuentas`.
2. Sube **todo** el contenido de esta carpeta a la raíz del repo
   (arrastra los archivos en *Add file → Upload files*, o `git push`).
3. En el repo: **Settings → Pages**.
   - *Source*: **Deploy from a branch**
   - *Branch*: **main** · carpeta **/ (root)** → **Save**.
4. Espera ~1 minuto. Aparecerá la URL:
   `https://TU-USUARIO.github.io/cuentas/`
5. Abre esa URL **en Safari** (en el iPhone).
6. Botón **Compartir** → **Añadir a pantalla de inicio** → *Añadir*.

Ya tienes el icono en la pantalla de inicio. Se abre a pantalla completa,
funciona sin conexión y guarda tus datos en el teléfono.

### Con git (alternativa al arrastrar-y-soltar)

```bash
git init
git add .
git commit -m "Cuentas"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/cuentas.git
git push -u origin main
```

Luego activa Pages como en el paso 3.

## Actualizar la app más adelante

Si cambias `index.html` o los iconos, sube el cambio y **sube la versión**
de la caché en dos sitios para que el teléfono la recoja:

- `sw.js`: cambia `const CACHE = 'cuentas-v1'` → `'cuentas-v2'`.

Cierra y reabre la app un par de veces y cargará la versión nueva.

## Copias de seguridad (importante)

Los datos se guardan solo en el navegador de tu teléfono. Si borras los datos
de Safari o quitas la app, se pierden. Dentro de la app:

- **Más → Copia de seguridad**: descarga un `.json` con todo. Guárdalo cada tanto.
- **Más → Exportar a Excel/Sheets**: descarga un `.csv` con los movimientos.
- **Más → Restaurar copia**: vuelve a cargar un `.json`.

## Notas honestas

- **No hay conexión con Apple Wallet.** Apple no deja que ninguna app lea tus
  cargos. El registro es manual; el contador de "días sin registrar" es el
  recordatorio realista.
- **Recordatorios push** en iPhone solo funcionan con la app añadida a la
  pantalla de inicio (iOS 16.4+) y son limitados. La app avisa cuando está abierta.
