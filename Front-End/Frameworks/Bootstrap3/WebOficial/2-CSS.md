2 - CSS
=======

##Características
* **Mobile first**: El enfoque de diseño responsive es *Mobile first*.
* **Normalize**: Bootstrap incluye normalize en el css para estandarizar el visionado en los diferentes navegadores.
* **Contenedores**: Los elementos de Bootstrap tienen que estar dentro de unos contenedores que usarán `.container` para un contenedor fijo y `.container-fluid` para un contenedor del ancho completo de la página.    

##Grid system
###Introducción
* Las filas deben de estar dentro de un contenedor ya sea `.container` o `.container-fluid`.
* Las filas crean grupos horizontales de columnas.
* Una fila está compuesta por hasta un máximo de 12 columnas.
* Podemos agrupar las columnas con clases como `.col-xs-4` o `.col-md-6`.
* Cuando haya grupos que sean más de 12 columnas en 1 fila, el último grupo pasa a la siguiente fila.

###Media Queries
| Nomenclatura  | Breakpoint    | Ancho .container  |
| ------------- |:-------------:| -----------------:|
| xs            | <768px        |              100% |
| sm            | >=768px       |             750px |
| md            | >=992px       |             970px |
| lg            | >=1200px      |            1170px |

###Columnas