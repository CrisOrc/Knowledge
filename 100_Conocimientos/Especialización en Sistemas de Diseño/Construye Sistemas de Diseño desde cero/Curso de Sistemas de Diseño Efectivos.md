# ¿Qué es un Sistema de Diseño?
Los sistemas de diseño están en todas partes, su función tiene que ver con la planeación y la construcción de productos _(no necesariamente digitales)_.

Hace muchos años, un hombre llamado Malcom McLean transportaba mercancías en sus barcos, pero la descarga de todos estos objetos era muy compleja, todo tenía tamaños y pesos distintos. Para resolver este problema, McLean trabajo con un grupo de ingenieros y crearon los _containers_ o contenedores, cajas de metal que agilizan este proceso gracias la estandarización de todos los sistemas y medios de transporte de estos contenedores.

Esto mismo sucede cuando trabajamos con software, buscamos una manera de agilizar nuestros desarrollo estandarizando todos estos procesos. Los sistemas de diseño son conjuntos de reglas para un producto que se modifica dependiendo de las necesidades del mismo, son una decisión de negocio. Cualquier persona del equipo de producto debe estar involucrada en este proyecto y poder consultar toda esta documentación.

Para crear un sistema de diseño podemos usar diferentes herramientas como Bear, Notion o Evernote, lo importante es que podamos escribir y organizar estos sistemas.
# Principios del Sistema de Diseño
Los principios del diseño son la base fundamental de los paradigmas y metodologías que aplicaremos en nuestro sistema. Todas las decisiones que tomemos deben tener en cuenta y fundamentarse en estos principios, así evitamos cometer errores o generar conflictos, ya que todos los caminos serian correctos.

Principios del sistema de diseño:

- **Accesibilidad**: Nuestro producto debería ser usable para cualquier usuario, debemos construir productos **perceptibles**, **operables**, **entendibles** y **robustos**.
- **Consistencia**: Todo el equipo deben tener los mismos objetivos y deben hablarle de la misma forma a los usuarios, sea visualmente o por escrito.
- **Reusabilidad**: Cada hora que invirtamos trabajando en algún componente debe servir para construir otros componentes y evitar que tu o alguien más tenga que reconstruir nuestro trabajo.
- **Shareable**: Debemos construir y trabajar con herramientas que nos permitan compartir todo nuestro trabajo.

Podemos añadir otros principios que se adecuen correctamente a nuestra empresa, pero debemos tener cuidado de que todos estos principios sean compatibles entre sí.

En nuestro caso, añadiremos los principios de **_User Control_** _(el usuario debe tener la sensación de control sobre el producto)_, **_Forgiveness_** _(debemos permitir que el usuario pueda cambiar de opinión o volver a empezar algún proceso)_ y **_Perceived stability_** _(aún con plataformas robustas y complejas, el usuario debe percibir los procesos tan simples y familiares como sea posible)_.

# Niveles de Sistematización
El **_Design System Workflow_** nos ayuda a entender mucho mejor cómo entra, por dónde sale y por cuáles puntos pasa nuestro trabajo cuando trabajamos con sistemas de diseño.

En este _workflow_ o flujo de trabajo comenzamos diseñando y documentando para después hacer deploy _(un término de programación para los momentos en que pasamos nuestro trabajo a producción, una versión funcionando en vivo)_, en esta etapa de deploy debemos tener muy claro para cuál plataforma o entorno estamos trabajando, así tendremos mucho más claro todo lo que vamos a necesitar construir _(por ejemplo, cuando construimos páginas web trabajamos en archivos `.css` con los estilos de nuestros productos)_.

Pero el trabajo no termina aquí, después de hacer deploy entramos a la etapa de testing para evaluar la efectividad de estos estilos y seguirlos mejorando.

