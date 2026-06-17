# PowerFit Gym — Proyecto Web
**ESPE Latacunga | Trabajo Colaborativo | Materialize CSS**

---

## Descripción

Sitio web completo para un gimnasio ficticio llamado **PowerFit Gym**, desarrollado como proyecto grupal para la Universidad de las Fuerzas Armadas ESPE — Latacunga. El proyecto usa **Materialize CSS 1.0.0** como framework principal para todo el diseño y dinamismo, complementado con CSS propio únicamente donde Materialize no llega. Contiene JavaScript mínimo (solo para el toast del formulario).

---

## Estructura de archivos

```
Trabajo colaborativo (Materalize)/
│
├── index.html                  ← Página principal (integra todo)
├── README.md                   ← Este archivo
│
├── css/
│   └── estilos.css             ← CSS propio (solo lo que Materialize no cubre)
│
└── sections/                   ← Archivos por integrante del grupo
    ├── navbar.html             ← Parte 1: Navbar, Hero y Footer
    ├── servicios.html          ← Parte 2: Cards de servicios + Tabla de planes
    ├── equipo.html             ← Parte 3: Perfiles del equipo + Horario
    └── contacto.html           ← Parte 4: Galería + Formulario de contacto
```

---

## Secciones de la página

### 1. Navbar (Parte 1)
Barra de navegación fija en la parte superior con:
- Logo con ícono de Material Icons
- Links de navegación al mismo documento (anclas)
- Fijo en el scroll usando `position: fixed` + `z-index`

### 2. Hero (Parte 1)
Sección de bienvenida a pantalla completa con:
- Fondo de imagen con gradiente oscuro superpuesto
- Título principal animado
- Dos botones de llamada a acción
- Chips informativos (miembros, clases, años de experiencia)
- Botón principal con efecto `.pulse` de Materialize

### 3. Servicios (Parte 2)
Cuatro cards de servicios (Cardio, Pesas, Yoga, Funcional):
- Imágenes reales de Unsplash acordes a cada actividad
- Chips de nivel y modalidad
- Efecto `.hoverable` al pasar el mouse

### 4. Tabla de Planes (Parte 2)
Comparativa de tres planes de membresía (Básico, Pro, Premium):
- Íconos `check_circle` y `cancel` de Material Icons
- Tabla responsive con `.striped` y `.highlight`

### 5. Equipo (Parte 3)
Cuatro perfiles completos de entrenadores:
- Foto real de Unsplash con overlay de nombre y especialidad
- Stats rápidas: edad, género, experiencia, área
- Descripción de su rol y especialidad
- Barras de habilidades con porcentajes (`.progress`)
- Chips de certificaciones
- Cada perfil con color de acento propio (morado, teal, naranja, rosa)

### 6. Horario Semanal (Parte 3)
Grid de 7 columnas (Lun–Dom) con flip cards CSS:
- Cara frontal: día abreviado, emoji y nombre del día
- Cara trasera (hover): ícono de la actividad, nombre, hora, instructor y nivel
- Responsivo: 7 columnas → 4 (tablet) → 2 (móvil)

### 7. Galería (Parte 4)
Seis fotos reales de instalaciones de gimnasio:
- Layout de 3 columnas en escritorio, 2 en tablet, 1 en móvil
- Efecto zoom sutil al pasar el mouse (CSS `transform: scale`)

### 8. Formulario de Contacto (Parte 4)
Formulario completo con:
- Campos: nombre, email, teléfono, membresía, mensaje, turno
- Validación visual de campos con `.validate`
- Radio buttons (sin JS, reemplaza `<select>`)
- Al enviar: animación de carga → Toast de Materialize → Card de éxito

### 9. Footer (Parte 1)
Pie de página con tres columnas:
- Marca, descripción y botones de redes sociales
- Links de navegación internos
- Datos de contacto reales (ESPE Latacunga):
  - Dirección con link a Google Maps
  - Teléfono clickeable `+593 99 539 6752`
  - Sitio web `www.espe.edu.ec`

---

## Componentes de Materialize utilizados

| Componente | Clase(s) | Dónde se usa |
|---|---|---|
| Grid system | `.row`, `.col`, `.s12`, `.m6`, `.l3`, `.l4`, `.offset-*` | En toda la página |
| Navbar | `<nav>`, `.nav-wrapper`, `.brand-logo` | Encabezado |
| Cards | `.card`, `.card-image`, `.card-content`, `.card-action`, `.card-title` | Servicios, equipo, formulario |
| Card horizontal | `.card.horizontal`, `.card-stacked` | Versión compacta de equipo |
| Chips | `.chip` | Servicios, equipo, horario |
| Botones | `.btn`, `.btn-large`, `.btn-floating` | CTAs, formulario, footer |
| Waves effect | `.waves-effect`, `.waves-light` | Todos los botones y links |
| Hoverable | `.hoverable` | Cards de servicios y equipo |
| Pulse | `.pulse` | Botón principal del hero |
| Progress bar | `.progress`, `.determinate` | Habilidades de entrenadores |
| Breadcrumb | `.breadcrumb`, `.nav-wrapper` | Navegación de sección contacto |
| Responsive table | `.responsive-table`, `.striped`, `.highlight` | Tabla de planes |
| Collection | `.collection`, `.collection-item`, `.badge`, `.divider` | Horario en sección equipo |
| Input fields | `.input-field`, `.validate`, `.helper-text`, `.prefix` | Formulario |
| Textarea | `.materialize-textarea` | Campo de mensaje |
| Radio buttons | `input[type=radio]` | Membresía y turno |
| Checkbox | `input[type=checkbox]` | Términos y condiciones |
| Toast | `M.toast({...})` | Confirmación del formulario |
| Z-depth | `.z-depth-2`, `.z-depth-3` | Cards y tabla |
| Responsive images | `.responsive-img` | Galería |
| Color classes | `.deep-purple`, `.teal`, `.orange`, `.pink`, `.grey` (+ variantes) | Tema oscuro general |
| Material Icons | `<i class="material-icons">` | Íconos en toda la página |
| Badge | `.badge` | Cupos en el horario tipo collection |

