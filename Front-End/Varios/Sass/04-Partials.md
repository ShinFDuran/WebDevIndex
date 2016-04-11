Partials
========

A mi modo de ver, si *Sass* y otros preprocesadores CSS sólo tuvieran variables, anidamiento y los parciales o *partials* ya de por si serían enormemente útiles sin añadir casi complejidad.

Uno de los mayores problemas que podemos encontrarnos con CSS es que por motivos de *performance* es recomendable tener un único archivo, si la web es mínimamente compleja puede dar lugar a un archivo .css enorme y en el que habrá que echar mano del buscador cada vez que queramos encontrar algo.  Esto es tremendamente engorroso e improductivo.

Los parciales nos permiten dividir y modularizar nuestro código.  Lo primero que hay que tener muy claro es que hay 2 entornos, el de desarrollo donde tendremos nuestro código estructurado y separado en la cantidad de archivos que sean necesarios y el de producción, minimizando la cantidad de archivos y apurando al máximo los bytes consumidos.

## Directiva @include

Esta directiva se utiliza en varios casos, en esta página voy a centrarme en su uso en lo que a *partials* se refiere, supongamos que tenemos un archivo `_variables.sass`, podremos incluirlo usando:

	@include "nombreArchivo"
	@include "nombreArchivo.sass"
	@include "_nombreArchivo.sass"

Es decir, por convención cuando un archivo es un partial se le agrega el prefijo `_`, y a la hora de usarlo no es necesario indicarlo, ni tampoco la extensión.

A groso modo, lo que hacemos es el contenido de ese archivo pegarlo en el archivo que lo incluye. Aquí otro aspecto a tener en cuenta, es cómo se reflejará al ser compilado:

* Si son variables no agrega contenido como tal, pero modificará el contenido de aquellos que usen esas variables.
* Si es una librería de mixins, sólo se mostrarán aquellos que sean usados.
* Si son estilos definidos se mostrarán tal cual.
 
Es decir, esta modularidad nos permite por un lado separar nuestros estilos por páginas, secciones u otros para tener nuestro código organizado, pero también tener unos archivos de configuración y librerías de mixins o funciones (ya lo explicaré posteriormente) que sólo generarán código si las utilizamos.