También vamos a aprender sobre **_Building Design Systems_**, donde construimos herramientas para que todos puedan usar e implementar las guías y los estilos que estamos trabajando. Para organizarnos y sistematizar estos procesos podemos implementar el modelo solitario, dónde tú, el diseñador haces todo el trabajo para que alguien más lo consuma, pero existen otros modelos como el centralizado o el confederado donde trabajamos con otras personas o incluso otros equipos y pedimos feedback dependiendo de la organización de nuestras empresas.
# Paradigmas: Diseño atómico, diseño procedural y DRY
Existen varios paradigmas de diseño que pueden guiarte en la construcción de tu sistema de diseño.

El paradigma **procedural** es la construcción de objetos variados para posteriormente construir nuestros sistemas a partir de estos elementos, es la construcción de funciones que en el futuro se construirán a sí mismas. En vez de construir todos los objetos de nuestro sistema, vamos a trabajar los elementos y reglas que se resolverán después. Por ejemplo, construir las mangas, el cuello u otros elementos para al obtener el resultado de un abrigo.

Otro paradigma que debemos entender es el **diseño atómico** para organizar los elementos de nuestros diseños y software. Los elementos independientes más sencillos de nuestro sistema _(labels, inputs, botones, títulos, etc)_ los conocemos como **átomos**, pero cuando juntamos átomos construimos **moléculas**, elementos sencillos unidos entre sí _(un buscador por ejemplo, el conjunto de label + input + botón)_, y formamos **organismos** cuando juntamos moléculas _(por ejemplo, una barra de navegación con logos, enlaces y un buscador)_.

Con la suma de estos organismos generamos **templates**, la forma más básica de nuestras plataformas qué podemos utilizar en diferentes partes de nuestros diseños aplicando pequeños cambios en los átomos, y cuando aplicamos estos cambios para las partes especificas de nuestro sitio obtenemos **páginas**, el resultado final de toda la organización de elementos independientes hasta formas conjuntos de organismos complicados y armónicos entre sí.

Por último, vamos a entender el paradigma **dry** _(Don’t Repeat Yourself)_ para construir elementos reciclables y no gastar tiempo volviendo a construir los mismos objetos una y otra vez.
# ¿Qué es un componente?
Los componentes forman parte de un todo, así como las velas de un pastel, el piso de los edificios o las partes de un motor cada una con su funcionalidad. Lo mismo pasa con las interfaces, vamos a construir diferentes elementos y herramientas para que los usuarios logren cumplir sus objetivos.

Todos los componentes tienen una entrada y una salida, el usuario realiza una acción y los elementos deben responder de alguna forma _(feedback)_, esta es la forma de comunicamos con los usuarios, trabajamos haciendo conversaciones para informar que todo esta funcionando correctamente y qué pasos deben seguir a continuación. Este proceso de comunicación lo conocemos como **interacción**.

Partes de un componente:

- Nombre _(así evitamos diferentes definiciones y establecemos los objetivos y funciones de nuestros componentes)_
- Descripción y solución _(en qué problema estamos trabajando y cómo deberíamos implementar estas soluciones)_
- _Behavior_ _(el comportamiento de nuestros componentes dentro del sistema)_
- States _(las variaciones y distintos comportamientos que pueden tener nuestros componentes dependiendo de su contexto)_

# Foundations
Los sistemas de diseño son un conjunto de reglas que organizamos con nuestros equipos, y los fundations son las partes más básicas que podemos configurar en nuestro sistema. Vamos a repasar cada una de estas bases mientras escribimos la documentación en Notion:

- Tipografía
- Colores
- _Layout_ y _spaces_ _(son las formas y espacios fundamentales que utilizamos para ordenar los elementos de nuestro sistema)_
- Iconografía
- _Styles (nuestra marca puede presentarse con estilos juguetones o realistas, lo importante es definir tan claro como sea posible qué intentamos transmitir)_
- Tono _(con qué personalidad o de qué forma debemos hablar con nuestra audiencia)_

