Etiquetas BODY
==============

Texto HTML
----------

Las marcas de texto en html, se emplean para el estructurado semántico del contenido
* `<p>` - párrafo
* `<br>` - Salto de línea de texto.  Sólo debe usarse cuando sea necesario para no perder su sentido semántico.
* `<h1>-<h6`> - Cabeceras o titulares, el de mayor peso es h1
* `<hgroup>` - Se utiliza para agrupar titulares sin que afecte al posicionamiento (repetición de h1)
* `<hr>` - Línea horizontal de separación

* `<abbr>` - Abreviatura
* `<acronym>` - Acrónimo.  Propiedad title para poner texto completo
* `<address>` - Define una dirección.
* `<bdo>` - Se utiliza para indicar la dirección del texto a mostrar
* `<blockquote>` - Cita textual de un texto externo.
* `<cite>` - Cita. Equivalente a blockquote.
* `<code>` - Se usa para representar código fuente.
* `<del>` - Texto borrado (tachado)
* `<dfn>` - Definición. Propiedad title para poner la definición de la palabra
* `<em>` - da énfasis al texto que encierra -- Habitualmente cursiva
* `<ins>` - Texto insertado recientemente (subrayado)
* `<kbd>` - Define un texto de teclado
* `<mark>` - Ilumina el texto marcado
* `<pre>` - Texto preformateado, los elementos en blanco se mantienen igual que en el texto original.
* `<samp>` - Define un ejemplo de código
* `<small>` - Se usa para indicar que un texto tiene que ser pequeño
* `<strong>` - Máxima importancia al texto que encierra -- Habitualmente negrita
* `<sub>` - Subíndice
* `<sup>` - Superíndice

* `<ul>` - Lista no ordenada
* `<ol>` - Lista ordenada
* `<li>` - Elemento de la lista
* `<dl>, <dt> y <dd>` - Listas de definiciones. Lista, término, definición.

Estructura y layout
-------------------

A la hora de crear un *layout* para la representación de una página, se suelen agrupar en bloques, existen 2 tipos de bloques, los que tienen un significado semántico y los que no (`div` y `span`). Estos bloques son:

* `<header>` - Se utiliza para establecer la cabecera de la página (aunque también se usa para headers de articles)
* `<nav>` - Es el menú de navegación, sólo debe haber uno por página.
* `<section>` - Sección del documento
* `<article>` - Bloque que define una unidad de información
* `<aside>` - Contenido tangencial al principal
* `<footer>` - Es el pie de página o de un artículo
* `<div>` - No tiene significado semántico.  Agrupa en bloques
* `<span>` - No tiene significado semántico.  Agrupa en línea

¿Cómo elegir entre article, section y div?
1. Si todo el contenido tendría sentido usarlo en un lector de feed usar `<article>`.
2. Si no es así, pero el contenido está relacionado, usar `<section>`.
3. Si no hay relación semántica del contenido usar `<div>`.

Multimedia
----------

* `<audio>` - Define el contenido de sonido
* `<canvas>` - Nos permite dibujar gráficos directamente en esa zona
* `<embed>` - Representa la integración de una aplicación externa o plugin
* `<figure>` - Define un grupo de contenido multimedia
	* `<img>` - Define una imagen
	* `<figcaption>` - Define el texto que acompaña a la imagen
* `<video>` - Define el contenido de un vídeo

Tanto en audio como en vídeo hay que tener en cuenta que según el navegador el formato será distinto. Ej:

```html
	<audio id="audio1" controls>							<!-- Controls mostrará la barra de duración -->
		<source src="media/song.m4a" type="audio/x-aac" />
		<source src="media/song.mp3" type="audio/mpeg" />	<!-- Chrome		-->
		<source src="media/song.ogg" type="audio/ogg" />	<!-- Firefox	-->
		<p> Tu navegador no soporta HTML5 audio</p>
	</audio>
```

Tablas
------

* `<table>` - Define una tabla
	* `<caption>` - Define el texto superior de una tabla. Primer elto antes que ninguna fila
	* `<tr>` - Fila en una tabla
	* `<thead>` - Cabecera de la tabla.  Aquí las celdas son `<th>`
		* `<th>` - Celda que conforma la cabecera de una tabla
	* `<tfoot>` - Pie de la tabla
	* `<tbody>` - Cuerpo de la tabla
	* `<td>` - Celda de una tabla (para tfoot y tbody)
	* `<colgroup>` - Define un grupo de columnas en una tabla
		* `<col>` - Define los atributos de la columna en una tabla

**Notas:**

* `<thead>` se mostrará al principio, luego `<tbody>` y finalmente `<tfoot>` aunque en el html estén en otro orden.
* `<th>` se usa para `<thead>` y `<td>` para `<tfoot>` y `<tbody>`, pueden contener varias filas (no son sustitutos de `<tr>`)
* `<colgroup>` se usa para definir un estilo dentro de una tabla, no sustituye a otros elementos, es una ayuda adicional. Ej en una tabla de 2 columnas.

```html
	<table>
		<colgroup>
			<col class="col1"> <!-- Representa la primera columna de la tabla -->
			<col class="col2"> <!-- Representa la segunda columna de la tabla -->
		</colgroup>
		<thead> <!-- ... --> </thead>
		<tbody> <!-- ... --> </tbody>
		<!-- ... -->
	</table>
```

Si usamos el atributo span podemos aplicarlo a más columnas: `<col span="2" class="col2">`

Formularios
-----------

`<form>` - Formulario
	`<input>`	- Campo para introducir datos.  Tiene muchas opciones
	`<label>` - Línea de texto.
	`<textarea>` - Campo para introducir datos de un área
	`<select>` - Lista seleccionable
		`<optgroup>` - Sirve para agrupar opciones en diferentes categorías
		`<option>` - Opción de una lista
	`<datalist>` - Listado que aparece en un inputo como un autocompletar (utiliza options)
`<output>` - Muestra valores obtenidos a partir de inputs

`<input type="tipo" name="nombre" value="valor"...>` Tiene una enorme cantidad de opciones
* text: Texto (valor por defecto)
* password: Texto oculto con *
* radio: Radio Button
* checkbox: Checkbox
* submit: Botón de envío
* hidden: Genera una varable oculta

Los siguientes son experimentales.  Están en Chrome pero no en Firefox (son sólo tipo text)
* date: Fecha.  Podemos indicarle un patrón, en Chrome aparece calendario, en firefox no
* color: 
* email:
* number:
* range: 
* search: Igual que de tipo texto, pero con aspecto de buscador
* url:

`<select>`: Menú desplegable de múltiples opciones
```html
	<option value="valor">Texto a mostrar en pantalla</option>
```

Otros
-----

* `<button>` - Agrega un botón
* `<iframe>` - Agrega una subventana inline
* `<meter>` - Barra de progreso y tiene varios atributos
	* value 			// Valor actual con respecto a min y max.  Si no ponemos min y max 0.6 sería un 60%
	* min				// Valor mínimo
	* max				// Valor máximo
* `<progress>` - Similar al anterior.  Hay que añadir javascript para irlo actualizándolo