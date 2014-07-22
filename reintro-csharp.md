# Una re-introducción a CSharp (Tutorial de C#)

#####Tabla de Contenidos

* [Resumen](#toc-resumen)
* [Sintaxis Básica](#toc-sintaxis)
* [Nomenclatura y Buenas Prácticas](#toc-nomenclatura)
* [Variables](#toc-variables)
* [Números](#toc-numeros)
* [Cadenas](#toc-cadenas)
* [Memoria y Recolector de Basura](#toc-memoria)
* [Operadores](#toc-operadores)
* [Otros Tipos](#toc-tipos)
* [Controles de Estructura](#toc-controles)
* [Namespaces](#toc-namespaces)
* [Clases y objetos](#toc-clases)
* [Metodos](#toc-metodos)
* [Referencia](#toc-referencia)
* [Información de Origen del Documento](#toc-info)

<a name="toc-resumen"></a>
##Resumen
CSharp es un lenguaje de programación orientado a objetos diseñado por Microsoft y que es parte de la tecnología .NET publicada en el 2000. Microsoft buscó desde su perspectiva traer una evolución del lenguaje C, por lo que si C++ es una versión mejorada (por ello el signo incremental ++), C# es una evolución, por eso la conjunción de ++ que forman un # y que en música es una nota más alta que la nota C. En el tutorial usaré C# o CSharp de manera indistinta.

C# se compila no a lenguaje de maquina como ocurre con C/C++, en lo que se compila es en un Lenguaje Intermedio (*IL* por sus siglas en ingles) que al igual que en Java requiere de un programa intermedio (Maquina Virtual o Runtime) que al momento de ejecución convierte este *IL* en lenguaje de máquina pudiendo el mismo *IL* correr en *X86* o en *ARM*, en *Windows* como en *Mac*, dejando el proceso de conversión al Runtime.

Pero con proyectos como Xamarin, C# también se puede compilar directamente en lenguaje de maquina, por lo que con este lenguaje podemos crear aplicaciones nativas para dispositivos móviles sin necesidad de aprender Objetive-C o Java.

CSharp sigue evolucionando, cada versión trae nuevas y mejores características que agilizan el desarrollo.

<a name="toc-sintaxis"></a>
##Sintaxis Básica
Las declaraciones de las instrucciones al igual que en C o cualquier derivación deben cumplir lo siguiente

* El sangrado del código no importa para el compilador, pero úsalo como buen práctica
* Se debe terminar cada declaración/linea con `;`
* Englobar lo códigos de los Namespaces, Clases, Métodos, Estructuras de Control con `{` y `}`
* Los comentarios de una misma línea se definen con `//`
* Los comentarios de más de una línea se definen con `/*` y se finalizan con `*/`

<a name="toc-nomenclatura"></a>
##Nomenclatura y Buenas Prácticas
Recomiendo las siguientes buenas prácticas al escribir código, sobre estas se siguen los ejemplos en el tutorial, pero cada quien puede seguir las que mejor le convenga, el compilador no encuentra diferencia en ello.

* Cuando se escribe código hay que comentarlo
* Usar abreviaciones comunes o fáciles de entender
* Los nombre de las variables y de los métodos sean fáciles de entender que no requieran un diccionario de datos
* Sangrar o *identar* el código con *tab* o espacios
* Para Namespace y Clases usar nomenclatura de camello iniciando con mayúscula `System.Console`
* Para métodos usar nomenclatura de camello iniciando con un verbo en minúscula que indique si es para establecer y obtener un valor `ClassName.getAge` o `ClassName.setAge`

<a name="toc-variables"></a>
##Variables
Los nombres de las variables deben ser letras en UTF-8, números y guiones bajos, pero no puede iniciar con números, no pueden usarse algunas palabras reservadas o *keywords*, las cuales pueden consultarse en [la documentación oficial](http://msdn.microsoft.com/en-us/library/x53a06bb.aspx).

La sintaxis de las variables la forma sencilla:

```c#
tipo nombre;
int A;
```

Con asignación de valor:

```c#
tipo nombre = valor;
int A = 1;
```
    
Con definición de tipo de acceso:

```c#
acceso tipo nombre = valor;
public int A = 1;
```
    
Los nombres son sensibles a mayúsculas y minúsculas por lo que todas las siguientes variables son distintas:

```c#
int Zapopan;
int ZAPOPAN;
int zapopan;
```
    
En una misma línea se pueden declarar varias variables:

```c#
int A, B, C;
int A = 1, B = 2, C = A + B;
```

***

Acceso | Tipo | Nombre | Asignacion
--- | --- | --- | ---
 | int | A | ; |
public | int | A | = 1;

***

<a name="toc-numeros"></a>
##Números

<a name="toc-cadenas"></a>
##Cadenas

<a name="toc-memoria"></a>
##Memoria y Recolector de Basura

<a name="toc-operadores"></a>
##Operadores

<a name="toc-otros-tipos"></a>
##Otros Tipos

<a name="toc-controles"></a>
##Controles de Estructura

<a name="toc-namespaces"></a>
##Namespaces

<a name="toc-clases"></a>
##Clases y objetos

<a name="toc-metodos"></a>
##Metodos

<a name="toc-referencia"></a>
##Referencia
* Programming in the Key of C#, A Primer  for Aspiring Programmers por Charles Petzold, ISBN 0-7356-1800-3
* <https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript>
* <http://msdn.microsoft.com/en-us/library/aa645597%28v=vs.71%29.aspx>
* <http://csharp.net-tutorials.com/basics/introduction/>

<a name="toc-info"></a>
## Información de Origen del Documento
* Autor: Alex Galindo ([elalecs](https://twitter.com/elalecs))
* Última Actualización: 22 de Julio de 2014
* Derechos Reservados: Alex Galindo bajo la [Licencia Creative Commons Atribución-NoComercial-CompartirIgual 4.0 Internacional.](http://creativecommons.org/licenses/by-nc-sa/4.0/)
