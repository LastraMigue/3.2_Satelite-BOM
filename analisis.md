# Documento de Análisis: Identificación de Objetos Predefinidos

---

## 1. Diferencia entre `window` (BOM) y Objetos Nativos Globales (`Math`, `JSON`)

| Ámbito | Definición y Propósito |
| :--- | :--- |
| **`window` (BOM)** | Representa la ventana del navegador web y actúa como el ámbito global (*global scope*) en el entorno del cliente. Permite interactuar directamente con el navegador, las pestañas, el historial, las dimensiones y las características del hardware. |
| **Objetos Nativos (Core JS)** | Formados por el núcleo estándar del lenguaje de programación (como `Math`, `JSON`, `Array`, `Object`, `Date`), diseñados para procesar datos, estructuras y cálculos con independencia absoluta del entorno del navegador. |

> [!NOTE]
> **¿Por qué no hace falta escribir `window.Math`?**  
> Como `window` es el objeto de más alto nivel que define el ámbito global en el cliente, cualquier objeto o función nativa del núcleo de JavaScript se encuentra disponible de forma implícita en este contexto global, por lo que el intérprete resuelve directamente su llamada.

---

## 2. Clasificación de las Instrucciones Utilizadas en la Práctica

| Instrucción | Clasificación | Descripción |
| :--- | :---: | :--- |
| `window.open()` | **BOM** | Método del objeto `window` para abrir y configurar nuevas ventanas o pestañas emergentes. |
| `parseFloat()` | **JS Nativo** | Función integrada para la conversión y análisis de cadenas de texto a números decimales. |
| `Math.floor()` | **JS Nativo** | Método del objeto integrado `Math` para realizar operaciones matemáticas, obteniendo la parte entera inferior. |
| `navigator.userAgent` | **BOM** | Propiedad de información del entorno del objeto `navigator` que identifica el sistema operativo y navegador del cliente. |
