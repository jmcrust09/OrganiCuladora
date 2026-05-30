# OrganiCuladora

**Versión 2.1.0**
*Representación molecular interactiva con notación lineal compacta, simulación de reacciones y simulación 3D aparente.*

---

## Descripción General

La **Calculadora de Química Orgánica** es una herramienta web interactiva que permite construir moléculas orgánicas y simular reacciones químicas mediante una interfaz dual: un editor gráfico con arrastre de átomos y grupos funcionales, y un intérprete de notación textual compacta. Cada átomo se representa como un círculo con sombreado que simula profundidad tridimensional (efecto *faux-3D*) y el sistema ofrece retroalimentación inmediata, generando el nombre IUPAC de la molécula resultante.

La aplicación está orientada a estudiantes, docentes e investigadores que requieran visualizar estructuras de forma ágil, desde grupos alquilo simples hasta biomoléculas complejas como proteínas, carbohidratos y lípidos.

---

## Características Principales

- **Construcción visual por arrastre**
  Cada elemento químico o grupo predefinido se muestra como una esfera 2D con sombras, simulando un objeto tridimensional. Las figuras pueden arrastrarse libremente sobre el lienzo para formar enlaces.
- **Elementos individuales y grupos predefinidos**
  Además de átomos (C, H, O, N, S, P, halógenos, metales alcalinos y de transición), se ofrecen grupos de uso común: `–CH₃`, `–CH₂–`, `–CH–`, `–OH`, `–NH₂`, `–COOH`, `–CHO`, `–CN`, `–SH`, `–SO₃H`, `–PO₄`, `–COO⁻`, `–NH₃⁺`, anillo de benceno, así como módulos complejos (aminoácidos, monosacáridos, ácidos grasos, colesterol) que representan proteínas, carbohidratos y lípidos.
- **Simulación de reacciones químicas**
  La pantalla se divide en secciones independientes para reactivos, condiciones y productos. Cada sección tiene su propio lienzo con zoom independiente.
- **Notación de reacciones**
  Admite sintaxis especializada para reacciones: `+` para compuestos múltiples, `-->` para separar reactivos de productos, `_` para espacios en blanco, y `-(condición)->` para especificar solventes y temperaturas.
- **Nombres IUPAC y nomenclatura común**
  Cada sección muestra automáticamente el nombre IUPAC del compuesto. Al hacer clic, cambia entre nomenclatura IUPAC y nombre común.
- **Zoom independiente**
  Cada sección puede hacer zoom con los botones +/- o con las teclas 'i' (zoom in) y 'o' (zoom out) cuando el cursor está sobre la sección.
- **Notación textual compacta**
  Admite una sintaxis inspirada en SMILES pero optimizada para escritura manual rápida, con delimitadores especiales para ramificaciones, multiplicidad y estereoquímica relativa.
- **Dos modos de visualización**
  
  - **Calculadora gráfica:** lienzo interactivo con los círculos 3D dividido en secciones de reacción.
  - **Documentación Markdown:** visor integrado con la guía de formato y referencia del proyecto (este mismo documento).
- **Validación y alertas**
  Los errores de sintaxis o combinaciones químicamente inviables se notifican mediante una alerta estilizada en la esquina inferior izquierda, sin interrumpir el flujo de trabajo.

---

## Diseño Visual

La interfaz sigue un estilo **brutalista industrial** con ligeros acentos orgánicos:

| Elemento               | Color            | Código HEX |
|------------------------|------------------|------------|
| Fondo principal        | Blanco rectangular (sin bordes redondeados) | `#FFFFFF` |
| Bordes y líneas        | Gris oscuro      | `#2E2E2E` |
| Acentos (enlaces, botones activos, resaltes) | Verde musgo | `#486648` |
| Detalles secundarios (etiquetas, sombras) | Beige neutro | `#BEAF9D` |
| Texto principal        | Negro carbón     | `#1A1A1A` |

*Nota: En la versión oscura de la interfaz (alternativa), los acentos verdes sustituyen a los azules del ejemplo brutalista original, manteniendo una coherencia cromática con el tema de química orgánica.*

---

## Formato de Representación Molecular (Notación Lineal)

