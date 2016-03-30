Comentarios
===========

Hay 2 tipos de comentarios en Jade:
* Los típicos comentarios de HTML con `//`
* Comentarios de Jade que no aparecen en HTML `//-`

Los comentarios anteriores se pueden usar indistintamente para comentar:
* Una línea.  Si el comentario se coloca al inicio de una línea
* De bloque.  Si después del comentario hay un nivel de indentación

Ej:

```
// Comentario de línea visible
//- Comentario de línea no visible
div
  //
    p Esto es un comentario de bloque
    p Es visible en navegadores
  //-
    p Esto es un comentario de bloque
    p No es visible en navegadores
```

Su resultado sería:

```html
<!-- Comentario de línea visible-->
<div>
  <!--
  p Esto es un comentario de bloque
  p Es visible en navegadores
  -->
</div>
```