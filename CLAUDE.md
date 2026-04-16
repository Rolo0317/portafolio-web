# Portafolio Web — William Danilo Solano Álvarez

## Propósito del proyecto

Portafolio web profesional de una sola página (SPA estática) para William Danilo Solano Álvarez, Data Analyst en GROUPCOS. Su objetivo es servir como presencia digital profesional para compartir en LinkedIn, procesos de selección y networking técnico. Está diseñado para comunicar logros cuantificables, stack técnico y formación de manera visual y rápida.

---

## Estructura de archivos

```
portafolio-web/
└── index.html        # Único archivo del proyecto — HTML, CSS y JS embebidos
```

No hay dependencias externas, frameworks, ni pasos de compilación. Todo vive en `index.html`.

---

## Datos del perfil

| Campo            | Valor                                  |
|------------------|----------------------------------------|
| Nombre completo  | William Danilo Solano Álvarez          |
| Rol              | Data Analyst                           |
| Email            | Daniloalvarez1719@gmail.com            |
| Teléfono         | +57 320 391 4473                       |
| Empresa actual   | GROUPCOS (2020 – actualidad)           |

### Logros destacados

- Reducción del **40%** en tiempos de reportería mediante automatización con Python
- Dashboards interactivos en Power BI para decisiones en tiempo real
- Integración de datos desde múltiples fuentes (APIs REST, SQL, archivos)
- Implementación de flujos de IA generativa para clasificación y procesamiento

### Stack técnico

| Categoría        | Tecnologías                                          |
|------------------|------------------------------------------------------|
| Lenguajes        | Python, SQL, JavaScript                              |
| Datos            | Pandas, NumPy, Matplotlib                            |
| Bases de datos   | MySQL, PostgreSQL, Redis                             |
| Visualización    | Power BI, Excel Avanzado                             |
| Infraestructura  | Docker, APIs REST, Git                               |
| Front-End        | HTML, CSS                                            |
| IA               | IA Generativa, LLMs, Pipelines IA                   |

### Formación

| Año  | Título                                             | Institución                  |
|------|----------------------------------------------------|------------------------------|
| 2025 | Desarrollo Web Front-End                           | Universidad de los Andes     |
| 2024 | Power BI — Análisis y Visualización de Datos       | CET Colsubsidio              |
| 2022 | Excel Avanzado                                     | CET Colsubsidio              |
| 2020 | Técnico en Operaciones Comerciales y Financieras   | SENA                         |

---

## Secciones del portafolio

| ID sección   | Contenido                                                            |
|--------------|----------------------------------------------------------------------|
| `#hero`      | Nombre, rol, badge animado, stat chips, CTA y avatar giratorio       |
| `#sobre`     | Bio en prosa, cita destacada, tarjetas de datos de contacto          |
| `#logros`    | 6 cards con métricas grandes y descripción de impacto                |
| `#stack`     | 7 categorías de tags + barras de habilidad animadas al scroll        |
| `#formacion` | Timeline vertical con 4 entradas educativas                          |
| `#contacto`  | Links directos + formulario con fallback a `mailto:`                 |

---

## Decisiones de diseño

### Paleta de colores (dark professional)

```css
--bg-primary:   #0f172a   /* fondo base — Slate 900   */
--bg-secondary: #1e293b   /* fondo alterno — Slate 800 */
--bg-card:      #1e293b   /* tarjetas                  */
--accent:       #38bdf8   /* cyan principal — Sky 400  */
--accent-2:     #818cf8   /* índigo secundario         */
--text-primary: #f1f5f9   /* texto — Slate 100         */
--text-muted:   #94a3b8   /* texto secundario — Slate 400 */
--border:       #334155   /* bordes — Slate 700        */
```

Paleta inspirada en herramientas de datos como Grafana y VS Code Dark+. Los acentos cyan e índigo refuerzan la identidad técnica sin ser estridentes.

### Tipografía

