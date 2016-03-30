Introducción
=================

**Jade** es un *motor de plantillas HTML* similar a **Handlebars** o **Moustache**.  Si bien hay diferencias entre ellos (como puede ser el nivel de abstracción del código HTML), el principal objetivo es claro: *Facilitar la elaboración de páginas y reutilización del código*.

Si tenemos 10 páginas que comparten la estructura principal y varían en función de la sección, no es nada práctico que si queremos cambiar un elemento del `<head>` o de la estructura tengamos que hacerlo en todas las páginas.

En general, estos motores de plantillas lo que nos permiten es la posibilidad de heredar o reutilizar partes de una página, lo que entendemos como layouts y añadir la posibilidad de generar un contenido en función de un código y el uso de variables.

## ¿Cuál es la principal diferencia de Jade?

Jade ha conseguido mucha popularidad en gran parte gracias a **Express** ya que se suele usar como motor de plantillas en ese frameworks.  Hay 2 aspectos que lo diferencian en gran medida de otros motores y son:

* Abstracción del código HTML
* Uso de la indentación para establecer la jerarquía o bloques

## Abstracción del código HTML

Mientras que otros motores lo que hacen es el mismo código HTML reutilizarlo añadiendo algunas funcionalidades extra, **Jade** utiliza otra sintaxis, si bien, las etiquetas son las mismas, la forma de representarlas, cambia.

Los más puristas del HTML usan este argumento como motivo para no usar **Jade**, a mi modo de ver, sabiendo HTML todo lo que sea facilitar la lectura del código, haciéndolo más *limpio* me parece una ventaja.

## Uso de la indentación

Esto es muy de **Python** y yo lo agradezco enormemente.  Es una buena forma, más aún combinado con la abstracción mencionada antes, para generar un código claro, limpio, bonito y mantenible.

Inicialmente, va a ser uno de los motivos por los que falle la compilación ya que es un tanto sensible en tanto que o usamos espacios o tabulaciones, pero si usamos una mezcla de ambos fallará.

Mi recomendación, para evitaros problemas, configurad vuestro editor para usar espacios y convertir las tabulaciones en espacios, una buena herramienta es [EditorConfig](http://editorconfig.org/) que podéis usarlo con vuestro editor habitual.  