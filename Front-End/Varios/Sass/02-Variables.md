Comentarios, variables e interpolación
======================================

## Comentarios

En *Sass* hay 3 tipos de comentarios:

**De línea**: Sólo visibles en el archivo origen

	// Comentario

**De bloque**: Visible en el archivo resultante css, pero no en la versión comprimida del css

	/* Comentario */

**De bloque**: Visible hasta en el archivo css en su versión comprimida

	/*! Comentario */ 

## Variables

Definir una variable es muy sencillo, tan sólo hay que tener en cuenta que debe ir precedido por el símbolo `$` y luego indicarle el valor tras `:`.  Ejemplo:

	$nombreVariable: valorVariable

## Tipos de datos

Aunque tendamos a usarlos sin mas, hay que tener claro que Sass usa seis tipos de datos:

* Números: Aquí inclimos tanto los simples somo son 3 o 3.5 como los *"copuestos"* como 16px. Sobre ellos se pueden utilizar operaciones matemáticas (16px * 1.5)
* Cadenas de texto o stings: Las definimos sin comillas o entre comillas simples o dobles cuando es una única palabra o con comillas cuando son varias
* Colores: Aquí pueden ser con palabras referidas al color, código hexadecimal o rgba (red, #FF0000, rgba(255, 0, 0, 0.9))
* Valores booleanos: true o false. Muy útiles con ciertas directivas
* Valores nulos
* Listas de valores: Los diferentes valores estarán separados por espacios en blanco o comas (10px 1px solid black)
* Mapas o pares de valores: Compuestos por una clave y un valor separados por : 

## Interpolación -> Variables o expresiones

En *Sass* podemos usar variables mediante interpolación, además podemos usarlas tanto como un valor, como parte de una expresión.  Además, Sass se comportará de forma diferente en función del tipo de variable que usemos, ya sean `px`, `em` u otras unidades.  Es decir, tendrá un comportamiento *"inteligente"*.

El siguiente código *Sass*:

```
$fuente: 16px
$familia: 'Times'

body
  // Ejemplo de uso de una variable como valor
  font-size: $fuente
  // Interpolación de texto
  font-family: '#{$familia} New Roman', serif

h1
  // Interpolación usando la operación de multiplicar
  font-size: #{$fuente * 2}

h2
  // Sass se comportará de una forma u otra según la unidad que usemos
  font-size: #{$fuente + 8px}
```

Generará el siguiente código css:

```css
body {
  font-size: 16px;
  font-family: Arial, sans-serif;
}

h1 {
  font-size: 32px;
}

h2 {
  font-size: 24px;
}
```