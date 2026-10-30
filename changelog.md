**Novedades en v2.3.0:**
- **Selector de orden de enlace** (— simple, = doble, ≡ triple) en la barra de notación del modo Calculadora y en la barra de herramientas del modo Ruta.
- **Herramienta "Seleccionar"** en el modo Ruta: clic sobre el primer átomo (se resalta en azul) y clic sobre el segundo para crear el enlace con el orden activo. Si el enlace ya existía, se actualiza el orden.
- **Shift + clic** en Calculadora ahora respeta el orden de enlace seleccionado (antes siempre creaba enlace simple).
- **Drag & drop con orden de enlace**: al soltar un elemento cerca de otro átomo (≤ 40 px) en cualquiera de los dos modos, se crea el enlace con el orden activo.
- **Atajos de teclado 1 / 2 / 3** para cambiar rápidamente el orden de enlace (ignorados si el foco está en un input de texto).
- **Corrección del resaltado visual**: el halo al seleccionar un átomo en el modo Ruta pasa de verde fluorescente (`#486648`) a azul medio (`#1B5BA1`), más sobrio y coherente con el nuevo selector.
- **Estilos defensivos**: se añadió `outline: none` a los `canvas`, wrappers y elementos arrastrables para eliminar halos no deseados del navegador al hacer foco.
- Actualización de la documentación (README y Changelog) a la versión 2.3.0.

**Novedades en v2.2.0:**
- Nuevo **modo Ruta**: lienzo de gran formato (1600 × 1000 px) para dibujar diagramas metabólicos con moléculas arrastrables y flechas.
- Herramientas de dibujo en modo Ruta: **Mover**, **Flecha recta**, **Flecha curva** (curvatura automática) y **Borrar** (moléculas y flechas).
- **Exportación a PNG** del diagrama completo mediante el botón "Guardar Imagen" (fondo blanco, resolución nativa).
- Añadido el grupo funcional **–PO₃²⁻** (fosfato ácido) al panel lateral, al parser de notación y a la generación de nombres IUPAC.
- Ajuste dinámico del tamaño de etiqueta para grupos con más de 3 caracteres (p. ej. `PO₃²⁻`).
- El botón "Limpiar" ahora actúa según el modo activo (Calculadora o Ruta).
- `Escape` cancela el dibujo de flecha en curso y libera la molécula arrastrada en modo Ruta.
- Actualización de la documentación (README y Changelog) a la versión 2.2.0.

**Novedades en v2.1.0:**
- Sistema de nomenclatura mejorado con detección completa de todos los elementos (incluyendo metales y no-CH)
- Corrección del sistema de zoom para alinear correctamente la posición visual con la funcional
- Botones de minimizar/maximizar en cada sección de reacción para mejor organización
- Aumento de altura de las secciones de reacción (280px min-height, 500px max-height)
- Mejor visibilidad del campo de notación con fondo blanco y texto negro
- Expansión masiva de la base de datos de nomenclatura IUPAC y nombres comunes
- Detección inteligente de grupos funcionales y elementos metálicos
- Nombres IUPAC hasta eicosano (20 carbonos) y compuestos inorgánicos completos
- Creación de Changelog e integración en el html
- Actualización a Github

**Novedades en v2.0.2:**
- Mejora de interfaz
- Corrección de errores del zoom
- Agregado de Grupos y Elementos periodicos

**Novedades en v2.0.1:**
- Corrección de errores en el parser de notación
- Mejora en la detección de grupos funcionales
- Optimización del rendimiento

**Novedades en v2.0.0:**
- División de pantalla en secciones independientes para reactivos, condiciones y productos
- Simulación de reacciones químicas con notación especializada
- Generación automática de nombres IUPAC con opción de cambiar a nomenclatura común
- Zoom independiente en cada sección con teclas 'i' y 'o'
- Ampliación de la tabla periódica con más elementos (Na, K, Ca, Mg, Fe, Cu, Zn, Mn, Co, Ni)
- Nuevos grupos funcionales (CHO, CN, SH, SO3H, PO4, COO⁻, NH3⁺)
- Nuevas biomoléculas (serina, valina, leucina, fructosa, sacarosa, colesterol)
- Subida a Github

**Novedades en v1.0.2:**
- Corrección de errores en el parser de notación
- Corrección en errores de objetos
- Corrección en errores de el view del README
- Mejora en la legibilidad del código

**Novedades en v1.0.1:**
- Corrección de errores en la estructura del js
- Mejora en los json del js
- Mayor información en la interfaz
- Iconos usando FontAwesome