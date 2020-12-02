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


### Referencias
* [git - the simple guide](https://rogerdudler.github.io/git-guide/)
* [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
