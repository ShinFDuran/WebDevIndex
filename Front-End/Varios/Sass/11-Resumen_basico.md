Resumen: Básico
===============

¿Es necesario saberlo **todo** sobre Sass? Pues no, de hecho hay personas que aunque saben maquetar con CSS y HTML no tienen un buen conocimiento en programación (no es lo más habitual, pero puede darse el caso sobre todo si su fuerte es el diseño).

A continuación pondré un resumen con las características que a mi modo de ver suponen un gran avance con un mínimo de dificultad.  En este caso, usaré la sintaxis scss para hacer el paso de css a sass lo más sencillo posible.

### Comentarios
* De línea (Sólo visible en el archivo origen)
	// Comentario
* De bloque: Visible en el archivo resultante css, pero no en la versión comprimida del css
	/* Comentario */
* De bloque: Visible hasta en el archivo css en su versión comprimida
	/*! Comentario */ 

### Variables
	$nombreVariable: valorVariable;

Donde valorVariable puede ser un texto encerrado entre comillas simples o dobles o un número (aquí es tanto válido 4 como 3.5, 16px, 2em).

Las variables podemos usarlas directamente continuando una propiedad, ya sea usándola directamente o dentro de una cadena de texto, en este caso dentro de `#{$nombreVariable}`:

```
$fuente: 16px;
$familia: 'Times';

body{
  // Ejemplo de uso de una variable como valor
  font-size: $fuente;

  // Interpolación de texto
  font-family: '#{$familia} New Roman', serif;
}
```

### Anidamiento

Es posible anidar selectores dentro de otros, como resultado se entenderá que en cada nivel de anidamiento hay un espacio entre el nuevo selector y el selector padre. Es posible cambiar ese comportamiento, de forma que entre el padre y el hijo no haya espacio (necesario para el uso de pseudo-selectores), para eso, usaremos el prefijo `&`.

Por último, no sólo podemos anidar selectores, sino también algunas propiedades que tienen una raíz común, como es el caso se font-size, font-family,...  Ej:

```
section{
  // Este anidamiento dará color gris a todos los párramos contenidos en cualquier section
  p{
    color: grey;
  }

  // Al usar & sólo las secciones con clase principal serán afectadas
  &.principal{
    // Es posible anidar algunas propiedades como font
    font:{
      family: 'Arial';
      size: 18px;
    }
    // Uso de pseudoclases cambiará el color del fondo del section con el cursor encima
    &:hover{
      background-color: red;
    }
  }
}
```

Dará como resultado:

```css
section p {
  color: grey;
}
section.principal {
  font-family: 'Arial';
  font-size: 18px;
}
section.principal:hover {
  background-color: red;
}
```

### Partials

Este es el último de los que considero básicos, con los css teníamos 2 opciones:

* Crear un único archivo css que al final según iba creciendo la página o añadiendo funcionalidades se tiende a convertir en una especie de Frankenstein donde el fin de una parte y el inicio de otra no estaba nada claro y para modificarlo se usa la función de buscar.
* Crear una serie de archivos css más modular pero con un perjuicio en el rendimiento al incrementar el número de peticiones a servidor.

Es tan sencillo el código de un archivo css, cortarlo y pegarlo en otro archivo y en su lugar poner una referencia al mismo:

	@include 'nombreArchivo'

Así de sencillo y así de potente, tenemos las ventajas de poder dividir nuestro código en zonas (header, footer,...), secciones (principal, about, contact,...), plantillas (fuentes, colores,...). Esto, en combinación con las variables es sencillamente brutal. Posteriormente, al compilarlo se creará un único archivo que será al que vincularemos la web.

**Algunas consideraciones:**

* Los archivos .scss que no sean los finales, se les añade el prefijo `_` para indicar que no son archivos finales.
* Podemos importar archivos .scss, .sass e incluso .css
* Al incluir un archivo, es necesario especificar la ruta donde está el archivo
	@include 'layout/grid'
* No es necesario ni indicar la extensión (si tiene alguna de las conocidads .scss, .sass o .css) ni añadir el prefijo `_` en el caso de los parciales

### Sass es mucho más

Este es un resumen rápido de algunas de las características de Sass de forma que sea un paso intermedio y rápido de css a Scss lo menos traumática posible y que nos facilite de una buena cantidad de recursos.

Posteriormente, cuando ya te sientas confortable será un buen momento para pasar al siguiente nivel donde las funciones, mixins y otras directivas nos proporcionan herramientas para potenciar la modularidad y reutilización de código.