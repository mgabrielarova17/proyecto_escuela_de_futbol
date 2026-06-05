# ⚽🔥 IERD Duitama — Escuela Deportiva

## _"No encendimos la antorcha para alumbrar nuestro camino, sino para que cada niño de Duitama encuentre el suyo."_

---

## 📋 Plan de Partido

- [Sobre el Club](#-sobre-el-club)
- [Material Deportivo](#-material-deportivo)
- [Plantilla de Archivos](#-plantilla-de-archivos)
- [Análisis por Tiempo](#-análisis-por-tiempo--archivos)
- [Recorrido por la Cancha](#-recorrido-por-la-cancha--secciones)
- [Jugadas Tácticas (JavaScript)](#-jugadas-tácticas--javascript)
- [Colores del Club](#-colores-del-club)
- [Camiseta y Tipografía](#-camiseta-y-tipografía)
- [Jugadas Ensayadas (Animaciones)](#-jugadas-ensayadas--animaciones)
- [Formaciones (Responsive)](#-formaciones--responsive)
- [Cómo Entrar a la Cancha](#-cómo-entrar-a-la-cancha)
- [Acta de Partido (Changelog)](#-acta-de-partido--changelog)
- [Créditos](#-créditos)

---

## 🏟️ Sobre el Club

Sitio web oficial de la **Escuela Deportiva IERD Duitama**, institución deportiva de Boyacá, Colombia, con más de **15 años formando jugadores** dentro y fuera de la cancha. La plataforma incluye el sitio público del club y un sistema de acceso con roles diferenciados para la familia IERD.

### Goles del proyecto:
- ⚽ Sitio público con toda la información del club
- 🔐 Sistema de acceso con 3 roles: Administrador, Profesor, Estudiante
- 📝 Formularios de pre-inscripción y contacto
- 📸 Galería con los mejores momentos del equipo
- ❤️ Sección "Quiénes Somos" con la historia del club
- 📱 Diseño 100% responsive — de la tribuna al celular
- ✨ Animaciones que encienden la pasión
- 🔔 Notificaciones tipo toast para cada jugada

---

## 🛠️ Material Deportivo

| Pieza | Referencia | Función en la cancha |
|---|---|---|
| **HTML5** | - | El terreno de juego |
| **Tailwind CSS** | CDN (v3.4.17) | La táctica de posicionamiento |
| **Iconify** | 3.1.0 | Los escudos y emblemas visuales (colección Lucide) |
| **Inter** | Google Fonts | La voz del narrador (sans-serif) |
| **Playfair Display** | Google Fonts | La placa del campeón (serif, títulos) |
| **JavaScript** | Vanilla ES6+ | El motor del equipo — interactividad y jugadas |

---

## 📁 Plantilla de Archivos

```
ierd-duitama/
├── index.html          ← Cancha principal — Sitio público del club
├── login.html          ← Vestuarios — Acceso según rol
└── README.md           ← Libro de actas — Este documento
```

---

## 📝 Análisis por Tiempo — Archivos

---

### 🏟️ `index.html` — Cancha Principal

La página completa del club. El estadio donde los visitantes conocen todo sobre la IERD: desde las categorías hasta la historia, desde los entrenadores hasta las inscripciones.

#### Preparación del Terreno (`<head>`)

- **Tailwind CSS**: Cargado vía CDN con configuración custom del club
- **Iconify**: Escudos e iconos de la colección Lucide
- **Google Fonts**: Inter (la voz del equipo) y Playfair Display (la placa del campeón)
- **Tailwind Config**: Los colores oficiales del club y las tipografías

##### Colores del club registrados:
```javascript
tailwind.config = {
  theme: {
    extend: {
      colors: {
        club: {
          green: '#1B5E20',       // El césped de la cancha
          green-light: '#2E7D32', // Césped bajo el sol
          green-50: '#E8F5E9',    // Brisa de la mañana en la cancha
          green-100: '#C8E6C9',   // Líneas de cal sobre el césped
          red: '#C62828',         // La pasión que nos arde
          red-light: '#E53935',   // La intensidad del partido
          red-50: '#FFEBEE',      // El rubor del esfuerzo
          orange: '#E65100',      // La antorcha encendida
          orange-light: '#F57C00',// La llama que guía
          orange-50: '#FFF3E0',   // El resplandor del fuego
          dark: '#2D2D2D',        // La noche del estadio
          dark-2: '#1A1A1A',      // Las sombras de la tribuna
          gray: '#4A4A4A'         // El asiento de cemento
        }
      },
      fontFamily: {
        sans: ['Inter', 'sans-serif'],
        serif: ['Playfair Display', 'serif']
      }
    }
  }
}
```

#### Estilo de Juego (`<style>`)

| Jugada | Descripción |
|---|---|
| `fadeInUp` | Entrada del jugador — desde el túnel hacia la cancha |
| `float` | Como un balón en el aire — movimiento vertical suave (3s loop) |
| `pulse-glow` | El resplandor de la antorcha que late en la noche |
| `flicker` | La llama que baila — parpadeo de la antorcha SVG |
| `.animate-fade-up` | Aplica la entrada del jugador (0.8s) |
| `.animate-float` | Balón en el aire — loop infinito |
| `.animate-pulse-glow` | Antorcha que late — loop infinito |
| `.flame` | La llama del club — transform-origin desde la base |
| `.scroll-hidden` → `.scroll-visible` | Jugadores que aparecen al entrar en la cancha visual |
| `.gallery-item:hover` | Replay del mejor momento — zoom + overlay |
| `.nav-active` | El jugador que tiene la pelota — naranja (#E65100) |
| `.stripe-green-red` | La bandera del club en la grada — verde→rojo→naranja |
| `.toast` | El gol celebrado — notificación que entra desde la banda |
| `.modal-backdrop` | El VAR — revisión con blur de fondo |
| `.category-card:hover` | Salto del jugador — elevación -8px |
| `.coach-card:hover` | El DT se levanta del banquillo — elevación -5px |
| `.news-card:hover` | La crónica destacada — elevación -5px |
| `.admin-btn` | Puerta del vestuario directo al panel |
| Scrollbar | La banda lateral del estadio — verde sobre oscuro |

---

### 🔐 `login.html` — Vestuarios

La puerta de acceso al equipo. Cada miembro entra por su vestuario según su rol, con su escudo y su color.

#### Preparación (`<head>`)

- Mismas dependencias que la cancha principal
- Misma configuración de colores del club
- Estilos adicionales para los vestuarios

#### Estilos propios del vestuario

| Jugada | Descripción |
|---|---|
| `.role-card` | La casilla del vestuario — transición al seleccionar |
| `.role-card:hover` | El jugador se acerca — elevación -4px |
| `.role-card.active` | El vestuario ocupado — resaltado con color del rol |
| `.role-img` | La foto del jugador en la taquilla — zoom al hover |
| `.password-toggle` | Mostrar/ocultar la estrategia — cursor pointer |

#### Los 3 Vestuarios

| Rol | Foto en taquilla | Escudo | Color de camiseta | Correo |
|---|---|---|---|---|
| **Administrador** | Directivo en oficina | `shield-check` | Verde — el del capitán | admin@ierdduitama.com |
| **Profesor** | Entrenadora en cancha | `whistle` | Naranja — el del DT | profesor@ierdduitama.com |
| **Estudiante** | Niño con balón | `graduation-cap` | Rojo — el de la promesa | estudiante@ierdduitama.com |

**Cada vestuario tiene**:
- Foto del rol (h-24) con zoom al hover
- Gradiente del color del equipo sobre la foto
- Escudo del rol centrado
- Nombre del rol debajo

**Al entrar al vestuario**:
- La casilla se ilumina con el color del equipo
- Las demás vuelven a estado neutro
- El placeholder del correo cambia al del rol
- Se borran mensajes de error

> ⚠️ **Sin cartel de "¿Quién eres?"** — Eliminado. Los vestuarios hablan por sí solos.
> ⚠️ **Sin credenciales expuestas** — Eliminadas. Nadie regala su camiseta.

---

## 🏟️ Recorrido por la Cancha — Secciones

### 1. 🚪 Túnel de Salida — Navbar

La entrada al estadio. Fija arriba, cambia cuando el árbitro pita el inicio.

- **Escudo del club**: Antorcha SVG animada + IERD (I=verde, E=oscuro, R=rojo, D=oscuro) + "Duitama"
- **Links en tribuna**: Inicio, Categorías, Entrenadores, Horarios, Inscripciones, Galería, Noticias, Contacto, Quiénes Somos + "Ingresar" al vestuario
- **Botón CTA**: "Inscribirse" rojo — visible desde la grada
- **Menú móvil**: Hamburguesa → X, fondo oscuro con blur
- **Al hacer scroll > 80px**: Camiseta oscura con blur — los links se vuelven blancos
- **Jugador con la pelota**: Se resalta la sección visible con naranja

---

### 2. 🏆 La Final — Hero (`#inicio`)

El momento más grande. La cancha iluminada bajo las luces del estadio.

- **Césped de fondo**: Estadio Unsplash con doble gradiente (lateral + inferior)
- **Bandera del club**: Franja `.stripe-green-red` arriba
- **Escudo de entrada**: "IERD Duitama — Escuela Deportiva" con llama
- **Grito de gol**: "Encendemos **pasión** por el fútbol" (Playfair, hasta 7xl)
- **3 botones de jugada**:
  - "Inscripciones" — Rojo, la pelota al arco
  - "Contáctanos" — Blanco, el pase al compañero
  - "Horarios" — Borde naranja, el calendario del campeonato
- **Marcador animado**: 15 años 🏟️ | 500 jugadores ⚽ | 30 trofeos 🏆
- **Señal de descenso**: "Descubre más" con flecha flotante
- **Entradas escalonadas**: Del 200ms al 1000ms — como jugadores saliendo del túnel

---

### 3. ⚽ Divisiones del Equipo — Categorías (`#categorias`)

Las divisiones del club. Cada una con su edad, su cancha y su nivel de juego.

- **Fondo**: Césped claro (`bg-stone-50`)
- **4 planteles**:

| División | Edades | Escudo | Nivel | Horario | Cancha |
|---|---|---|---|---|---|
| **Infantil** | 5-10 años | Bebé | Iniciación | Lun, Mié, Vie 4:00 PM | Principal |
| **Prejuvenil** | 11-14 años | Rayo | Intermedio | Lun, Mié, Vie 5:30 PM | Principal |
| **Juvenil** | 15-18 años | Trofeo | Competitivo | Mar, Jue, Sáb 5:00 PM | Complejo |
| **Femenino** | 12+ años | Escudo | Todos | Mar, Jue 4:30 PM | Auxiliar |

- **Cada plantel**: Foto del equipo, badge de edad, descripción, 3 datos tácticos
- **Al hacer click**: Se abre el VAR (modal) con toda la información detallada
- **Hover**: El jugador salta — elevación -8px

---

### 4. 👨‍🏫 Cuerpo Técnico — Entrenadores (`#entrenadores`)

Los directores tácticos del equipo. Quienes dibujan la jugada en la pizarra.

- **Fondo**: Blanco
- **4 miembros del staff**:

| DT | Cargo | Camiseta | Licencia | Experiencia | Horario |
|---|---|---|---|---|---|
| **Carlos Mendoza** | Director Técnico General | Verde | CONMEBOL Pro | 20 años | Todas |
| **Ana Rodríguez** | DT. Categoría Femenino | Rojo | FIFA A | 12 años | Mar y Jue |
| **Miguel Torres** | DT. Categoría Prejuvenil | Naranja | Nacional B | 8 años | Lun, Mié, Vie |
| **Roberto Sánchez** | Preparador Físico | Oscuro | Lic. Deporte | 10 años | Todos |

- **Cada DT**: Foto con gradiente, badge de rol, nombre, cargo, 3 datos
- **Hover**: El DT se levanta del banquillo — elevación -5px

---

### 5. 🕐 Plan de Entrenamiento — Horarios y Sedes (`#horarios`)

Dónde y cuándo entrena el equipo. La pizarra táctica del club.

- **Fondo**: Noche de estadio (`bg-club-dark-2`)
- **2 bandas**:

**Banda izquierda — Horarios**:
- Tabla con las 4 divisiones, cada una con su color, días y franja horaria
- Foto de la cancha debajo

**Banda derecha — Sedes**:
- **Complejo IERD** (Cra 15 #45-20): Cancha principal, vestuarios, parqueo
- **Cancha La Esperanza** (Calle 30 #12-45): Cancha auxiliar, graderías
- Mapa de Google embebido debajo

---

### 6. 📝 Fichajes — Inscripciones (`#inscripciones`)

La ventana de fichajes del club. Todo lo que necesitas para vestir la camiseta.

- **2 bandas**:

**Banda izquierda — Requisitos del fichaje**:
- **Médico** (verde): 5 requisitos con checkmark — edad, certificado, documento, foto, autorización
- **Contrato** (oscuro): Inscripción $150.000, Mensualidad $120.000, Uniforme $95.000 + 4 formas de pago (Efectivo, Transferencia, Tarjeta, Nequi/Daviplata)
- **Documentos** (stone): 3 PDFs para descargar — Formato inscripción, Autorización acudiente, Reglamento

**Banda derecha — Formulario de fichaje** (sticky):
- Campos: Nombre, Apellido, Fecha nacimiento, Categoría (select), Acudiente, Teléfono, Email, Mensaje
- Botón "Enviar Pre-Inscripción" — la pelota al arco
- Nota: "Nos comunicaremos en máximo 48 horas hábiles"

---

### 7. 📸 Los Mejores Momentos — Galería (`#galeria`)

El replay de las jugadas más bonitas del equipo. Cada foto cuenta una historia.

- **Grid masonry**: 4 columnas en desktop, 3 en tablet, 2 en móvil
- **1 foto gigante** (col-span-2, row-span-2): "Final departamental juvenil"
- **4 fotos pequeñas**: Infantil, Femenino, Sede, Entrenamiento
- **Al pasar el mouse**: Zoom al replay + overlay con badge y descripción

---

### 8. 📰 Crónica del Club — Noticias (`#noticias`)

Las últimas novedades del equipo. Lo que se habla en la tribuna.

- **3 crónicas**:

| Titular | Badge | Fecha |
|---|---|---|
| IERD campeón del torneo intercolegial de Boyacá | Torneo (rojo) | 15 Ene 2025 |
| Abiertas inscripciones 2025 para todas las categorías | Inscripciones (verde) | 8 Ene 2025 |
| Categoría femenino logra subcampeonato regional | Femenino (naranja) | 20 Dic 2024 |

- **Cada crónica**: Foto, badge, fecha, titular, extracto, enlace "Leer más"
- **Hover**: La noticia se destaca — elevación -5px

---

### 9. 📞 Comunicado del Club — Contacto (`#contacto`)

La línea directa con la dirigencia. Para hablar con el club.

- **Fondo**: Noche de estadio
- **4 datos del club**: Teléfono, Email, Ubicación, Redes sociales
- **Formulario de comunicado**: Nombre, Correo, Asunto, Mensaje + botón verde "Enviar Mensaje"

---

### 10. ❤️ El Alma del Club — Quiénes Somos (`#nosotros`)

La historia que se cuenta en la tribuna. Los valores que se sienten en la cancha. El fuego que nunca se apaga.

- **Fondo**: Césped claro con círculos decorativos — como las luces del estadio

#### a) 📖 La Historia

- **Texto**: Cómo nació la IERD, los voluntarios con un balón, la cancha de tierra, el significado de la antorcha, 500+ jugadores y 30 torneos
- **Foto del equipo**: Con gradiente nocturno, badge flotante "15+ Años encendiendo pasiones" con pulse-glow, badge flotante "30 Torneos" en rojo

#### b) 🎯 Misión, Visión y Valores

3 tarjetas que definen el estilo de juego del club:

| Carta | Escudo | Contenido |
|---|---|---|
| **Misión** | Target | Formar integralmente a través del fútbol — disciplina, equipo, valores |
| **Visión** | Eye | Ser el referente de Boyacá — excelencia deportiva y humana |
| **Valores** | Shield-check | 5 valores con sus colores: Disciplina (verde), Pasión (naranja), Respeto (rojo), Unión (oscuro), Compromiso (verde) |

#### c) 🗣️ El Grito de la Tribuna

- **Fondo**: Noche de estadio con imagen sutil
- **Bandera del club**: Franja `.stripe-green-red`
- **Cita**: _"No encendimos la antorcha para alumbrar nuestro camino, sino para que cada niño de Duitama encuentre el suyo."_
- **Firma**: — Familia IERD Duitama
- **2 jugadas**: "Quiero ser parte" (rojo) + "Escríbenos" (blanco)

#### d) 📅 La Trayectoria — Línea de Tiempo

El camino del club desde el silbato inicial hasta hoy. Línea central gradiente verde→naranja→rojo.

| Año | Hito | Icono | Color |
|---|---|---|---|
| **2009** | El inicio — Voluntarios y cancha de tierra | 🔥 Flama | Verde |
| **2014** | Primer título departamental — Juvenil campeón de Boyacá | 🏆 Trofeo | Naranja |
| **2019** | Nueva sede y categoría femenina — Complejo IERD | ❤️ Corazón | Rojo |
| **2025** | Más fuertes que nunca — 500+ jugadores, 30 torneos | ⭐ Estrella | Oscuro (pulse-glow) |

- Hitos alternados izquierda/derecha — como ida y vuelta en la cancha
- Cada hito con círculo de color, tarjeta con año, título y crónica

---

### 11. 🦶 Túnel de Salida — Footer

La despedida del estadio. La firma del club.

- **Fondo**: La noche del estadio
- **Franja del club**: `.stripe-green-red` arriba y abajo
- **4 columnas**:
  - Escudo del club + descripción
  - Secciones del estadio (links)
  - Más secciones (links)
  - Contacto + redes sociales
- **Copyright**: "© 2025 IERD Duitama" + "Hecho con 🔥 en Boyacá, Colombia"

---

### 🎪 Fuera de la Cancha — Componentes Flotantes

| Componente | Posición | Función |
|---|---|---|
| **Puerta del vestuario** | Abajo-izquierda | Acceso directo al panel admin |
| **WhatsApp del club** | Abajo-derecha | Chat directo con la dirigencia |
| **Celebración de gol** | Abajo-derecha (100px) | Notificación toast que entra desde la banda |

---

### 📺 El VAR — Modal de Categoría

Revisión con el árbitro asistente. Toda la información detallada de cada división.

- **Backstage**: Blur + fondo oscuro — como la pantalla del VAR
- **Click fuera**: Se cancela la revisión
- **Contenido dinámico**: Según la categoría seleccionada
- **Datos de las 4 categorías** almacenados en `categoryData`
- **Cada revisión muestra**: Título, edad, descripción táctica, 4 cajas (horario, cancha, DT, nivel), requisitos del fichaje, CTA de inscripción
- **Scroll bloqueado** mientras el VAR está activo

---

## ⚡ Jugadas Tácticas — JavaScript

### `index.html` — Jugadas en la Cancha

| # | Jugada | Descripción |
|---|---|---|
| 1 | **Cambio de camiseta** | Al scroll > 80px, el navbar viste oscuro con blur y los links se vuelven blancos |
| 2 | **Hamburguesa → X** | Toggle del menú móvil; al elegir sección, se cierra solo |
| 3 | **Entrada a la cancha** | IntersectionObserver (.scroll-animate → .scroll-hidden → .scroll-visible) |
| 4 | **Marcador en vivo** | Contadores animados: 0 → target en ~60 frames, al ser visibles |
| 5 | **Celebración de gol** | showToast(título, mensaje) — entra desde la banda, auto-hide 4s |
| 6 | **Revisión VAR** | openCategoryModal(cat) / closeCategoryModal() — datos en categoryData object |
| 7 | **Fichaje y Comunicado** | Formularios con preventDefault — toast de éxito + reset |
| 8 | **Quién tiene la pelota** | Detecta sección visible y resalta el link del navbar con naranja |

### `login.html` — Jugadas en el Vestuario

| # | Jugada | Descripción |
|---|---|---|
| 1 | **Elección de vestuario** | selectRole(el, role) — Resetea todas las casillas, aplica color del rol (borde, fondo, label, gradiente), actualiza selectedRole, borra errores |
| 2 | **Mostrar la estrategia** | togglePassword() — Alterna password/text, cambia icono eye/eye-off |
| 3 | **Celebración** | showToast(title, msg) — Misma jugada que en la cancha |
| 4 | **Pase al arco** | handleLogin(e) — Validación (vacíos, longitud < 4), loading 1.2s, éxito con toast, errores visibles |
| 5 | **Pista del vestuario** | Al hacer click en un rol, el placeholder del correo cambia según el equipo |

---

## 🎨 Colores del Club

| Color | Hex | Significado en el club |
|---|---|---|
| **Verde cancha** | `#1B5E20` | El césped donde todo empieza. La I del escudo. El capitán. |
| **Verde sol** | `#2E7D32` | La cancha bajo el sol de Boyacá |
| **Verde brisa** | `#E8F5E9` | La mañana de entrenamiento |
| **Verde cal** | `#C8E6C9` | Las líneas del terreno de juego |
| **Rojo pasión** | `#C62828` | La sangre que hierve. La R del escudo. El gol. |
| **Rojo intensidad** | `#E53935` | El partido al máximo |
| **Rojo esfuerzo** | `#FFEBEE` | El rubor después de los 90 minutos |
| **Naranja antorcha** | `#E65100` | El fuego que nos guía. La llama del club. |
| **Naranja llama** | `#F57C00` | La antorcha encendida en la noche |
| **Naranja resplandor** | `#FFF3E0` | El calor de la tribuna |
| **Noche de estadio** | `#2D2D2D` | Las gradas bajo las luces. La E y D del escudo. |
| **Sombra de tribuna** | `#1A1A1A` | El estadio a media noche |
| **Cemento** | `#4A4A4A` | La grada de concreto |

### La Bandera del Club (`.stripe-green-red`)
Franja repetitiva: **Verde 40px → Rojo 40px → Naranja 40px** — Los tres colores de la IERD ondeando en la tribuna.

---

## 👕 Camiseta y Tipografía

| Camiseta | Peso | Uso en el club |
|---|---|---|
| **Inter** | 300-800 | La voz del narrador — cuerpo de texto, labels, botones, descripciones, todo lo que se lee en la tribuna |
| **Playfair Display** | 400-700 | La placa del campeón — títulos de sección (`.font-serif`), h1-h3, los gritos de gol en letras grandes |

---

## 🏃 Jugadas Ensayadas — Animaciones

| Jugada | Duración | Descripción futbolera |
|---|---|---|
| `fadeInUp` | 0.8s | El jugador sale del túnel hacia la cancha (Y: 30px → 0) |
| `float` | 3s loop | Balón flotando en el aire — como un centro al área |
| `pulse-glow` | 2s loop | La antorcha del club que late en la noche del estadio |
| `flicker` | 0.8s loop | La llama que baila con el viento de la cancha |
| Scroll reveal | 0.8s | Jugadores que entran al campo visual |
| Counter | ~1.5s | El marcador que sube gol a gol |
| Hover cards | 0.3s | El jugador salta a cabecear |
| Gallery hover | 0.5s | Replay en cámara lenta del mejor momento |
| Toast slide | 0.4s | El gol celebrado que corre por la banda |

### Tiempos de salida del túnel (Hero)

| Jugador | Tiempo |
|---|---|
| Escudo de entrada | 200ms |
| Grito de gol (h1) | 400ms |
| El comunicado | 600ms |
| Las jugadas (CTAs) | 800ms |
| El marcador | 1000ms |

---

## 📐 Formaciones — Responsive

### Las Formaciones del Equipo

| Formación | Tailwind | Cuándo se usa |
|---|---|---|
| 5 en el fondo | Base | Mobile first (< 640px) — cancha chica |
| 4-4-2 | `sm:` | 640px+ — más espacio en la cancha |
| 4-3-3 | `md:` | 768px+ — apertura por bandas |
| 4-2-3-1 | `lg:` | 1024px+ — formación completa de cancha ancha |
| 3-5-2 ofensiva | `xl:` | 1280px+ — todo el estadio disponible |

### Posiciones por Formación

| Sección | 5 en el fondo | 4-4-2 | 4-2-3-1 |
|---|---|---|---|
| Navbar | Hamburguesa | Hamburguesa | Links en tribuna |
| Hero | Texto 4xl | Texto 5-6xl | Texto 7xl |
| Categorías | 1 col | 2 cols | 4 cols |
| Entrenadores | 1 col | 2 cols | 4 cols |
| Horarios | 1 col | 1 col | 2 cols |
| Inscripciones | 1 col | 1 col | 2 cols |
| Galería | 2 cols | 3 cols | 4 cols |
| Noticias | 1 col | 2 cols | 3 cols |
| Contacto | 1 col | 1 col | 2 cols |
| Quiénes Somos | 1 col | 1-2 cols | 2-3 cols |
| Login vestuarios | 3 cols compacto | 3 cols | 3 cols |

### Espaciado de la cancha
- **Profundidad**: `py-20 lg:py-32`
- **Líneas de banda**: `max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`
- **Formulario fijo**: `sticky top-24` (solo en cancha ancha)

---

## 🚀 Cómo Entrar a la Cancha

1. **Descargar** los archivos del club
2. **Abrir `index.html`** en el navegador — como entrar al estadio
3. No necesita servidor, ni compilador, ni instalación
4. **Para ir al vestuario**: Abrir `login.html` o hacer click en "Ingresar" / "Admin"

### Requisitos del terreno
- Navegador moderno (Chrome, Firefox, Edge, Safari)
- Conexión a internet (CDN: Tailwind, Iconify, Google Fonts, fotos Unsplash)

---

## 📋 Acta de Partido — Changelog

### 🏆 Temporada 1.0 — Enero 2025

#### 🏟️ `index.html` — Cancha Principal

- ⚽ Terreno de juego HTML5 con meta tags responsive
- ⚽ Colores oficiales del club registrados en Tailwind
- ⚽ Escudos e iconos via Iconify (Lucide)
- ⚽ Camisetas tipográficas: Inter + Playfair Display
- ⚽ Túnel de salida (navbar) con cambio de camiseta al scroll
- ⚽ Menú móvil hamburguesa → X
- ⚽ La Final (hero): Estadio iluminado, CTAs y marcador animado
- ⚽ Divisiones del equipo (categorías): 4 planteles interactivos + VAR (modal)
- ⚽ Cuerpo técnico (entrenadores): 4 perfiles del staff
- ⚽ Plan de entrenamiento (horarios y sedes): Tabla + mapas bajo la luna
- ⚽ Ventana de fichajes (inscripciones): Requisitos, costos, documentos y formulario
- ⚽ Los mejores momentos (galería): Grid masonry con replay hover
- ⚽ Crónica del club (noticias): 3 artículos de la temporada
- ⚽ Comunicado del club (contacto): Línea directa con la dirigencia
- ⚽ **El alma del club (Quiénes Somos)** — Sección agregada al final:
  - 📖 La historia del club con foto y badges flotantes
  - 🎯 Misión, Visión y Valores del equipo
  - 🗣️ El grito de la tribuna — cita inspiracional
  - 📅 La trayectoria — línea de tiempo 2009-2025
- ⚽ Túnel de salida (footer): 4 columnas, links, contacto, redes
- ⚽ Puerta del vestuario flotante (admin)
- ⚽ WhatsApp del club flotante
- ⚽ Celebración de gol (toast)
- ⚽ VAR de categoría con datos dinámicos
- ⚽ Animaciones de entrada a la cancha (IntersectionObserver)
- ⚽ Marcador en vivo (contadores animados)
- ⚽ Quién tiene la pelota (active nav link)
- ⚽ Banda lateral del estadio (scrollbar personalizado)
- ⚽ Antorcha SVG animada — la llama del club

#### 🔐 `login.html` — Vestuarios

- ⚽ Vestuarios con foto de estadio de fondo
- ⚽ Bandera del club `.stripe-green-red` arriba
- ⚽ Escudo IERD con antorcha animada
- ⚽ **3 vestuarios con fotos de los roles**:
  - Administrador: Directivo + escudo shield-check + camiseta verde
  - Profesor: Entrenadora + escudo whistle + camiseta naranja
  - Estudiante: Niño con balón + escudo graduation-cap + camiseta roja
- ⚽ **Eliminado "¿Quién eres?"** — Los vestuarios hablan por sí solos
- ⚽ **Eliminadas credenciales expuestas** — Nadie regala su camiseta
- ⚽ Gradientes de foto dinámicos según el vestuario seleccionado
- ⚽ Placeholder del correo dinámico según el rol
- ⚽ Formulario con correo y contraseña
- ⚽ Mostrar/ocultar estrategia (toggle password eye/eye-off)
- ⚽ Checkbox "Recordarme"
- ⚽ Link "¿Olvidaste tu contraseña?" con celebración toast
- ⚽ Validación frontend (vacíos, longitud mínima)
- ⚽ Estados del botón: Normal → Cargando → Gol → Reset
- ⚽ Mensaje de error ocultable
- ⚽ Celebraciones toast
- ⚽ Link "Inscríbete aquí" → cancha principal
- ⚽ Link "Volver al sitio" → cancha principal
- ⚽ Animación de entrada al vestuario (fade-up)

#### 📋 `README.md`

- ⚽ Acta de partido completa del proyecto

---

## 👥 Créditos

- **Dirección deportiva**: Proyecto IERD Duitama
- **Fotografía del estadio**: [Unsplash](https://unsplash.com)
- **Escudos y emblemas**: [Iconify](https://iconify.design) — Colección Lucide
- **Táctica visual**: [Tailwind CSS](https://tailwindcss.com)
- **Camisetas tipográficas**: [Google Fonts](https://fonts.google.com)

---

## 📄 Licencia

© 2026 IERD Duitama — Escuela Deportiva. Todos los derechos reservados.

> Hecho con 🔥 en Boyacá, Colombia ⚽