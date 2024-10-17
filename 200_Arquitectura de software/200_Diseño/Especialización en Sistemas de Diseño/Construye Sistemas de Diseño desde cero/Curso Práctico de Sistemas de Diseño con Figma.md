# Anatomía de un Sistema de Diseño
### Anatomía de un Sistema de Diseño

Un sistema de diseño es un lenguaje y una fuente de verdad. Es un lugar donde hay información en la que podemos confiar (componentes con reglas claras). Y permite comunicarnos en torno a un lenguaje visual.

Sus partes fundamentales son:

- Guías de estilo: todo lo visual, botones, inputs, colores, textos, etc.
- Librería de patrones: interacciones, flujos, acciones que se repiten.
- Librería de componentes.

#### Beneficios

- **Ahorrar tiempo**: al tener los componentes creados, simplemente debemos replicarlos; lo cual nos ahorra mucho tiempo.
- **Consistencia**: permite que todo el producto se vea y se sienta muy similar o igual.
- **Organización**: tener reglas de diseño iguales, márgenes, paddings, tamaños, etc.
- **Flexibilidad**: permite a las personas que se sumen al equipo tener un mejor onboarding, entendiendo claramente las reglas de diseño de forma más rápida.
- **Colaboración**: permite colaborar con diferentes partes del equipo para armar un producto con reglas claras.
- **Estandarización**: permite tener un producto estandarizado con componentes reutilizables que podemos usar en todas las interfaces.

#### Desventajas

- No es tarea fácil crearlo. Lleva mucho tiempo.

Recordar que tiene más sentido crearlo si se trabaja iterativamente en un producto.

# ¿Cómo crear un sistema de diseño? Proceso, principios y flujo de trabajo

> Un sistema de diseño no se crea porque sí.

Debe existir una necesidad para crear un Design System (DS)

**Factores a considerar antes de crear un DS**

- **Contexto**: del producto.
- **Necesidades**: razones por las cuáles sería de beneficio implementar el Design System
---
**Pasos para definir el DS:**

1. **Revisar inconsistencias**: puede servir aplicar una evaluación heurística 🤓
2. **Armar equipos**: se necesita colaboración entre equipos, principalmente entre diseño y desarrollo, ya que es un producto de todos.
3. **Vender su importancia**: la forma en la que expresamos las ventajas de aplicarlo..
4. **Explorar otros DS**: para ver los patrones de diseño, los alcances, y empezar a definir nuestro propio sistema
5. **Definir fundamentos visuales**: corresponde a la guía de estilos del DS.
6. **Crear componentes**: dependiendo de las prioridades y la complejidad de cada uno.
7. **Construir patrones**: detectar experiencias y componentes que se repiten para definir y tener mapeados esos patrones.
8. **Mantenimiento**: se debe mantener al día, actualizando y adaptando a las necesidades que vayan surgiendo en el crecimiento e iteración del producto
---
**Proceso a nivel de diseño**

- **Evaluación del producto**: se evalúa la marca, la voz, el tono, la accesibilidad.
- **Creación de la librería**: colores, espaciados componentes, entre otros.
- **Documentación**: para mantener una comunicación y colaboración correcta con el equipo.
---
**Flujo de trabajo**

Definir cuáles son las metodologías de trabajo dentro del equipo

_Ejemplo: Design Sprint_

