# Portafolio web — William Danilo Solano Álvarez

Portafolio de una sola página, estático, para reclutadores y clientes freelance. Presenta a William como **analista de datos (Continautos, desde nov 2026) y desarrollador full stack (SurgirIA)**.

**URL pública:** https://rolo0317.github.io/portafolio-web/ (GitHub Pages, rama `main`, raíz `/`; cada push publica)

## Estructura: todo bajo `assets/`

```
index.html                       Página completa
assets/css/styles.css            Estilos (tokens en :root)
assets/js/main.js                Menú móvil, aparición al hacer scroll, botón flotante
assets/img/foto_corporativa.jpeg Foto del perfil (1024×1536)
assets/docs/hoja-de-vida-william-solano.pdf
assets/docs/certificados/*.pdf   Un PDF por certificado, nombres en minúscula con guiones
```

Regla: **ningún archivo fuera de `assets/`** salvo `index.html` y la documentación. Toda ruta en el HTML empieza por `assets/`.

### De dónde salen los archivos
- **Hoja de vida:** copia de `../hoja_de_vida/sitio/cv_william_solano.pdf`, que es la fuente. Cuando cambie, se vuelve a copiar aquí con el mismo nombre.
- **Certificados:** los originales están en `C:\Users\millo\Proyectos\documentos_personales\02_estudios (no vencen)\`.
- **Datos de experiencia y certificaciones:** salen de la hoja de vida (`../hoja_de_vida/sitio/index.html`). No se inventan cifras: las de la página (−40 %, 2,5 h diarias, 4 campañas) vienen de allí.

## Agregar un certificado
1. Copiar el PDF a `assets/docs/certificados/` con un nombre como `tema-institucion.pdf`.
2. Agregar un `<li class="reveal">` en `.cert-list`, dentro de `#certificados`, con el nombre, la institución, las horas y la fecha.

## Diseño
- Mundo oscuro (fondo `#0B0F14`) con acento cian `#38BDF8` y verde `#22C55E` para WhatsApp. Fuentes: Space Grotesk para títulos e Inter para el texto.
- Sin etiquetas pequeñas encima de los títulos y sin emojis como íconos. Experiencia, servicios y certificados van en listas con líneas finas; las tarjetas quedan solo para proyectos y stack.
- El botón flotante de WhatsApp solo aparece en celular y después del hero.
- La animación de aparición solo se aplica con JS (clase `js` en `<html>`) y respeta `prefers-reduced-motion`.

## Local
`python -m http.server 8080` o `npx serve .` y abrir http://localhost:8080
