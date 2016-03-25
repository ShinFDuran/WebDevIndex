Etiquetas HEAD
==============

* `<title>` - Se utiliza para asignar un título a la página.
* `<style>` - Se utiliza para añadir un estilo css dentro de la misma página.
* `<script>` - Se utiliza para embeber scripts ya sea directamente o mediante un archivo.
```html
	<script src="javascript.js"></script>
	<script>Código Script</script>
```
* `<noscript>` - Define una sección que se ejecuta si no se pueden ejecutar scripts (están desactivados en el navegador).
* `<link>` - Se utiliza para asociar la página a un archivo externo.
```html
	<link href="style.css" rel="stylesheet" type="text/css">
```
* `<base>` - Se utiliza para indicar una href base para las href relativas usadas en la página
```html
	<base href="http://www.yourdomain.com/">
	<base target="_blank" href="http://www.yourdomain.com/">
```
* `<meta>` - Representa otra información que no se puede obtener a partir de las etiquetas anteriores.
```html
	<meta charset="utf-8">
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
	<meta http-equiv="refresh" content="3; url=http://bw.org" />	
	<!-- Espera 3 segundos y redirecciona a la nueva página -->
```