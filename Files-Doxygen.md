# Práctica 10. Ficheros. Documentación de programas. Doxygen.

### Objetivos
Los objetivos de esta práctica son que el alumnado:
* Desarrolle programas sencillos en C++ que utilicen ficheros, así como todas las características del lenguaje
  estudiadas

### Rúbrica de evaluacion de esta práctica
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva)
que se tendrán en cuenta a la hora de evaluar esta práctica:
* El alumnado ha de acreditar conocer los conceptos expuestos en el material de referencia de esta práctica.
* El alumnado ha de acreditar que ha realizado todos los ejercicios propuestos, así como ser capaz de desarrollar otros similares.
* Ha de acreditar que es capaz de escribir un fichero Makefile para automatizar el proceso de compilación de sus programas.
* El código que escriba ha de estar escrito de acuerdo a los estándares definidos en la Guía de Estilo de Google para C++.
* Todos los identificadores que utilice en su programa (constantes, variables, etc.) deberán ser
  siempre significativos. No utilice nunca identificadores de una única letra, tal vez con la excepción de las
  variables que utilice para iterar en un bucle.
* Antes de su ejecución, todos los programas que desarrolle, deben imprimir en pantalla un
  mensaje indicando la finalidad del programa así como la información que precisará del usuario para su correcta ejecución.

### Trabajo previo: Doxygen
Instale Doxygen en su máquina virtual de la asignatura:
```
$ sudo apt install doxygen
```


### Ejercicios 
Al realizar los siguientes ejercicios cree dentro de su repositorio de esta práctica un directorio diferente
para cada uno de los ejercicios.
Ponga a cada uno de esos directorios nombres significativos.
Haga que cada uno de sus programas conste de 3 ficheros:
* Un fichero `mi_programa.cc` (programa principal) que contendrá la función `main` e incluirá el fichero de cabecera `funciones.h`
* El fichero `funciones.h` que contendrá las declaraciones de las diferentes funciones que se utilizan en el
  programa principal para resolver el ejercicio en cuestión.
* El fichero `funciones.cc` que contendrá el código (definiciones) de las funciones declaradas en el fichero
  de cabecera.

Modifique los nombres de los ficheros que aquí se proponen para adaptarlos al ejercicio en cuestión.

La compilación de los programas correspondientes a cada ejercicio se automatizará con un fichero Makefile para
cada ejercicio.

Desarrolle cada uno de estos ejercicios de forma incremental, probando cada una de las funciones que va Ud.
desarrollando. Utilice el depurador de VSC para corregir cualquier tipo de error semántico que se produzca en
cualquiera de sus desarrollos.

1. Escriba un programa `find_first_of.cc' que dada una cadena y un carácter, determine la primera posición 
   de la cadena en la que se encuentra ese carácter, en caso de que se encuentre. 
	 Si el carácter no se encuentra, el programa imprimirá -1. 
	 Se considerará que la primera posición de la cadena (la correspondiente al primer carácter de la misma) es la cero:
```
$ ./find_first_of abracadabra r
2

$ ./find_first_of AlbertEinstein Z
-1
```

### Documentación de código. Doxigen
[Doxygen](https://en.wikipedia.org/wiki/Doxygen)
es una herramienta de código abierto generadora de documentación para escribir documentación de referencia de software. 
La documentación está escrita en el propio código fuente de los programas, y por lo tanto es relativamente 
fácil de mantener actualizada. 
Doxygen puede hacer referencias cruzadas entre la documentación y el código, de modo que el lector 
de un documento puede referirse fácilmente al código fuente.

Doxygen extrae la documentación de los comentarios de los ficheros de código fuente y 
y puede generar la salida en diferentes formatos entre los cuales están HTML, PDF LaTeX o páginas man de Unix.

En esta asignatura no se propone un uso exhaustivo de Doxygen pero sí se promueve que la
documentación de los programas desarrollados se realice en el formato reconocido por Doxygen, que se ha
convertido en un estándar de facto.

Comience por instalar Doxygen en su máquina virtual de la asignatura:
```
$ sudo apt install doxygen
```

En el [manual de Doxygen](https://www.doxygen.nl/manual/starting.html) indica cómo comenzar a trabajar con la
herramienta.
Si, ubicados en un directorio de trabajo se invoca `doxygen`:
```
doxygen -g <config-file>

