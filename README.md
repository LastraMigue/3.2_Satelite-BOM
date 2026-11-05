# Práctica 3.2: Satélite BOM - Control de Ventanas en JavaScript

Proyecto desarrollado para poner en práctica la interacción real entre ventanas del navegador mediante el **BOM (Browser Object Model)**, el control del historial de navegación, la detección del entorno y el uso de temporizadores asíncronos en JavaScript.

---

## Documento de Análisis Teórico

Antes del desarrollo de la práctica, se realizó la identificación y clasificación de los objetos predefinidos del lenguaje:

**[Consulta aquí el Documento de Análisis (analisis.md)](./analisis.md)**

En dicho documento se explican:
* La diferencia conceptual entre el objeto global del navegador (`window`) y los objetos nativos del núcleo de JavaScript (`Math`, `JSON`).
* Por qué no es necesario invocar `window.Math`.
* La clasificación técnica de las funciones y métodos utilizados en el proyecto (`window.open()`, `parseFloat()`, `Math.floor()`, `navigator.userAgent`).

---

## Funcionalidades Principales

1. **Ventana Madre (`src/index.html`)**:
   * **Centrado dinámico**: Calcula en tiempo real las coordenadas exactas de pantalla mediante `screen.availWidth` y `screen.availHeight` para abrir la ventana secundaria centrada en cualquier monitor.
   * **Apertura controlada**: Lanza la ventana satélite mediante `window.open()` con dimensiones fijas de 400x300 píxeles.

2. **Ventana Satélite (`src/satelite.html`)**:
   * **Detección del Entorno**: Lee e interpreta `navigator.userAgent` para detectar si el usuario navega desde **Windows**, **Mac** o **Linux**, inyectando un mensaje de bienvenida personalizado en el DOM.
   * **Control de Navegación e Historial**:
     * `Redirigir con Historial`: Utiliza `window.opener.location.assign()` permitiendo al usuario volver atrás.
     * `Redirigir sin Historial`: Utiliza `window.opener.location.replace()` sustituyendo la entrada de historial para impedir el retroceso.
   * **Autodestrucción y Temporizadores**: Cuenta atrás visual segundo a segundo (`setInterval()`) que culmina cerrando la ventana de forma autónoma con `setTimeout()` y `window.close()`.

---

## Estructura del Repositorio

```text
3.2_Satelite-BOM/
├── README.md             # Documentación general del repositorio
├── analisis.md           # Análisis técnico sobre el BOM y objetos nativos
└── src/
    ├── index.html        # Ventana principal (madre)
    ├── satelite.html     # Ventana secundaria (satélite)
    └── css/
        ├── index.css     # Estilos de la ventana principal
        └── satelite.css  # Estilos de la ventana satélite
```

---

## Enlace del Proyecto

Puedes acceder y probar la aplicación en vivo a través de GitHub Pages:

**[Ver Proyecto en GitHub Pages](https://lastramigue.github.io/3.2_Satelite-BOM/)**

> **URL directa:** `https://lastramigue.github.io/3.2_Satelite-BOM/`
