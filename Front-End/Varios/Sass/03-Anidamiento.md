Anidamiento
===========

Antes de entrar en detalle en lo que es el anidamiento de *Sass* es bueno remarcar el comportamiento de *CSS* y cómo define los estilos ya que no existe un sistema de anidamiento y lo que tenemos son pares:  

```css
elemento {  
	propiedades  
}
```

Aclarar que la definición de los elementos puede ser la siguiente en función de si hay una coma, un espacio o están juntos:

- **Elemento simple**: h1
- **Elemento específico**: h1.clase#id
- **Diferentes elementos sin relación**: h1, .clase
- **Elementos con hijos** (anidados en cualquier nivel): section p span
- **Descendiente directo**: h1 > .clase

En *CSS* es difícil distinguir las relaciones que hay de padres e hijos de los elementos, sin embargo, *Sass* nos permite un anidamiento que lo deja bastante claro.

Por defecto, cuando anidamos en *Sass* lo que estamos haciendo es separar esos elementos por un espacio, es decir, indicando que el elemento anidado es un hijo, pero sin especificar el nivel.

Sin embargo, podemos usar el operador `&` para indicar un elemento específico, es decir, que no existe espacio entre los elementos, muy útil para usar las pseudo-clases.

E incluso tenemos otra opción, y es que podemos utilizarlo en propiedades que tengan cierta relación, como es el caso de las diferentes propiedades de `font`.  Ejemplo:

```
section
  // Este anidamiento dará color gris a todos los párramos contenidos en cualquier section
  p
    color: grey
  // Al usar & sólo las secciones con clase principal serán afectadas
  &.principal
    // Es posible anidar algunas propiedades como font
    font:
      family: 'Arial'
      size: 18px
    // Uso de pseudoclases cambiará el color del fondo del section con el cursor encima
    &:hover
      background-color: red
```

Dará como resultado el siguiente *CSS*:

```css
section p {
  color: gray;
}
section.principal {
  font-family: "Arial";
  font-size: 18px;
}
section.principal:hover {
  background-color: red;
}
```