La cadena principal y las ramificaciones se escriben usando los siguientes símbolos:

| Símbolo               | Significado                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| `-`                   | Enlace simple entre átomos o grupos                                         |
| `=`                   | Enlace doble                                                                |
| `=-`                  | Enlace triple (guion + igual)                                               |
| `==`                  | Enlace cuádruple (poco común, metales de transición)                        |
| `[grupo]`            | Grupo que se proyecta **hacia abajo** del plano (cuña punteada/rayada)      |
| `(grupo)n`            | Multiplicador: repite el grupo *n* veces (ej. `(CH2)4` → cadena de 4 metilenos) |
| `<>` dentro de `[]`   | Indica dirección de un subgrupo dentro de un corchete que ya define orientación |
| `+`                   | Separa compuestos múltiples en la misma sección                             |
| `-->`                 | Separa reactivos, condiciones y productos de la reacción                    |
| `_`                   | Espacio en blanco (el programa lo interpreta como vacío)                    |
| `-(condición)->`      | Especifica condiciones de reacción (solvente, temperatura, catalizador)      |

### Ejemplos de Moléculas

1. **3-metilpentano**
   `CH3 - CH2 - CH[<CH3] - CH2 - CH3`
   *Interpretación:* un metilo (`CH3`) unido hacia arriba en el tercer carbono.
2. **2,2-dimetilpropano con doble enlace**
   `CH3 - C[<>(CH3)2] = CH2`
   *Interpretación:* el carbono 2 lleva dos metilos, uno arriba y otro abajo (indicado por `<>`), y forma un enlace doble con el carbono 3.
3. **Benceno con grupo nitro**
   `AnilloBenceno - NO2`
   *Los grupos cíclicos pueden escribirse como palabra clave; el sistema los despliega automáticamente.*

### Ejemplos de Reacciones

1. **Combustión del metano**
   `CH4 + 2O2 --> CO2 + 2H2O`
   *Interpretación:* metano más oxígeno produce dióxido de carbono y agua.
2. **Esterificación con condiciones**
   `CH3 - COOH + CH3 - CH2 - OH - H2SO4 / 140°C --> CH3 - COO - CH2 - CH3 + H2O`
   *Interpretación:* ácido acético más etanol con ácido sulfúrico a 140°C produce acetato de etilo y agua.
3. **Reacción con espacio en blanco**
   `CH3 - CH2 - OH + _ --> CH3 - CHO + _`
   *Interpretación:* etanol más un reactivo desconocido produce acetaldehído y un producto desconocido.*

---

## Elementos Predefinidos (Arrastre Directo)

Desde el panel lateral pueden insertarse directamente:

- **Átomos individuales:** H, C, N, O, P, S, halógenos (Cl, Br, I, F), metales alcalinos (Na, K), metales alcalinotérreos (Ca, Mg), metales de transición (Fe, Cu, Zn, Mn, Co, Ni).
- **Grupos alquilo:** `–CH₃`, `–CH₂–`, `–CH–` (con valencias libres para enlazar).
- **Grupos funcionales:** `–OH`, `–NH₂`, `–COOH`, `–CHO`, `–CN`, `–SH`, `–SO₃H`, `–PO₄`, `–COO⁻`, `–NH₃⁺`.
- **Anillo de benceno:** estructura cíclica de seis carbonos con aromaticidad.
- **Biomoléculas modulares:**
  - *Proteínas:* fragmentos de aminoácidos (glicina, alanina, serina, valina, leucina) representados como cadenas con grupo amino y carboxilo.
  - *Carbohidratos:* anillos de piranosa/furanosa simplificados (glucosa, fructosa, sacarosa).
  - *Lípidos:* cadenas de ácidos grasos (ej. `CH3(CH2)16COOH`) y colesterol.

La selección es fluida: al soltar un grupo sobre un átomo del lienzo de cualquier sección, se genera el enlace correspondiente y se actualiza la notación textual automáticamente.

---

## Modos de la Interfaz

### 1. Calculadora Gráfica

