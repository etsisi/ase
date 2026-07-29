# Microcredencial en Ingeniería de Software Agéntica — ETSISI/UPM

Página web estática de la microcredencial, publicada con GitHub Pages (Jekyll).

## Estructura

```
├── index.html      Página principal (front matter + HTML/Tailwind)
├── 404.html        Página de error personalizada
├── _config.yml     Configuración de Jekyll  ← ajustar url y baseurl
├── robots.txt      Indexación + referencia al sitemap
├── Gemfile         Entorno local equivalente al de GitHub Pages
└── .gitignore
```

## Antes del primer despliegue

Edita `_config.yml` y ajusta `url` y `baseurl`:

- Sitio de **proyecto** (`https://usuario.github.io/mi-repo/`):
  `url: "https://usuario.github.io"` y `baseurl: "/mi-repo"`
- Sitio de **usuario** (`https://usuario.github.io/`, repo llamado `usuario.github.io`):
  `url: "https://usuario.github.io"` y `baseurl: ""`

## Publicar

```bash
git init -b main
git add .
git commit -m "Publicación inicial de la web de la microcredencial"
git remote add origin https://github.com/USUARIO/REPO.git
git push -u origin main
```

Después, en GitHub: **Settings → Pages → Build and deployment → Source:
Deploy from a branch → Branch: `main` / `(root)` → Save**.

En 1–3 minutos la página estará disponible. El estado de cada build se ve en
la pestaña **Actions** (`pages build and deployment`).

## Vista previa local (opcional)

```bash
bundle install
bundle exec jekyll serve --livereload
# http://127.0.0.1:4000/mi-repo/
```

Requiere Ruby ≥ 3.1 y Bundler. `_site/` es la salida del build y no se versiona.

## Actualizar contenidos

```bash
git add index.html
git commit -m "Actualiza fechas de la convocatoria"
git push
```

Cada `push` a `main` regenera el sitio automáticamente.
