Estructura básica de una página
===============================

## doctype

Aquí no debería haber mucha complicación ya que aunque se pueden generar *doctype* para versiones anteriores a fin de cuentas vamos a usar el de html.

```
  doctype html
```

Daría como resultado:

``` html
  <!DOCTYPE html>
```

## Estructura básica

Llegados a este punto, ya se ha visto el `doctype`, el sistema de etiquetas, su anidamiento, sus propiedades y el texto, así que nos debería resultar familiar el siguiente código:

```
doctype
html( lang="es" )
	head
		title Título de la página
		meta( charset='utf-8' )
		meta( http-equiv='X-UA-Compatible', content='IE=edge' )
		meta( name='viewport', content='width=device-width, initial-scale=1.0' )
		meta( name='description', content='Descripción de la página' )
		link( href='css/style.css', rel='stylesheet' )
	body
		// Contenido de la página
```

Cuyo resultado sería:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <title>Título de la página</title>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Descripción de la página">
    <link href="css/style.css" rel="stylesheet">
  </head>
  <body>
    <!-- Contenido de la página-->
  </body>
</html>
```

Con esto actualmente podríamos generar las típicas páginas html a partir de la versión **Jade**, sin embargo, ahora es cuando empieza lo bueno, lo que realmente nos hará sacarle provecho: herencia, uso de código y mixins entre otros.