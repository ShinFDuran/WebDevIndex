Plantillas: Inclusiones y extensiones
=====================================

## Uso de plantillas

Aquí ya empezamos a ver el potencial de Jade.  Una de las principales ventajas de **Jade** es reutilizar el código mediante el uso de plantillas, aquí podemos definir 2 formas:

* **Include**: En este caso lo que hacemos es incluir un archivo externo tal cual, tiene sus ventajas pero también sus limitaciones.
* **Extends**: Este es el sistema de plantillas propiamente dicho, nos permite reutilizar otras plantillas pero con la posibilidad de modificar más fácil el contenido.

## Includes

Es tan sencillo como escribir:

	include nombreArchivo

Decir que no hace falta incluir la extensión, por defecto se entiende que es `.jade`.  De esa forma tan sencilla podríamos modular el código de una página, sin embargo, podemos dar un paso más.

## Plantillas

Aquí tenemos una plantilla principal o padre que será la base, lo único que tenemos que hacer es definir unos puntos o anclas que usarán las plantillas que hereden para incluir información y sería:

	block nombreBloque

En las plantillas que hereden tenemos que seguir 2 pasos.

En primer lugar definimos de qué plantilla vamos a heredar, no hace falta indicar extensión:

	extends nombrePlantilla

Posteriormente lo que hacemos es definir el contenido para los bloques especificados en el padre.

	block nombreBloque
		contenido

También es posible re-utilizar información en diferentes partes de la página:

```
extends nombrePlantilla

block titulo
	| Texto título

block content
	h1
		block titulo  		
		//- Añadirá el bloque de información declarado antes
```

## Append y Prepend

Como dije anteriormente, en la plantilla principal lo que hacemos es indicar unos puntos o anclas.  No es obligatorio definir el contenido de cada bloque al extender y de hecho, el bloque original puede tener contenido y posteriormente sobreescribirlo, colocar contenido antes de la referencia con **prepend** o después de la referencia con **append**.  Mejor verlo con un ejemplo:

	block nombreBloque
		// Contenido por defecto

Ahora vemos las 3 posibilidades:

	block prepend nombreBloque
		// Agregamos contenido antes
	block nombreBloque
		// Sobreescribimos el contenido del bloque
	block append nombreBloque
		// Agregamos contenido después

Como podéis apreciar, las extensiones nos dan mucho juego. El bloque no actúa como forma de herencia, sino como identificador.  Cuando se usa `append` o `prepend`, no es necesario usar la *keyword* `block`.