![design process.png](https://static.platzi.com/media/user_upload/design%20process-2db07953-b944-4ea1-843a-05dabf6b351e.jpg)
---
**Prototipado**

![prototipado.png](https://static.platzi.com/media/user_upload/prototipado-af50a46d-d1bb-4d9b-a920-940a8a2cf063.jpg)
---
**Principios**

Permiten sentar las bases de nuestro sistema de diseño, y por ende, los lineamientos que seguiremos en toda la creación de los productos


# Neo Brutalismo: tendencias de diseño y proyecto del curso
Neubrutalism, una tendencia de diseño, "Amor a lo feo" Textos muy grandes, bordes muy marcados, cualquier persona lo puede hacer.

Este es un concepto que sale de la arquitectura.

**Los fundamentos del proyecto son:**

- Type scale (Tipografía)
- Paleta de colores
- Espaciado
- Elevation.

**Componentes:**

- Buttons
- Cards
- header
- hero

# Conceptos y recursos importantes en Sistemas de diseño
Para documentar nuestro Sistema de Diseño, es importante que revisemos cuál es el objetivo y cuáles son las cosas que debemos incluir para cumplir con ese objetivo.  
Inicialmente, lo que queremos es que nuestro equipo conozca los fundamentos del Sistema de Diseño y cómo y cuándo usarlos. Por esta razón, debemos incluir a nivel general:

- Título e introducción
- Descripción de uso
- Tokens
- Do and Don’ts

Esto puede variar dependiendo del tipo de fundamento (si es color, tipografía, etc.) y de lo que el equipo de diseño considere pertinente para el diseño. Esto puede tener varias iteraciones y no necesariamente debe estar 100% perfecto y completo en un inicio. Lo importante es hacer una descripción detallada que de una clara idea del fundamento: cuál es su intención, cuál es su uso, qué cosas se pueden hacer y que otras cosas no, cuáles son los tokens, ejemplos, entre otras cosas. Imagina que estás escribiendo una especie de tutorial para personas de tu equipo que ya puedan llevar tiempo o que apenas están comenzando.

# Design Tokens: cómo y cuándo usarlos
**Design Tokens**: son un conjunto de valores predefinidos y reutilizables que representan los componentes visuales de un diseño, como colores, tipografía, espaciado, tamaños de elementos, etc. En lugar de definir estos valores directamente en el código, se crean tokens que se utilizan como variables y se llaman desde el código. Esto permite una mayor coherencia en el diseño, ya que los valores se pueden actualizar de manera centralizada y se aplican automáticamente en todo el diseño.

---

❌ “Los tokens de diseño son solo variables” es como decir “responsive design son solo media queries”

---

++¿Por qué usar Design Tokens?++

- Coherencia
- Única fuente de verdad
- Genera orden
- Permite colaboración
- Consistencia
- Permite hacer seguimiento

---

++Aplicación de los Design Tokens:++

![sistema.png](https://static.platzi.com/media/user_upload/sistema-afcb67af-38b5-45d8-8757-984aa211ac10.jpg)

---

++Tipos de tokens:++

Una arquitectura de tokens robusta y extensible depende de cuántos niveles de abstracción se tengan.

- **Tokens globales**: valores primitivos independientes del contexto heredado por otros tokens. Ej, el hexadecimal de un color.
- **Tokens de alias**: se relacionan con un contexto, son efectivos cuando un valor con una sola intención aparecerá en varios lugares.
- **Tokens específicos de componentes**: son la representación de cada valor asociado a un componente.

---

++Desventajas de los tokens++

- Se necesita un proceso sólido y convenciones de nomenclatura sólidas para que las cosas no se salgan de control y no sea una pesadilla de mantener.
- Se requiere una gran inversión inicial. Un sistema de tokens deficiente puede ser más perjudicial que beneficioso.

---

++Cómo saber si los tokens son adecuados para el equipo++

- Planeas actualizar el diseño o hacer uno nuevo.
- Tu diseño se aplica a más de un producto.
- Deseas mantener o actualizar estilos fácilmente en el futuro.

---

++Cuando no es necesario crear tokens++

- Los valores no cambiarán en 1 o 2 años.
- No se cuenta con un sistema de diseño.

---

++Tips para crear tokens++

- Realiza un inventario.
- Define criterios y convenciones de nomenclatura.
- Ten un rol de guardián o guardiana.
- Cumple con A11Y.

---

++¿Cómo funcionan los tokens en la vida real?++

- **Los protagonistas**: diseño y desarrollo.
- La realidad es diferente al hacer el Handoff.
- Las herramientas de ambos equipos necesitan poder comunicarse.

# Cómo calcular escalas tipográficas matemáticamente
	**Escala tipográfica**: es esencialmente un rango de tamaños de letra definidos por una proporción.

---

**Proporción aurea**: La proporción áurea, también conocida como la divina proporción, es un número irracional que se aproxima a 1,618. Se utiliza en matemáticas y arte por su estética agradable y armónica. Se dice que se encuentra en la naturaleza en formas como la espiral de una concha o la disposición de hojas en un tallo.

---

**Base**: de donde partimos la escala

**Radio**: la distancias entre las escalas

---

**Tercera**: intervalos que se producen entres dos notas

**Tercera menor**: corresponde a la relación de frecuencias 6:5

---

++Fórmula para definir las escalas basado en la proporción áurea:++

Multiplicando la base por el número aureo. Ejemplo:

12 x 1,618

---

++Proporciones de escala tipográfica comunes:++

Tomada de la música

![escala.png](https://static.platzi.com/media/user_upload/escala-0c414d7c-6182-4e15-b070-57434e8d0768.jpg)

# Cómo escoger colores: psicología, pautas y accesibilidad
**A11Y**: es una abreviatura comúnmente utilizada para referirse a "accesibilidad", que se refiere a la práctica de hacer que los productos, servicios, entornos y tecnologías sean accesibles para todas las personas, independientemente de sus habilidades o discapacidades.

---

++Proceso de creación de un sistema de colores (recomendados):++

- **Organizar los colores base en grupos**.
- **Crear variaciones de los colores base**.
- **Definir convenciones de nomenclatura**: cómo nombrar nuestros colores.
- **Validar A11Y**: hay que asegurar la accesibilidad
- **Establecer pautas de uso**: documentación de los patrones de diseño. Se incluye también la escala de color: porcentajes de uso.

---

++Cómo organizar los colores base en grupos++

> 💡 Es primordial para asegurar una buena documentación

1. Primarios
2. Secundarios
3. Neutros
4. Semánticos: vienen siendo los booleanos. Sirven para darle feedback a los usuarios.

---

++Psicología del color++

Los colores tienen significado prestablecidos (generalmente aceptados), que me gusta definir más como los estereotipos asociados a los colores.

---

++Crear variaciones de los colores base++

- Se generan para satisfacer diferentes usos
- Se escogen pocos para reducir la carga cognitiva
- Más opciones = más carga cognitiva = más mantenimiento

---

++Definir convenciones de nomenclatura++

- Definimos el Design Token. Ejemplo: `primary-300`

🤓 En mi caso personal, utilizo una nomenclatura similar a [Figma](https://www.youtube.com/watch?v=1DTnojio89Y&t=937s)

---

++Validar funcionalidad y A11Y++

- Reemplazar los colores en el diseño verificando si cumplen el propósito
- Que cumplan las pautas de contraste

🤓 Para este utilizo un Plugin llamado [A11Y en Figma](https://www.figma.com/community/plugin/733159460536249875/A11y---Color-Contrast-Checker)

---

++Establecer pautas de uso++

Ejemplos:

- ¿Qué sombra debo usar para el texto secundario?
- ¿Cuál debería ser el color de fondo de los CTA?
- ¿Qué colores se van a utilizar en los elementos deshabilitados?

# Espaciado y elevación
**Breakpoints**: es un punto específico en la medida de la pantalla donde el diseño de la interfaz de usuario se ajusta para adaptarse a diferentes dispositivos o resoluciones, proporcionando una experiencia de usuario óptima y coherente.

---

++Se pueden usar dos tipos de escalas de espaciados++

- **Espaciado de componentes**: comenzando con unidades pequeñas. Ejemplo, 4px.
- **Espaciado de layout**: Distribución de las pantallas (Grids)

---

++Breakpoints++

- Mobile: 640px
- Tablet: 768px
- Laptop: 1024px
- Desktop: 1280px

---

++Consideraciones++

1. Usar menos espacio entre componentes que comparten una relación cercana (Ley de proximidad)
2. Pueden existir excepciones en donde no haya espaciado. Ejemplo, al centrar tomando en cuenta el texto.
3. Las diferentes plataformas tienen diferentes unidades de medida iOS: PT Android: DP Web: PX

---

++Elevación++

Representa la distancia y la jerarquía entre 2 superficies en el eje Z
# Guía de iconos e ilustraciones en Figma
**Iconos**: ayudan a comprender rápida y claramente cómo funcionan las cosas en cada experiencia

---

**Ilustración**: agregan información no verbal, contexto y comprensión de lo que se está haciendo

---

++Consideraciones en los iconos++

- **Agruparlos**: bajo temas o funcionalidades.
- **Usarlos cerca a un texto**: los iconos no reemplazan palabras.
- **Establecer pautas**: guía de usos y aplicación.

---

++Consideraciones en las ilustraciones++

- **Ser consistentes**: mantener el mismo estilo
- **Evitar distracciones**: hay que mantener presente el objetivo del usuario en cada parte donde interactúe con el producto
- **Usar la misma paleta**
- **Acercarlas al mundo real**
- **Establecer pautas**

# Cómo Documentar Sistemas de Diseño
Para documentar nuestro Sistema de Diseño, es importante que revisemos cuál es el objetivo y cuáles son las cosas que debemos incluir para cumplir con ese objetivo.  
Inicialmente, lo que queremos es que nuestro equipo de diseño y desarrollo conozca qué componentes hay y cómo puede utilizarlos. Por esta razón, como buenas prácticas debemos incluir en la documentación:

- Título e introducción
- Anatomía del componente
- Arquitectura del componente (donde están incluidas las variantes)
- Ejemplos del componente con las diferentes variantes
- Descripciones de uso
- Consideraciones adicionales (como por ejemplo de accesibilidad)

Esto puede variar dependiendo del componente y de lo que el equipo de diseño considere pertinente para el diseño. Esto puede tener varias iteraciones y no necesariamente debe estar 100% perfecto y completo en un inicio. Lo importante es hacer una descripción detallada que de una clara idea del componente: cómo es, qué variantes tiene, cuáles son sus dimensiones, ejemplos de uso, entre otras cosas. Imagina que estás escribiendo una especie de tutorial para que personas de tu equipo (que ya puedan llevar tiempo o que apenas están comenzando) puedan diseñar pantallas con estos componentes.
# Atomic Design
**ATOMIC DESIGN** . **Brad Frost** encontró inspiración en la Química, y basado en eso es que desarrolló el concepto y metodología de diseño de Atomic Design. .

- **Átomos** - Elementos de la interfaz que no se pueden dividir más y sirven como bloques de construcción. Ejemplos: Label, botón, input .
- **Moléculas** - Son agrupaciones de átomos que conforman componentes de interfaz de usuario relativamente simples. Ejemplo: Barra de búsqueda .
- **Organismos** - Son componentes relativamente complejos que forman secciones discretas de una interfaz. Ejemplos: Header, footer, etc. .
- **Templates** - Colocan componentes dentro de un diseño y demuestran la estructura de contenido subyacente al diseño. Ejemplo: Plantilla de Home .
- **Páginas** - Aplican contenido real a las plantillas (templates). Ejemplo: Landing page completa con imágenes, links y texto reales

# Arquitectura y auditoría de componentes
Definir las variantes de un compoentente por ejemplo en un boton, definir "Size", style (Filled), state (Active).

Estado de los compoennte con el fin de:

- Orden de prioridades
- categoria atomica
- su fase en diseno
- su fase en desarrollo
- su fase de documentacion.

Esta auditoria seria genial, hacerlo en un notion, excel, etc.

En la arquitectura podriamos definir, los tamanos, estilos, estados, si va en mobile o desktop, si lleva CTA o no, etc. . .
https://www.knapsack.cloud/calculator