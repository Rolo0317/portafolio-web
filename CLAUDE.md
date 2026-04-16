# Portafolio Web — William Danilo Solano Álvarez

## Propósito del proyecto

Portafolio web profesional de una sola página (SPA estática) para William Danilo Solano Álvarez, Data Analyst en GROUPCOS. Sirve como presencia digital para compartir en LinkedIn, procesos de selección y networking técnico. Comunica logros cuantificables, stack técnico, formación y certificados de forma visual y directa.

**URL pública:** https://Rolo0317.github.io/portafolio-web/

---

## Estructura de carpetas

```
portafolio-web/
├── index.html                                  # Único archivo fuente — HTML, CSS y JS embebidos
├── CLAUDE.md                                   # Esta documentación
├── foto_corporativa/
│   └── foto_corporativa.jpeg                   # Foto de perfil del hero
└── certificados/
    ├── CV_William_Solano_2026.pdf
    ├── certificado_desarrollo_web_front-end.pdf
    ├── certificado_english_basics_I.pdf
    └── certificado_english_basics_II.pdf
```

No hay dependencias externas, frameworks ni pasos de compilación.

---

## Datos del perfil

| Campo           | Valor                                |
|-----------------|--------------------------------------|
| Nombre completo | William Danilo Solano Álvarez        |
| Rol             | Data Analyst                         |
| Email           | Daniloalvarez1719@gmail.com          |
| Teléfono        | +57 320 391 4473                     |
| Empresa actual  | GROUPCOS (2020 – actualidad)         |
| GitHub          | github.com/Rolo0317                  |

### Logros destacados

- Reducción del **40%** en tiempos de reportería con Python
- Dashboards interactivos en Power BI para decisiones en tiempo real
- Integración de datos desde múltiples fuentes (APIs REST, SQL, archivos)
- Flujos de IA generativa para clasificación y procesamiento automatizado

### Stack técnico

| Categoría       | Tecnologías                                    |
|-----------------|------------------------------------------------|
| Lenguajes       | Python, SQL, JavaScript                        |
| Datos           | Pandas, NumPy, Matplotlib                      |
| Bases de datos  | MySQL, PostgreSQL, Redis                       |
| Visualización   | Power BI, Excel Avanzado                       |
| Infraestructura | Docker, APIs REST, Git                         |
| Front-End       | HTML, CSS                                      |
| IA              | IA Generativa, LLMs, Pipelines IA             |

### Formación

| Año  | Título                                           | Institución              |
|------|--------------------------------------------------|--------------------------|
| 2025 | Desarrollo Web Front-End                         | Universidad de los Andes |
| 2024 | Power BI — Análisis y Visualización de Datos     | CET Colsubsidio          |
| 2022 | Excel Avanzado                                   | CET Colsubsidio          |
| 2020 | Técnico en Operaciones Comerciales y Financieras | SENA                     |

---

## Secciones del portafolio

| ID              | Contenido                                                              |
|-----------------|------------------------------------------------------------------------|
| `#hero`         | Nombre, rol, badge animado, stat chips, foto de perfil y CTAs         |
| `#sobre`        | Bio, cita destacada y tarjetas de datos de contacto/empresa            |
| `#logros`       | 6 cards con métrica grande y descripción de impacto                    |
| `#stack`        | 7 categorías de tags + barras de habilidad animadas al scroll          |
| `#formacion`    | Timeline vertical con 4 entradas educativas                            |
| `#certificados` | Cards de PDFs con botón "Ver certificado" que abre en nueva pestaña   |
| `#contacto`     | Links directos (email, tel, LinkedIn, GitHub) + formulario mailto      |

---

## Decisiones de diseño

### Paleta de colores (dark professional)

```css
--bg-primary:   #0f172a   /* fondo base — Slate 900        */
--bg-secondary: #1e293b   /* fondo alterno — Slate 800     */
--accent:       #38bdf8   /* cyan principal — Sky 400      */
--accent-2:     #818cf8   /* índigo secundario             */
--text-primary: #f1f5f9   /* texto — Slate 100             */
--text-muted:   #94a3b8   /* texto secundario — Slate 400  */
--border:       #334155   /* bordes — Slate 700            */
```

Paleta inspirada en herramientas de datos como Grafana y VS Code Dark+.

### Foto de perfil

- Ruta: `foto_corporativa/foto_corporativa.jpeg`
- Renderizada en un círculo con borde gradiente (`.photo-ring`) usando `object-fit: cover`
- Visible en móvil (180×180px centrada sobre el texto del hero)

### Animaciones

- **Reveal on scroll** — `IntersectionObserver` con stagger de 80ms entre hermanos
- **Skill bars** — animación disparada al entrar en viewport, no al cargar
- **Hover cards** — `translateY(-4px)` + `box-shadow` para sensación de elevación
- **Badge hero** — pulso de opacidad en el dot de estado

### Sección Certificados

- Una card por cada PDF en `certificados/`
- El botón abre el PDF en `target="_blank"` con `rel="noopener"` (seguridad)
- El CV usa ícono 📄 y texto "Ver documento"; los certificados usan 🎓 y "Ver certificado"
- Grid responsive: hasta 4 columnas → 1 columna en móvil pequeño

### Decisiones estructurales

- **Un solo archivo** — sin build step, sin dependencias, desplegable con `git push`
- **Mobile-first** — breakpoints en 768px y 480px
- **CSS custom properties** — toda la paleta en `:root` para cambios globales en un lugar
- **`IntersectionObserver`** en lugar de scroll listeners — sin jank, sin debounce
- **Formulario con `mailto:`** — sin backend, abre el cliente de correo del usuario

---

## Cómo agregar nuevos certificados

1. Copiar el PDF a la carpeta `certificados/`
2. En `index.html`, dentro de `<div class="cert-grid">`, agregar una nueva card:

```html
<div class="cert-card reveal">
  <div class="cert-icon">🎓</div>
  <div class="cert-name">Nombre del Certificado</div>
  <a href="certificados/nombre_del_archivo.pdf" target="_blank" rel="noopener" class="cert-btn">
    Ver certificado →
  </a>
</div>
```

3. Hacer commit y push (GitHub Pages redespliega automáticamente):

```bash
git add certificados/nombre_del_archivo.pdf index.html
git commit -m "feat: agrega certificado Nombre del Certificado"
git push
```

---

## Despliegue en GitHub Pages

### Repositorio

- **URL del repo:** https://github.com/Rolo0317/portafolio-web
- **Rama:** `main`
- **Fuente Pages:** raíz `/` de la rama `main`

### Subir cambios

```bash
cd "C:\Users\millo\Proyectos\portafolio-web"
git add .
git commit -m "update: descripción del cambio"
git push
```

GitHub Pages redespliega automáticamente en cada push. No se necesita ningún paso extra.

### Comandos para abrir localmente

```bash
# Sin servidor (abrir directamente)
start index.html                  # Windows

# Con servidor local (recomendado para que los PDFs abran correctamente)
python -m http.server 8080        # Python 3 — abrir http://localhost:8080
npx serve .                       # Node.js

# VS Code: extensión Live Server → botón "Go Live"
```

> **Nota:** Abrir `index.html` directo puede bloquear los PDFs por política CORS del navegador.
> Usar un servidor local garantiza que los PDFs abran correctamente en desarrollo.
