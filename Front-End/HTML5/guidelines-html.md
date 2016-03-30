Guías de estilo HTML
====================

A continuación pongo un listado de guías, la base principal son las de *Google*, pero he añadido algunos aportes interesantes de las de *GitHub* y de *Mark Otto*:

* [Google](http://google.github.io/styleguide/htmlcssguide.xml)
* [GitHub](http://primercss.io/guidelines/)
* [Mark Otto](http://mdo.github.io/code-guide/)

###Protocolo
* Omitir la parte de protocolo `http:, https:` de la url, nos ahorra unos bytes y evita algunos problemas de *IExplorer* que muestra un mensaje cuando cambia de una conexión segura a una no segura

###Reglas de formato
* **Indentación:** Usar 2 espacios como indentación.  No usar mezclas de tabuladores y espacios.
* **Capitalización:** Usar sólo letras en minúsculas.
* **Espacios en blanco arrastrados:** O Trailing whitespaces, pueden generar problemas entre otros ya que pueden generar nodos vacíos.  