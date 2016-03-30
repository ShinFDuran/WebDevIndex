Etiquetas
=========

## Uso y anidamiento

Las etiquetas que hay en **Jade** son las mismas que en **HTML**. Lo que varía, entre otras cosas es que no hace falta cerrarlas.  Las etiquetas simples como `<meta>` o `<img>` se cierran solas y las que tienen una etiqueta de cierre estarán determinadas por el nivel de anidamiento.

Dicho sea de paso, tenemos 2 formas de anidar:

1 - Usando espacios o tabulaciones:

```
div
  p
    span
```

2 - Usando el elemento ` : ` en la misma línea:

```
div: p: span
```

En ambos casos, el resultado será:

```html
<div>
  <p><span></span></p>
</div>
```

## Texto

Hay 2 formas de colocar texto dentro de una etiqueta:

1. Añadiéndolo a continuación de la etiqueta:  
`p A continuación el texto dentro del párrafo`
2. Usándolo en líneas posteriores precedido del símbolo ` | `:  
```
p
  | Texto en líneas
  | diferentes al de la etiqueta
```

Aquí aclarar un detalle, el resultado *visual* será un único párrafo con un párrafo continuado ya que aunque el resultado del código HTML aparezcan en diferentes líneas, los navegadores ignoran ese salto de línea que hemos agregado nosotros.  Además, debemos agregar la indentación para indicar que ese texto forma parte de la etiqueta `<p>`.

### Atributos

Esto cambia bastante con lo que estamos acostumbrados en *HTML*, lo que sería la asignación de atributos a las etiquetas, nuevamente **Jade** nos da diferentes opciones:

#### Asignar atributos a una etiqueta
	tag(atributo="valor") Texto dentro de la etiqueta
	tag(atributo1="valor", atributo2="valor") Texto dentro de la etiqueta

#### Indentado y sustituyendo las comas por líneas
	tag(
		atributo1="valor"
		atributo2="valor"
	) Texto dentro de la etiqueta

#### Usar múltiples clases es usando un array
	tag(
		atributo1="valor"
		atributo2="valor"
		class=["clase1", "clase2",...]
	) Texto dentro de la etiqueta

#### Usando la notación de JavaScript:
	tag()&attributes({
		'id': 'idname',
		'href': 'link.html',
		'rel': 'nofollow'
		'class': ['class1', 'class2']
	}) Texto dentro de la etiqueta

#### Usando atajos para clases e ids

	div.classname Texto dentro de la clase

Generará un `<div>` con una clase *classname*.  Añadir, que también podemos omitir la etiqueta `<div>`.  Ejemplo:

	.classname.otraclassname.otraclass#idclass Texto

Generará el siguiente código:

```html 
<div id="idclass" class="classname otraclassname otraclass">Texto</div>
```

Como se puede ver, facilidades... muchas