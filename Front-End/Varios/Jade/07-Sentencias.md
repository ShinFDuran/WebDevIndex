Sentencias condicionales, case y blucles each y while
=====================================================

Si bien ya se vio que el código tal cual hay que precederlo por ` - ` para que Jade lo identifique como código, existen una serie de sentencias que automáticamente son interpretadas.

## Sentencia condicional if

Es el `if` que estamos acostumbrados a ver en todos los lenguajes:

```
- var user = { description: 'foo bar baz' }
- var authorised = false
#user
  if user.description
    h2 Description
    p.description= user.description
  else if authorised
    h2 Description
    p.description.
      User has no description,
      why not add one...
  else
    h1 Description
    p.description User has no description
``` 

La diferencia es que *Jade* además agrega la versión negada `unless`.

## Sentencia condicional case

Esta sentencia es la condicional multirespuesta  típica de los lenguajes de programación como es el caso de `switch` en *JavaScript*.  Le indicamos una variable y en función de su valor generará un código u otro.

Hay que tener en cuenta un detalle, si bien también se da la ejecución en cascada después de casa opción no es necesario un `break`.  Supongamos el caso:

```
- var friends = 0
case friends
  when 0
  when 1
    p you have very few friends
  default
    p you have #{friends} friends
```

Se ejecutará el mismo código para la opción 0 y 1, pero no existe la opción de que se ejecutara el código 0 y luego 
 
```
- var friends = 10
case friends
  when 0
    p you have no friends
  when 1
    p you have a friend
  default
    p you have #{friends} friends
```

En el `switch` habitual, para el caso 0 ejecutaría los 3, en el caso de **Jade** automáticamente añade un `break`. 

También es posible anidar las etiquetas como se vio antes:

```
- var friends = 1
case friends
  when 0: p you have no friends
  when 1: p you have a friend
  default: p you have #{friends} friends
```

## Each

Este es el típico `for` o `for each` de otros lenguajes.  Ejemplos:

Bucle simple:


```
ul
  each val in [1, 2, 3, 4, 5]
    li= val
```

```html
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
  <li>4</li>
  <li>5</li>
</ul>
```

Usando índices en un array

```
ul
  each val, index in ['zero', 'one', 'two']
    li= index + ': ' + val
```

```html
<ul>
  <li>0: zero</li>
  <li>1: one</li>
  <li>2: two</li>
</ul>
```

Iterando a través de los índices de un objeto

```
ul
  each val, index in {1:'one',2:'two',3:'three'}
    li= index + ': ' + val
```

```html
<ul>
  <li>1: one</li>
  <li>2: two</li>
  <li>3: three</li>
</ul>
```

## While

Poco se puede decir ya del conocido bucle `while`, así que simplemente pongo un ejemplo.

```
- var n = 0
ul
  while n < 4
    li= n++
```

```html
<ul>
  <li>0</li>
  <li>1</li>
  <li>2</li>
  <li>3</li>
</ul>
```