- Pantalla dividida en secciones independientes: Reactivo 1, Reactivo 2, Condiciones, Producto.
- Cada sección tiene su propio lienzo blanco con bordes rectos (sin `border-radius`).
- Cada átomo se representa como un círculo con degradado radial y sombra paralela, dando ilusión de esfera 3D.
- Las conexiones se dibujan como líneas rectas o dobles según el tipo de enlace.
- Cada sección tiene controles de zoom (+/-) y muestra el nombre IUPAC del compuesto.
- Al hacer clic en el nombre IUPAC, cambia entre nomenclatura IUPAC y nombre común.
- Teclas 'i' y 'o' permiten zoom in/out en la sección donde está el cursor.
- Panel superior con botones para cambiar entre modo **Calculadora** y **README**.

### 2. Visor Markdown (README)

- Muestra el presente documento con formato completo (encabezados, tablas, código).
- Permite consultar la sintaxis mientras se trabaja en el otro modo.
- El contenido está estático pero se puede actualizar con nuevas versiones de la herramienta.

---

## Manejo de Errores

Cuando se ingresa una cadena de texto que no cumple la gramática definida, aparece una notificación en la esquina **inferior izquierda** con el siguiente comportamiento:

- Fondo beige (`#BEAF9D`) y borde verde (`#486648`).
- Texto en rojo oscuro para el mensaje de error.
- Desaparece tras 5 segundos o al hacer clic en ella.
- No bloquea la interacción con el lienzo.

Ejemplos de errores detectados:

- Paréntesis no balanceados.
- Multiplicador no numérico (ej. `(CH3)x`).
- Uso de `<>` fuera de un bloque `[]`.
- Enlaces inconsistentes (cuádruple entre carbonos sin justificación).

---

## Tecnologías Utilizadas

- **Frontend puro:** HTML5, CSS3, JavaScript (Vanilla).
- Sin dependencias externas.
- Renderizado de moléculas mediante Canvas API.
- Parsing de notación lineal con algoritmo de análisis sintáctico descendente recursivo.

---

## Referencias de Sintaxis

| Símbolo | Nombre       | Ejemplo               | Resultado esperado                       |
|---------|--------------|-----------------------|------------------------------------------|
| `-`     | Enlace simple | `CH3 - CH3`          | Etano                                    |
| `=`     | Enlace doble | `CH2 = CH2`          | Eteno                                    |
| `=-`    | Enlace triple | `CH =- CH`           | Etino (acetileno)                        |
| `==`    | Enlace cuádruple | `Cr == Cr`        | Anión dicromato (solo metales)           |
| `[X]`  | Cuña abajo   | `C[>Cl]`             | Cloro orientado hacia atrás              |
| `<>`    | Dirección dual dentro de `[]` | `C[<>(CH3)2]` | Dos metilos, uno arriba y otro abajo      |
| `(X)n`  | Repetición   | `(CH2)4`             | Cadena de cuatro metilenos               |
| `+`     | Compuestos múltiples | `CH3 + O2`       | Metano más oxígeno                       |
| `-->`   | Reacción    | `CH4 + O2 --> CO2 + H2O` | Combustión del metano                   |
| `_`     | Espacio en blanco | `A + _ --> B + _`   | Reactivo/producto desconocido            |
| `-(cond)->` | Condiciones | `A + B - H2SO4 / 140°C --> C` | Reacción con catalizador y temperatura |

---

## Atajos de Teclado

- **i** - Zoom in en la sección donde está el cursor
- **o** - Zoom out en la sección donde está el cursor
- **Shift + clic** en dos átomos: crear enlace entre ellos
- **Doble clic** en un átomo: eliminarlo
- **Escape** - Cancelar modo de conexión
- **Delete** - Eliminar átomo seleccionado
- **Enter** en campo de notación: parsear la notación

## Créditos y Licencia

Desarrollado por WM – 2026.
Licencia Libre sin restricción

**Versión 2.1.0** - Actualización con sistema de nomenclatura mejorado, corrección de zoom, minimización de secciones y expansión masiva de base de datos de compuestos.

---

*Este documento es parte integral del proyecto y puede visualizarse desde la propia aplicación en la pestaña "README".*
*Para contribuciones o reporte de errores, por favor abra un issue en el repositorio oficial.*