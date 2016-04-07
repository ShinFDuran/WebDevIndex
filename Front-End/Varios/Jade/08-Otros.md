Filtros y Mixins
================

## Filtros

Es posible añadir otros lenguajes con un formato de *Jade*, para ver el listado de los lenguajes disponibles visitar [JSTransformers](https://www.npmjs.com/browse/keyword/jstransformer).

```
:markdown
  # Markdown

  I often like including markdown documents.
script
  :coffee-script
    console.log 'This is coffee script'
```

Daría como resultado:

```html
<h1>Markdown</h1>
<p>I often like including markdown documents.</p>
<script>console.log('This is coffee script')</script>
```

## Mixins

Está muy de moda el uso de mixins en plantillas, preprocesadores u otros y es que añaden un plus de modularidad y reutilización de código y en el caso de *Jade* no iba a ser diferente. Para usar un mixin primero es necesario definirlo con la palabra `mixin`:

```
mixin menunav(nombreVar)
	mixin contenido
```

Posteriormente podemos usarlo usando ` + ` seguido del nombre del *mixin*:

	+menunav(var)

Como podéis ver es muy sencillo de usar y muy poderoso en tanto que no sólo sirve para crear bloques de código usados, sino que además nos permite generar diferentes bloques de código en función de las variables que les pasamos. Incluso podemos usar mixins dentro de otros mixins:

```
mixin menunav(menu_items)
	.menunav
		ul
			each item in menu_items
				li
					+links(item)
					if item.hijo
						ul
							each item_hijo in item.hijo
								li
									+links(item_hijo)

mixin links(item)
	- var linkatts = { 'href': item.link }
	a()&attributes(linkatts)= item.titulo
```

Al mixin podemos pasarle una variable, un objeto o un grupo de variables e incluso tenemos la opción de utilizar una cantidad de variables no definida:

```
mixin list(id, ...items)
  ul(id=id)
    each item in items
      li= item

+list('my-list', 1, 2, 3, 4)
```

**Importante**, la variable múltiple tiene que ser la última.