`'Segoe UI', system-ui, -apple-system, sans-serif` — system font stack para carga instantánea sin requests externos. Tamaños con `clamp()` para escalado fluido entre móvil y escritorio.

### Animaciones

- **Reveal on scroll** — `IntersectionObserver` con stagger de 80ms entre hermanos. Sin librerías.
- **Skill bars** — animación disparada al entrar en viewport, no al cargar la página.
- **Avatar** — rotación CSS infinita (`spin-slow 18s linear`) con inner en sentido contrario.
- **Hover cards** — `translateY(-4px)` + `box-shadow` para sensación de elevación.
- **Badge hero** — pulso `opacity` en el dot de estado.
- Todas las transiciones usan `cubic-bezier(.4,0,.2,1)` (Material Design easing).

### Decisiones estructurales

- **Un solo archivo** — sin build step, sin dependencias, desplegable con `git push`.
- **Mobile-first** — breakpoints en 768px (tablet) y 480px (móvil pequeño).
- **Sin frameworks** — HTML/CSS/JS puro para máximo control y cero overhead.
- **CSS custom properties** — toda la paleta y tokens en `:root` para cambios globales en un lugar.
- **`IntersectionObserver`** en lugar de scroll listeners — sin jank, sin debounce manual.
- **Formulario con `mailto:`** — sin backend. Al enviar abre el cliente de correo del usuario con el mensaje pre-rellenado.
- **Meta tags Open Graph** — título, descripción e imagen configurados para previsualización en LinkedIn y Twitter/X.

### Elementos a personalizar antes de publicar

1. `og:url` — completar con la URL real del sitio desplegado
2. `og:image` — reemplazar el placeholder por una imagen real (1200×630px recomendado)
3. Links de LinkedIn y GitHub en `#contacto` — añadir las URLs reales del perfil
4. Foto/avatar — el avatar giratorio puede reemplazarse por una foto real con `border-radius: 50%`

---

## Despliegue en GitHub Pages

### Pasos

**1. Crear el repositorio en GitHub**

```bash
# Desde la carpeta portafolio-web
git init
git add index.html CLAUDE.md
git commit -m "feat: portafolio web inicial"
```

**2. Crear repositorio en GitHub y subir**

```bash
# Crear repo en GitHub (requiere gh CLI instalado)
gh repo create portafolio-web --public --source=. --remote=origin --push

# O con git estándar (reemplaza TU_USUARIO con tu nombre de usuario GitHub)
git remote add origin https://github.com/TU_USUARIO/portafolio-web.git
git branch -M main
git push -u origin main
```

**3. Activar GitHub Pages**

- Ir a **Settings → Pages** en el repositorio
- En **Source**, seleccionar `Deploy from a branch`
- Branch: `main`, carpeta: `/ (root)`
- Guardar — GitHub tardará ~1 minuto en publicar

**4. URL resultante**

```
https://TU_USUARIO.github.io/portafolio-web/
```

Actualizar `og:url` en `index.html` con esta URL y hacer push.

### Actualizaciones futuras

```bash
# Cualquier cambio en index.html se refleja automáticamente
git add index.html
git commit -m "update: descripción del cambio"
git push
```

GitHub Pages redespliega en cada push a `main`. No se necesita ningún paso adicional.

### Dominio personalizado (opcional)

1. Comprar dominio (ej. `williamsolano.dev`)
2. En **Settings → Pages → Custom domain** escribir el dominio
3. En el DNS del proveedor agregar un CNAME apuntando a `TU_USUARIO.github.io`
4. Activar **Enforce HTTPS**

---

## Comandos rápidos de referencia

```bash
# Abrir en el navegador local (sin servidor)
start index.html                  # Windows
open index.html                   # macOS

# Con servidor local (evita restricciones CORS futuras)
python -m http.server 8080        # Python 3
npx serve .                       # Node.js

# Ver cambios en tiempo real (requiere VS Code)
# Usar extensión Live Server → botón "Go Live"
```
