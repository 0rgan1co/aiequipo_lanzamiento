# Identidad de Marca — AI+Equipo

> Documento de referencia para la identidad visual del programa AI+Equipo, GCBA · Subsecretaría de Comunicación Digital.

---

## Logo

**Nombre:** AI+Equipo  
**Variantes disponibles:**
- Op1: gris oscuro + outline sobre fondo blanco (usado en header light)
- Op2: cyan + outline sobre fondo blanco con borde cyan
- Op3: gris + outline sin borde exterior
- Op4: blanco sobre fondo gris oscuro (dark backgrounds)

**Archivo:** `/static/img/logo.png` (Op1, recortado del PDF de identidad)  
**Uso en header dark:** aplicar `filter: brightness(0) invert(1)` via CSS si se necesita versión blanca.

---

## Paleta de colores

### Primaria
| Token | Hex | Uso |
|-------|-----|-----|
| `--cyan` | `#00AEFE` | Acento principal, links, badges |
| `--cyan-deep` | `#0076B8` | Texto sobre fondo claro, botones |
| `--cyan-light` | `#D4F8FE` | Fondos suaves, hover states |
| `--cyan-bg` | `#EBF7FF` | Backgrounds de cards con acento |
| `--cyan-border` | `#B3DEFF` | Bordes con acento |

### Secundaria
| Token | Hex | Uso |
|-------|-----|-----|
| `--lavender` | `#CABDEC` | Acento suave, gradientes |
| `--lav-bg` | `#F3F0FB` | Backgrounds lavanda |
| `--lav-border` | `#D9D0F5` | Bordes lavanda |

### Dark (hero y footer)
| Token | Hex | Uso |
|-------|-----|-----|
| `#070708` | Negro puro | Base del hero y footer |
| `#0A1628` | Azul oscuro | Gradiente del hero |
| `#0B1A2E` | Azul noche | Gradiente del hero (fin) |

### Neutros
| Token | Hex | Uso |
|-------|-----|-----|
| `--ink-900` | `#111318` | Títulos principales |
| `--ink-700` | `#2C3038` | Texto body |
| `--ink-500` | `#565C68` | Texto secundario |
| `--ink-300` | `#9EA5B0` | Texto muted, labels |
| `--ink-100` | `#E4E7EC` | Bordes, separadores |
| `--ink-50` | `#F7F8FA` | Fondos de cards internas |
| `--bg` | `#F0F2F5` | Fondo general del sitio |

### Estados
| Token | Hex | Uso |
|-------|-----|-----|
| `--yellow` | `#F5C000` | Destacado, #1 más votado |
| `--yellow-text` | `#7A5C00` | Texto sobre amarillo |
| `--green` | `#1B6E3A` | Hallazgos positivos |
| `--red-text` | `#8B1A1A` | Hallazgos negativos |

---

## Tipografía

| Rol | Familia | Pesos | Uso |
|-----|---------|-------|-----|
| **Primaria** | DM Sans | 300, 400, 500, 600, 700 | Todo el body, títulos de secciones |
| **Secundaria** | Inter | 400, 500, 600, 700 | Labels, badges, navegación, números |

**Import:**
```html
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;1,9..40,400&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

**Escala tipográfica:**
- Títulos H1 hero: `2.8rem / 700 / tracking -1.5px`
- Títulos de sección: `1.4rem / 700 / tracking -0.4px`
- Subtítulos de card: `0.9rem / 700`
- Body: `0.79–0.82rem / 400`
- Labels/badges: `0.6–0.67rem / 700 / uppercase / Inter`

---

## Fondos

La identidad contempla 3 tipos de fondo:
1. **Gradiente cyan** (blob): usado en el hero como glow radial
2. **Blanco** (`#FFFFFF`): fondo de cards
3. **Negro** (`#070708`): hero y footer

---

## Iconografía

Estilo: circular, plateado/metálico (ver PDF de identidad).  
En la landing se usan emojis como reemplazo funcional.

---

## Recursos gráficos (del PDF de identidad)

- Blob/mancha azul degradada → fondos de secciones
- Wireframe de cabeza IA → ilustración conceptual
- Chip/CPU con nube → representación tecnológica
- Círculo de líneas cyan → elemento decorativo

---

## Tono de comunicación

- **Directo y humano**: evitar jerga técnica innecesaria
- **Primera persona plural**: "lo que construimos juntos"
- **Optimista pero honesto**: mostrar tensiones reales del equipo
- **Sin marketing vacío**: datos reales, voces reales del equipo

---

## Componentes UI (landing)

### Shape & spacing
```css
--radius-sm:  6px
--radius:     12px
--radius-lg:  18px
--radius-xl:  24px
--radius-pill:9999px
```

### Sombras
```css
--shadow-xs: 0 1px 2px rgba(0,0,0,.05)
--shadow-sm: 0 1px 4px rgba(0,0,0,.06), 0 2px 8px rgba(0,0,0,.04)
--shadow-md: 0 4px 16px rgba(0,0,0,.08), 0 1px 4px rgba(0,0,0,.04)
--shadow-lg: 0 8px 32px rgba(0,0,0,.1),  0 2px 8px rgba(0,0,0,.05)
```

### Hero
- Fondo: dark gradient `#070708 → #0A1628 → #0B1A2E`
- Glows: radial cyan (top-right) + radial lavanda (bottom-left)
- Layout: 2 columnas — texto+stats | video vertical 9:16

### Cards
- Background: `#FFFFFF`
- Border: `1px solid #E4E7EC`
- Hover: `translateY(-2px)` + `shadow-md` + `cyan-border`
- Acento top: `3px solid var(--cyan)` o `3px solid var(--yellow)` para destacados

### Badges / IDs
```css
background: var(--cyan-deep); /* #0076B8 */
color: white;
font-family: Inter;
font-size: 0.6rem;
font-weight: 700;
border-radius: 6px;
text-transform: uppercase;
letter-spacing: 0.5px;
```

---

## Estructura de la landing (v1.0 — Mayo 2026)

| Sección | ID | Descripción |
|---------|-----|-------------|
| Hero | — | Video + stats + eyebrow |
| TL;DR | `#tldr` | Resumen ejecutivo en 3 cards |
| ¿Qué fue el Kick Off? | `#resumen` | Selfie + 4 cards contexto |
| Los 7 desafíos | `#desafios` | Grid D1–D7 |
| Cosecha de grupos | `#cosecha` | D1–D7 con ideas clave + citas transcript |
| Lo que votamos | `#votaciones` | Ranking + resultados AI Tournament |
| Recursos | `#recursos` | Research PDF, Slides, Álbum fotos |
| Cierre | — | Imagen + frase |

---

## Archivos del proyecto

```
/static/img/
  logo.png        → Logo Op1 (gris + outline)
  selfie.jpg      → Foto grupal del Kick Off (hero background)
  bienvenida.jpg  → Imagen de cierre
  wordcloud.png   → Nube de palabras del equipo
  video.mp4       → Video del evento (9:16 vertical)
```

---

*Última actualización: Mayo 2026*