# Tipografía
Cuando trabajamos con tipografía para software debemos tener en cuenta las implicaciones que estas pueden generar si trabajamos para dispositivos móviles o los requerimientos técnicos de alguna pantalla en particular. Un buen lugar para encontrar tipografías listas para el desarrollo y diseño de nuestros productos es [Google Fonts](https://fonts.google.com/).

Para definir y clasificar las características y peculiaridades en los elementos de nuestro diseño podemos basarnos las etiquetas de HTML para títulos y encabezados _(`H1`, `H2`, `H3`, `H4`, `H5` y `H6`)_, párrafos _(`p`)_ y párrafos más pequeños _(`small`)_. Podemos definir que los títulos se trabajen en negrita y con tamaños de fuente más grandes, lo importante es que estas reglas se acomoden al sistema de diseño que estamos trabajando.

# Cómo evitar colores constrastantes
Cuando utilizamos colores demasiado contrastantes podemos generar efectos visuales algo molestos, problemas en el _render_ o lineas blancas y negras en los bordes de los elementos. Para solucionar estos problemas visuales debemos elegir nuestros colores con mucho más cuidado, moviendo los colores hacia alguna tonalidad para evitar colores demasiado contrarios.

# Paleta de colores
Los colores también deben llevar algún tipo de clasificación ya que definen el estilo visual de nuestro sistema. [La paleta de colores](https://platzi.com/clases/1228-fundamentos-diseno/10147-paletas-de-color1263/) define el estilo de tu sistema de diseño y ayuda a definir el sistema de diseño, diferenciando la identidad de la marca y del resto de efectos y elementos visuales.

Muchos sistemas de diseño clasifican sus colores según sus productos _(un color para ventas, otro para servicio al cliente, etc)_, otros utilizamos Material Design y clasificamos los colores como _actions colors_, _secondary colors _ y otros niveles de clasificación. En realidad no importa, podemos tomar cualquier otro paradigma de fundamentos de color para nuestros sistemas, lo importante es clasificar el uso de estos colores y asegurarnos de que todo el equipo los entiende.

Para escoger estos colores debemos tener en cuenta los colores de la marca, los colores principales _(colores de acción o call to actions)_, colores secundarios, los grises y los colores de fondo. El trabajo se puede complicar un poco cuando tenemos en cuenta todos estos colores, pero el resultado será mucho mejor, los colores funcionaran correctamente entre todos.
# Reglas de espaciado
Las reglas de espaciado son muy útiles cuando trabajamos nuestros sistemas de diseño para anticipar la visualización de nuestras interfaces en diferentes dispositivos.

- **Ritmo**: Qué tan seguido aparecen elementos arriba o debajo de otros.
- **Padding**: Es el espacio dentro de nuestros elementos, nos ayuda a enfocar y transmitir los estilos de nuestra marca.
- **Margin**: Es el espacio entre elementos pero hacia afuera, nos permite generar ritmo visual o para separar elementos de secciones diferentes.
- **Border**: Trabajamos con el borde de los elementos, recuerda que las dimensiones o medidas de nuestros objetos se verán afectadas al aplicar o no aplicar estos bordes.
- **Layout**: Vamos a definir la forma general en que combinamos las columnas, headers y barras de navegación de nuestras plataformas, gracias a estas reglas podemos garantizar que nos adaptamos a todos los tamaños y dispositivos.

# Animación
Los 12 principios de la animación son un conjunto de reglas creadas por Disney para la animación de personajes, pero muchos de estos principios son muy útiles para ciertos aspectos de la animación de elementos de nuestras interfaces:

- **Anticipación**: Vamos a a preparar a los usuarios para la acción que viene a continuación, por ejemplo, antes de desconectar la señal de un teléfono podemos animar el icono del avión y transmitir que no señal durante algún tiempo.
- **Estirar y encoger**: Nos ayuda a generar drama sobre algún elemento, por ejemplo, para dramatizar la animación de un botón cuando el usuario ha cometido un error o alguna acción incorrecta.
- **Entradas y salidas lentas**: Nos permite introducir o remover elementos de la plataforma, tal vez conozcas estas animaciones como _Fade In_ y _Fade Out_.
- **Acciones secundarias**: Todas las microinteracciones trabajan con este principio, estas animaciones nos ayudan a transmitir o dar información adicional como respuesta a alguna acción de los usuarios.
- **Timing**: Mientras más detalles añadimos a las animaciones, más rápidas o lentas se pueden percibir. Podemos utilizar estos efectos visuales para transmitir apuro o tranquilidad mientras la plataforma esta cargando.
- **Exageración**: Así como las acciones secundarias, podemos exagerar los movimientos de nuestros elementos para transmitir alguna sensación, por ejemplo, cuando el usuario quiere eliminar su cuenta.

También vamos a utilizar [Animate.css](https://daneden.github.io/animate.css/), una librería para trabajar con todo tipo de animaciones sin mucho trabajo, también nos facilita el proceso de documentación de las reglas de animación de nuestro sistema.
# Voz y tono
Los textos o _copies_ que acompañan nuestros diseños también hace parte de la forma en que te comunicas con tus usuarios. Al incluir la voz y el tono de nuestros productos en el sistema de diseño conseguimos que todo el equipo tenga una guía sobre la personalidad de la marca, recuerda que toda esta documentación debe contribuir a la consistencia y comunicación con nuestros equipos.

Para definir la voz y el tono de nuestros sistemas debemos tener en cuenta los siguientes aspectos:

- Buzzwords: las palabras más usadas de nuestro producto
- Phrases: vamos a construir una librería de frases clave de nuestro producto
- Objetivo: el objetivo o la misión de nuestro producto en términos de voz y tono ayuda a que el equipo tenga orientación a la hora de crear nuevos textos o frases
- Características: definimos la personalidad de la marca, así tendremos mucho más contexto y podremos crear mejores _copies_ para nuestra marca



# Iconografía
Los iconos son muy útiles para comunicar o resaltar características y funcionalidades de nuestros productos, podemos construir nuestras propias librerías de iconos personalizados o utilizar librerías como [Font Awesome](https://fontawesome.com/) y completar los iconos que hagan falta si no tenemos un equipo tan grande.

Para definir las reglas y la documentación de una iconografía consistente debemos tener en cuenta los siguientes aspectos:

- Grid: Las medidas y lineamientos que deben seguir todos los iconos
- Shapes: Las formas o figuras que podemos utilizar
- Size: Qué tamaño deben tener nuestros iconos para estar alineados con la tipografía y el resto de la plataforma
- Styles: Cómo deben estar construidos visualmente nuestros iconos, podemos utilizar colores planos o podemos trabajar en iconos mucho más realistas, etc, lo importante es estar alineados con las reglas de nuestro sistema

# Hitos
Los **hitos** son características muy particulares o incluso personales de nuestros productos, las mejores marcas incluso pueden definirse y marcar su presencia sin necesidad de utilizar logos o nombres, tal es el caso de las animaciones de carga de Google o Slack.

# Un sistema basado en personas
Un sistema de diseño se asegura que todo lo que estás diseñando se convierta en software, debemos asegurarnos de que todos los elementos estén conectados para hacer nuestro trabajo más eficiente.

Los sistemas de diseño nos ayudan a construir software en equipo, involucrando al equipo de desarrollo, de marketing, de finanzas, etc, todos aquellos que contribuyen a la hora de crear un nuevo software y ayudan a que el trabajo fluya y sea más eficiente.

# Iteremos
El proceso de creación de software no es tan definitivo como la creación de otros tipos de producto, son productos vivos que siguen mutando y desarrollándose en el tiempo. Los sistemas de diseño también pueden prever la forma de iterar, es decir, mejorar todos los días las construcciones y la forma de construir del equipo, lo más importante es que entre todos nos pongamos de acuerdo de manera fácil, rápida y efectiva.

Para organizar el proceso de iteraciones debemos documentar todos los cambios y problemas que nos encontramos para que todo el equipo este actualizado y logremos entender el trabajo de la misma forma. Vamos a seguir los siguientes pasos:

- Darle un nombre a la iteración
- Describir por qué estamos iterando, ¿qué problema vamos a resolver?
- ¿Qué solución encontramos a estos problemas?
- Cambios de estimación de conflictos, la duración y la dificultad estimada para trabajar esta iteración