---

## CSS propio — `estilos.css`

El CSS personalizado se limita estrictamente a lo que Materialize no puede hacer solo:

| Clase / Selector | Qué hace |
|---|---|
| `body` | Fondo `#0f0f0f` oscuro + `padding-top` para el navbar fijo |
| `.section`, `.bg-dark-1`, `.bg-dark-2` | Alterar entre fondos oscuros por sección |
| `.section-title`, `.title-underline` | Tipografía de encabezados y línea decorativa |
| `.hero-section` | Imagen de fondo con `fixed` parallax + gradiente |
| `.hero-title`, `.hero-sub` | Tamaño responsivo con `clamp()` |
| `.card` (override) | Fondo `#1c1c1c` para tema oscuro |
| `.srv-img` | Altura fija en imágenes de servicios con `object-fit: cover` |
| `.trainer-img` | Foto de entrenador con altura fija y recorte desde arriba |
| `.trainer-overlay` | Gradiente oscuro sobre la foto con nombre encima |
| `.skill-lbl` | Fila de etiqueta + porcentaje para las barras |
| `.info-stat`, `.val`, `.lbl` | Stats del perfil del entrenador |
| `.schedule-grid` | CSS Grid de 7 columnas con breakpoints (7 → 4 → 2) |
| `.day-card`, `.day-card-inner` | Perspectiva 3D y transición del flip |
| `.day-front`, `.day-back` | Caras de la flip card con `backface-visibility: hidden` |
| `.day-abbr`, `.day-emoji`, `.day-name` | Tipografía de la cara frontal |
| `.day-back-*` | Tipografía de la cara trasera |
| `.gallery-img` | Altura fija + `transform: scale` en hover |
| `table` overrides | Colores de tema oscuro para tabla de planes |
| `.collection` overrides | Fondo oscuro para la colección de horarios |
| `nav.breadcrumb-nav` | Color morado para el breadcrumb |
| `.input-field` overrides | Colores de tema oscuro para el formulario |
| `[type="radio"]`, `[type="checkbox"]` | Color morado para controles de formulario |
| `#msg-enviado` | Oculto por defecto, visible con clase `.visible` |
| `@keyframes fadeInUp` | Animación de entrada suave para el mensaje de éxito |
| `footer a:hover` | Cambio de color en hover para links del footer |

---

## JavaScript utilizado

Se usó JavaScript únicamente para el formulario de contacto. Se importó **Materialize JS 1.0.0** via CDN solo por esta razón:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js"></script>
```

Función `enviarFormulario(event)`:
1. Previene el envío real del formulario (`e.preventDefault()`)
2. Cambia el botón a estado "Enviando..." con ícono de carga
3. Espera 1.2 segundos (simulación)
4. Dispara `M.toast()` — toast verde de Materialize con mensaje de confirmación
5. Muestra la card verde de éxito con animación
6. Cambia el botón a estado "¡Enviado!" permanentemente

---

## CDNs utilizados

```html
<!-- Íconos de Material Design (Google Fonts) -->
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet" />

<!-- Materialize CSS 1.0.0 -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css" />

<!-- Materialize JS 1.0.0 (solo para Toast del formulario) -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js"></script>
```

Imágenes obtenidas de **Unsplash** (libres de uso).

---

## Tema visual

- **Fondo principal:** `#0f0f0f` (casi negro)
- **Fondos alternos:** `#111` y `#181818`
- **Color de acento:** `deep-purple darken-2 / darken-3` (Materialize)
- **Texto principal:** blanco / `#e0e0e0`
- **Texto secundario:** `grey-text text-lighten-1`
- **Colores de entrenadores:** morado, teal, naranja, rosa (uno por entrenador)

---

## Responsividad

La página es completamente responsiva gracias al grid de Materialize y breakpoints propios:

| Elemento | Móvil (s) | Tablet (m) | Escritorio (l) |
|---|---|---|---|
| Cards de servicios | 1 columna | 2 columnas | 4 columnas |
| Perfiles equipo | 1 columna | 2 columnas | 2 columnas |
| Horario flip cards | 2 columnas | 4 columnas | 7 columnas |
| Galería | 1 columna | 2 columnas | 3 columnas |
| Tabla de planes | scroll horizontal | completa | completa |

---

## División del trabajo por integrante

| Parte | Archivo | Contenido |
|---|---|---|
| Parte 1 | `sections/navbar.html` | Navbar + Hero + Footer |
| Parte 2 | `sections/servicios.html` | Cards de servicios + Tabla de planes |
| Parte 3 | `sections/equipo.html` | Perfiles del equipo + Horario semanal |
| Parte 4 | `sections/contacto.html` | Galería + Formulario de contacto |

El archivo `index.html` integra todos los fragmentos y es la página entregable final.

---

*Proyecto desarrollado para la asignatura de Tecnologías Web — ESPE Latacunga, 2025.*
