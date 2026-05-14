# AI+Equipo — Landing Kick Off

> Ayuda memoria del Kick Off del programa AI+Equipo  
> GCBA · Subsecretaría de Comunicación Digital · Mayo 2026

🌐 **Landing (principal):** [ai-equipo-kickoff.surge.sh](https://ai-equipo-kickoff.surge.sh)  
🔁 **Landing (backup):** [0rgan1co.github.io/aiequipo_lanzamiento](https://0rgan1co.github.io/aiequipo_lanzamiento/)

---

## ¿Qué es esto?

Site estático construido con **Hugo** que documenta el primer Kick Off del programa AI+Equipo. Incluye los desafíos identificados en el research, la cosecha de los grupos de trabajo, las votaciones del AI-Tournament y recursos del evento.

---

## Stack

| Herramienta | Uso |
|-------------|-----|
| [Hugo](https://gohugo.io/) | Generador de sitio estático |
| [Surge.sh](https://surge.sh/) | Deploy y hosting |
| HTML/CSS custom | Sin frameworks, diseño desde cero |
| Google Fonts | DM Sans + Inter |

---

## Estructura del proyecto

```
aiequipo_lanzamiento/
├── layouts/
│   ├── index.html                  # Plantilla principal + meta tags OG
│   └── partials/
│       ├── styles.html             # Todo el CSS (design tokens + componentes)
│       ├── header.html             # Header sticky con logo y nav
│       ├── hero.html               # Hero dark con video y stat cards
│       ├── section-tldr.html       # Resumen ejecutivo (3 cards)
│       ├── section-resumen.html    # ¿Qué fue el Kick Off? + selfie
│       ├── section-desafios.html   # Los 7 desafíos (D1–D7)
│       ├── section-cosecha.html    # Cosecha de grupos con citas del transcript
│       ├── section-hallazgos.html  # 15 hallazgos del research (vacío/oculto)
│       ├── section-votaciones.html # Ranking + resultados AI-Tournament
│       ├── section-proximos.html   # Vacío (próximos pasos removidos)
│       ├── section-recursos.html   # Links a Research PDF, Slides, Álbum
│       ├── section-cierre.html     # Imagen de cierre + frase
│       └── footer.html             # Footer dark con borde cyan
├── static/
│   └── img/
│       ├── logo.png        # Logo AI+Equipo Op1
│       ├── selfie.jpg      # Foto grupal del Kick Off
│       ├── og.jpg          # Imagen OG optimizada 1200x630 para previews
│       ├── bienvenida.jpg  # Imagen de cierre
│       ├── wordcloud.png   # Nube de palabras del equipo
│       └── video.mp4       # Video del evento (9:16 vertical)
├── hugo.toml               # Configuración Hugo
├── IDENTIDAD.md            # Guía de identidad visual completa
└── README.md               # Este archivo
```

---

## Cómo editar contenido

### Cambiar texto de una sección
Cada sección es un archivo HTML independiente en `layouts/partials/`. Editá directamente el archivo correspondiente.

**Ejemplo:** para cambiar el texto del TL;DR → editá `section-tldr.html`

### Agregar una sección nueva
1. Crear `layouts/partials/section-nueva.html`
2. Agregar `{{ partial "section-nueva.html" . }}` en `layouts/index.html` en el orden deseado

### Cambiar estilos
Todo el CSS está en `layouts/partials/styles.html`. Los design tokens están al inicio en `:root {}`.

**Tokens clave:**
```css
--cyan:      #00AEFE   /* acento principal */
--cyan-deep: #0076B8   /* texto y botones */
--lavender:  #CABDEC   /* acento secundario */
--bg:        #F0F2F5   /* fondo general */
```

### Reemplazar imágenes
Copiá el archivo nuevo a `static/img/` con el mismo nombre. Luego hacer build y deploy.

### Actualizar links de recursos
Editar `layouts/partials/section-recursos.html` — cambiar los atributos `href` de los 3 `.rec-link`.

---

## Cómo hacer deploy

### Requisitos
```bash
# Instalar Hugo (Mac)
brew install hugo

# Instalar Surge
npm install -g surge
```

### Flujo de trabajo
```bash
# 1. Clonar el repo
git clone https://github.com/0rgan1co/aiequipo_lanzamiento.git
cd aiequipo_lanzamiento

# 2. Hacer cambios en layouts/ o static/

# 3. Build
hugo

# 4. Deploy a Surge
surge public/ ai-equipo-kickoff.surge.sh

# 5. Guardar en el repo
git add -A
git commit -m "descripción del cambio"
git push
```

### Ver en local antes de deployar
```bash
hugo server
# Abre http://localhost:1313
```

---

## Secciones y su orden

| # | ID | Sección | Archivo |
|---|-----|---------|---------|
| — | — | Hero + video | `hero.html` |
| — | `#tldr` | TL;DR — 60 segundos | `section-tldr.html` |
| 01 | `#resumen` | ¿Qué fue el Kick Off? | `section-resumen.html` |
| 02 | `#desafios` | Los 7 desafíos | `section-desafios.html` |
| 03 | `#cosecha` | Cosecha de grupos | `section-cosecha.html` |
| 04 | `#votaciones` | Lo que votamos | `section-votaciones.html` |
| 05 | `#recursos` | Recursos del encuentro | `section-recursos.html` |
| — | — | Cierre | `section-cierre.html` |

---

## Links importantes

| Recurso | URL |
|---------|-----|
| Landing (principal) | https://ai-equipo-kickoff.surge.sh |
| Landing (backup) | https://0rgan1co.github.io/aiequipo_lanzamiento/ |
| Repo | https://github.com/0rgan1co/aiequipo_lanzamiento |
| Research Voces AI | https://drive.google.com/file/d/1CfOL28b0o6jbMCnKo-5CFuKnqtIQI7SV/view |
| Slides del Kick Off | https://drive.google.com/file/d/1YN7fdqE6QVUDFSYmq8JHMEN5gLhZaaxB/view?usp=sharing |
| Álbum de fotos | https://photos.app.goo.gl/fTxMWhc7GjEVguv2A |
| Identidad de marca | Ver `IDENTIDAD.md` en este repo |

---

## Próximos pasos / ideas para evolucionar

- [ ] Agregar sección de Ideaton cuando esté confirmada
- [ ] Incorporar más fotos del evento entre secciones
- [ ] Versión en inglés si se comparte externamente
- [ ] Agregar formulario de contacto o registro ("Quiero participar")
- [ ] Analytics (Plausible o similar, sin cookies)
- [ ] Convertir a PWA para uso offline en el equipo

---

## Identidad visual

Ver [`IDENTIDAD.md`](./IDENTIDAD.md) para la guía completa de colores, tipografía, componentes y tono de comunicación.

---

*Construido con ❤️ por el equipo de AI+Equipo · Mayo 2026*
