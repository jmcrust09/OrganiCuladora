# Calculadora de Química Orgánica

**Versión 1.0.0**
*Representación molecular interactiva con notación lineal compacta y simulación 3D aparente.*

---

## Descripción General

La **Calculadora de Química Orgánica** es una herramienta web interactiva que permite construir moléculas orgánicas mediante una interfaz dual: un editor gráfico con arrastre de átomos y grupos funcionales, y un intérprete de notación textual compacta. Cada átomo se representa como un círculo con sombreado que simula profundidad tridimensional (efecto *faux-3D*) y el sistema ofrece retroalimentación inmediata, generando el nombre IUPAC de la molécula resultante.

La aplicación está orientada a estudiantes, docentes e investigadores que requieran visualizar estructuras de forma ágil, desde grupos alquilo simples hasta biomoléculas complejas como proteínas, carbohidratos y lípidos.

---

## Características Principales

- **Construcción visual por arrastre**
  Cada elemento químico o grupo predefinido se muestra como una esfera 2D con sombras, simulando un objeto tridimensional. Las figuras pueden arrastrarse libremente sobre el lienzo para formar enlaces.
- **Elementos individuales y grupos predefinidos**
  Además de átomos (C, H, O, N, S, P, etc.), se ofrecen grupos de uso común: `–CH₃`, `–CH₂–`, `–CH–`, anillo de benceno, así como módulos complejos (aminoácidos, monosacáridos, ácidos grasos) que representan proteínas, carbohidratos y lípidos.
- **Notación textual compacta**
  Admite una sintaxis inspirada en SMILES pero optimizada para escritura manual rápida, con delimitadores especiales para ramificaciones, multiplicidad y estereoquímica relativa.
- **Dos modos de visualización**
  
  - **Calculadora gráfica:** lienzo interactivo con los círculos 3D.
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

### Ejemplos

1. **3-metilpentano**
   `CH3 - CH2 - CH[<CH3] - CH2 - CH3`
   *Interpretación:* un metilo (`CH3`) unido hacia arriba en el tercer carbono.
2. **2,2-dimetilpropano con doble enlace**
   `CH3 - C[<>(CH3)2] = CH2`
   *Interpretación:* el carbono 2 lleva dos metilos, uno arriba y otro abajo (indicado por `<>`), y forma un enlace doble con el carbono 3.
3. **Benceno con grupo nitro**
   `AnilloBenceno - NO2`
   *Los grupos cíclicos pueden escribirse como palabra clave; el sistema los despliega automáticamente.*

---

## Elementos Predefinidos (Arrastre Directo)

Desde el panel lateral pueden insertarse directamente:

- **Átomos individuales:** H, C, N, O, P, S, halógenos.
- **Grupos alquilo:** `–CH₃`, `–CH₂–`, `–CH–` (con valencias libres para enlazar).
- **Anillo de benceno:** estructura cíclica de seis carbonos con aromaticidad.
- **Biomoléculas modulares:**
  - *Proteínas:* fragmentos de aminoácidos (glicina, alanina) representados como cadenas con grupo amino y carboxilo.
  - *Carbohidratos:* anillos de piranosa/furanosa simplificados.
  - *Lípidos:* cadenas de ácidos grasos (ej. `CH3(CH2)16COOH`).

La selección es fluida: al soltar un grupo sobre un átomo del lienzo, se genera el enlace correspondiente y se actualiza la notación textual automáticamente.

---

## Modos de la Interfaz

### 1. Calculadora Gráfica

- Lienzo blanco con bordes rectos (sin `border-radius`).
- Cada átomo se representa como un círculo con degradado radial y sombra paralela, dando ilusión de esfera 3D.
- Las conexiones se dibujan como líneas rectas o dobles según el tipo de enlace.
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

---

## Créditos y Licencia

Desarrollado por WM – 2026.
Licencia Libre sin restricción

---

*Este documento es parte integral del proyecto y puede visualizarse desde la propia aplicación en la pestaña "README".*
*Para contribuciones o reporte de errores, por favor abra un issue en el repositorio oficial.*
