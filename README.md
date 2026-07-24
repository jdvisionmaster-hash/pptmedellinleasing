# El leasing financiero en la insolvencia de la persona natural

Wiki navegable de la conferencia jurídica de **Atria Abogados** ("El leasing financiero en la insolvencia de la persona natural — No comerciante y pequeña comerciante"), con buscador local (sin API ni LLM) y modo de presentación en pantalla completa.

Sitio 100% estático — `index.html` + las imágenes `img-01...` a `img-18...` sueltas en la misma carpeta (sin subcarpetas, para poder subirlas todas de una con el selector normal de archivos de GitHub). No requiere build ni servidor backend.

## Estructura

```
index.html      → la presentación completa (slides + buscador + botón de pantalla completa)
img-01...18...  → imágenes referenciadas por index.html (todas sueltas, sin carpeta assets/)
vercel.json     → configuración de caché para las imágenes en Vercel
```

## Probar en local

```bash
python3 -m http.server 8080
```

y abrir `http://localhost:8080`. (Abrir el archivo directamente con doble clic también funciona.)

## Desplegar en GitHub

Desde esta carpeta:

```bash
git init
git add .
git commit -m "Publicar wiki de la conferencia"
git branch -M main
git remote add origin https://github.com/<tu-usuario>/<nombre-del-repo>.git
git push -u origin main
```

(Antes hay que crear el repositorio vacío en GitHub, sin README/licencia, para que el push no choque con nada.)

## Desplegar en Vercel

1. Entrar a [vercel.com/new](https://vercel.com/new) e importar el repositorio de GitHub recién creado.
2. Framework Preset: **Other** (sitio estático, sin build command, sin output directory especial — Vercel detecta `index.html` en la raíz automáticamente).
3. Deploy. No hace falta configurar variables de entorno ni comandos de build.

Cada push a `main` vuelve a desplegar automáticamente.