```
la herramienta creará un fichero de configuración.
Si no se le pasa el nombre del fichero como parámetro, creará un fichero con nombre `Doxyfile` preconfigurado
para su uso.
En el directorio de trabajo de esta práctica se encuentra un fichero `Doxyfile` ya listo para usarse con
proyectos de C++.
Se ha incluído asimismo (directorio `fibonacci_sum`) el código fuente de un programa para ilustrar con el mismo el uso de
documentación con Doxygen.
Si revisa Ud. el fichero `Doxyfile` (es un fichero de texto) verá toda una serie de opciones que el programa permite.
Cada opción va precedida de una explicación de su finalidad y funcionamiento, de modo que puede Ud. probar a
modificar algunas de ellas si lo desea.
En [esta página](https://www.doxygen.nl/manual/config.html)
puede consultarse la finalidad y funcionamiento de cada una de las etiquetas (Tags) que se usan en el fichero
de configuración de Doxygen.

Para generar la documentación de su aplicación, colóquese en el directorio de su proyecto 
(`fibonacci_sum` en esta práctica) y ejecute:
```
doxygen Doxyfile
```
en el directorio donde se encuentre el código fuente.
Con el fichero `Doxyfile` que se suministra, la herramienta creará un subdirectorio `doc` en el que alojará
toda la documentación generada.
Con la configuración suministrada se generan dos subdirectorios dentro de `doc`: `html` y `latex`.
Si abre con un navegador el fichero `doc/html/index.html` accederá a la página principal de la documentación
generada para el programa.
Si se coloca en el directorio `doc/latex/` y ejecuta `make` el sistema "compila" el código latex y genera un
fichero `refman.pdf` que contiene igualmente la documentación generada.
Tal como se ha indicado, HTML o latex son solo dos de los formatos que permite generar Doxygen.
Tanto HTML como Latex (también Markdown) son lo que se conoce como 
[lenguajes de marcas](https://es.wikipedia.org/wiki/Lenguaje_de_marcado).
HTML es el lenguaje que se utiliza para componer los textos que se muestran en las páginas web.
[Latex](https://en.wikipedia.org/wiki/LaTeX)
es un sistema de composición de textos que cuida el formato en especial en el ámbito de la tipografía y que es
especialmente adecuado para textos de carácter científico.
No se pretende aquí que profundice Ud. en conocer HTML o Latex.

La sección 
[Documenting the code](https://www.doxygen.nl/manual/config.html)
del manual de Doxygen indica cómo comentar el código fuente de modo que los comentarios sean procesados por
Doxygen para incorporarlos a la documentación generada.

En la asignatura se propone utilizar comentarios de tipo JavaDoc para comentarios de bloque:
```
/**
 * ... text ...
 */
```
[JavaDoc](https://en.wikipedia.org/wiki/Javadoc)
es otro sistema de documentación ideado para Java y que también es muy popular.
Doxygen soporta el uso de etiquetas "al estilo Javadoc" en el código.

Los bloques de comentarios multi-línea deben comenzar con 
```
/** 
```
y finalizar con
```
*/
```
Los comentarios de una única línea deben comenzar con `///`.
Por consistencia no use las opciones 
```
/*!
```
o
```
//!
```
permitidas en Doxygen.


Así el bloque de comentarios que debe preceder a cualquier función (o método) tendrá la siguiente apariencia:
```
/**
 * Sum numbers in a vector.
 *
 * @param values Container whose values are summed.
 * @return sum of `values`, or 0.0 if `values` is empty.
 */
double sum(std::vector<double> & const values) {
  ...
}
```
En el ejemplo anterior `@param` y `@return` son etiquetas de tipo Javadoc.
En 
[Overview of supported JavaDoc style tags](http://www.time2help.com/doc/online_help/idh_java_doc_tag_support.htm)
pueden consultarse este tipo de etiquetas.

El siguiente es un ejemplo (plantilla) de comentario de bloque que debería incluirse al comienzo de todos los ficheros
(*.cc, *.h) de un proyecto de programación en el ámbito de esta asignatura:
```
/**
  * Universidad de La Laguna
  * Escuela Superior de Ingeniería y Tecnología
  * Grado en Ingeniería Informática
  * Informática Básica
	*
	* @file fibonacci_main.cc
  * @author F. de Sande fsande@ull.es
  * @date 23 Jun 2020
  * @brief El programa calcula la suma de todos los términos de valor par de la serie
	*        de Fibonacci que sean menores que un valor dado.
  *        Cada nuevo término de la serie se genera sumando los dos anteriores.
  *        Comenzando con 0 y 1, los primeros 10 términos serán: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34
  * @bug No hay bugs conocidos
	* @see https://www.cs.cmu.edu/~410/doc/doxygen.html
  */
```
Todo fichero debiera contener (etiqueta `@brief`) una breve descripción del contenido del fichero.
Si fuera necesario se incluirá a continuación una descripción más detallada.
Obviamente el comentario específico así como el nombre del fichero debieran particularizarse para cada caso
concreto.

La guía 
[Documenting C++ Code](https://developer.lsst.io/cpp/api-docs.html) 
de documentación de código del proyecto LLST es la referencia que se adoptará en la asignatura para documentar
el código de los programas que se desarrollen.

Por otra parte, estudie atentamente todo lo que se indica en el epígrafe
[Comments](https://google.github.io/styleguide/cppguide.html#Comments)
de la Guía de Estilo de Google y ponga en práctica todo lo que en ella se propone, usando el formato Doxygen
para todos los comentarios que introduzca en su código fuente.

### Referencias
* [Doxygen](https://en.wikipedia.org/wiki/Doxygen)
* [Latex](https://en.wikipedia.org/wiki/LaTeX)
* [Overview of supported JavaDoc style tags](http://www.time2help.com/doc/online_help/idh_java_doc_tag_support.htm)
* [Documenting C++ Code](https://developer.lsst.io/cpp/api-docs.html)
* [Comments](https://google.github.io/styleguide/cppguide.html#Comments)
* [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
