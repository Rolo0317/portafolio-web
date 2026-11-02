# Portafolio web — William Solano

Portafolio profesional de una sola página: perfil, logros, stack técnico, formación y certificados. Sirve para LinkedIn, procesos de selección y networking.

- **En línea:** https://Rolo0317.github.io/portafolio-web/
- **Publicación:** GitHub Pages, desde la rama `main`. Cada push publica.

## Estructura

Todo lo que enlaza la página vive en una sola ruta, `assets/`:

```
index.html                 Página completa
assets/css/                Estilos
assets/js/                 Interacciones
assets/img/                Foto del perfil
assets/docs/               Hoja de vida en PDF
assets/docs/certificados/  Un PDF por certificado
```

## Trabajar en local

Es un sitio estático: basta con abrir `index.html` en el navegador o servir la carpeta.

```bash
npx serve .
```

Las pautas de contenido y diseño están en `CLAUDE.md`.
