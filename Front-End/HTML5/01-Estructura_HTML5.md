Estructura HTML5
================

Un documento HTML está formado por varios bloques o zonas.  
Inicialmente (aunque no obligatorio) hay que indicar el tipo de documento HTML que es, para el caso de HTML5 es:

```
<!DOCTYPE html>
```

Lo siguiente es el documento html en sí, este a su vez tiene 2 partes claramente delimitadas:

	<html>
		<head></head>			<!-- Cabecera, contiene información no visible -->
		<body></body>			<!-- Cuerpo, es lo que se suele mostrar -->
	</html>

```html
<html>
	<head></head>			<!-- Cabecera, contiene información no visible -->
	<body></body>			<!-- Cuerpo, es lo que se suele mostrar -->
</html>
```

`<head>` o cabecera: Contiene información y recursos sobre la página, la única información que se suele mostrar externamente es el `<title>` en la parte superior del navegador. Etiquetas importantes del `<head>`:

	<title></title> 			-- Se usa para indicar el título de la página web
	<meta charset="utf-8"> 		-- Se usa para indicar la codificación usada (utf-8 en este caso)


`<body>` o cuerpo.  Es donde están los elementos que van a ser visualizados en el navegador.

Comentarios. Si queremos agregar un texto que no sea interpretado lo escribimos entre:

`<!-- texto -->`

Ejemplo básico de página HTML:

```
<!doctype html>
	<html lang="es">
	<head>
		<meta charset="UTF-8">
		<title>Document</title>
	</head>
	<body>
		
	</body>
</html>
```