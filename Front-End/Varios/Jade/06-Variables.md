Variables e interpolación
=========================

## Variables

*Jade* Nos permite la utilización de variables, ya sea para utilizarlas directamente, para facilitar la legibilidad, reutilización de código o usarlo en sentencias.

Podemos usarlo directamente como contenido o texto de alguna etiqueta:

```
- var titulo = "Título de la cabecera"
h1= titulo
```

O como valor de algún atributo:

```
- var url = "http://jade-lang.com/"
a(href=url) Web oficial de Jade 
``` 

Dará como resultado

	<a href="http://jade-lang.com/">Web oficial de Jade</a>

## Interpolación

Cada vez es más típico ver esto.  Los que hayáis trabajado con la mayoría de lenguajes seguro que en muchas ocasiones habréis construido un `string` largo con variables en plan: 

	"Texto " + variable1 + " más texto " + otraVariable

Cada vez es más típico ver la interpolación, de hecho es uno de los aspectos añadidos en **ES6** y consiste en añadir directamente el valor de las variables en el *string* y esto se consigue encerrando la variable entre `#{}`.  Ej:

```
- var title = "On Dogs: Man's Best Friend";
- var author = "enlore";
- var theGreat = "<span>escape!</span>";

h1= title
p Written with love by #{author}
p This will be safe: #{theGreat}
```

También es posible interpolar etiquetas:

```
p.
  If you take a look at this page's source #[a(target="_blank", href="https://github.com/jadejs/jade/blob/master/docs/views/reference/interpolation.jade") on GitHub],
  you'll see several places where the tag interpolation operator is
  used, like so.
```

Dará como resultado:

```html
<p>If you take a look at this page's source <a target="_blank" href="https://github.com/jadejs/jade/blob/master/docs/views/reference/interpolation.jade">on GitHub</a>,
  you'll see several places where the tag interpolation operator is
  used, like so.
</p>
```