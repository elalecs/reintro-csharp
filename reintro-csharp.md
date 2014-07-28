# Una re-introducción a CSharp (Tutorial de C#)

#####Tabla de Contenidos

* [Introducción](#toc-intro)
* [Resumen](#toc-resumen)
* [Sintaxis Básica](#toc-sintaxis)
* [Nomenclatura y Buenas Prácticas](#toc-nomenclatura)
* [Hola Mundo y Consola](#toc-hola)
* [Variables](#toc-variables)
* [Consonantes](#toc-consonantes)
* [Números Enteros](#toc-enteros)
* [Números Flotantes](#toc-flotantes)
* [Operadores](#toc-operadores)
* [Cadenas](#toc-cadenas)
* [Conversiones](#toc-conversiones)
* [Memoria y Recolector de Basura](#toc-memoria)
* [Otros Tipos](#toc-otros-tipos)
* [Controles de Estructura](#toc-controles)
* [Namespaces](#toc-namespaces)
* [Clases y objetos](#toc-clases)
* [Metodos](#toc-metodos)
* [Referencia](#toc-referencia)
* [Información de Origen del Documento](#toc-info)


<a name="toc-intro"></a>
##Introducción
En este caso hablamos de *CSharp* y el objetivo es hablar sobre el lenguaje, no sobre los frameworks, de hecho el código ejemplo en este documento está probado en *Xamarin Studio* usando *Mono* corriendo en una Mac. Pero al hablar del lenguaje se puede aplicar para cualquiera de los dos frameworks para crear cualquier tipo de aplicaciones, si el tiempo lo permite después de este tutorial sigue un de desarrollo de aplicaciones para Mac y otro de aplicaciones móviles con *Xamarin* y con *Cordova*. Al final deberá quedar un libro de desarrollo de aplicaciones multi plataforma usando *CSharp* y *Mono*.

Este tutorial está orientado para personas con conocimientos de programación en cualquier lenguaje, no voy a entrar en detalles como por ejemplo que es una variable.


<a name="toc-resumen"></a>
##Resumen
CSharp es un lenguaje de programación orientado a objetos diseñado por Microsoft y que es parte de la tecnología .NET publicada en el 2000. Microsoft buscó desde su perspectiva traer una evolución del lenguaje C, por lo que si C++ es una versión mejorada (por ello el signo incremental ++), C# es una evolución, por eso la conjunción de ++ que forman un # y que en música es una nota más alta que la nota C. En el tutorial usaré C# o CSharp de manera indistinta.

C# se compila no a lenguaje de maquina como ocurre con C/C++, en lo que se compila es en un Lenguaje Intermedio (*IL* por sus siglas en ingles) que al igual que en Java requiere de un programa intermedio (Maquina Virtual o Runtime) que al momento de ejecución convierte este *IL* en lenguaje de máquina pudiendo el mismo *IL* correr en *X86* o en *ARM*, en *Windows* como en *Mac*, dejando el proceso de conversión al Runtime.

Pero con proyectos como Xamarin, C# también se puede compilar directamente en lenguaje de maquina, por lo que con este lenguaje podemos crear aplicaciones nativas para dispositivos móviles sin necesidad de aprender Objetive-C o Java.

CSharp sigue evolucionando, cada versión trae nuevas y mejores características que agilizan el desarrollo.


<a name="toc-sintaxis"></a>
##Sintaxis Básica
Las declaraciones de las instrucciones al igual que en C o cualquier derivación deben cumplir lo siguiente

* El sangrado (*indent*) del código no importa para el compilador, pero úsalo como buen práctica
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
* Sangrar (*indent*) el código con *tab* o espacios
* Para Namespace y Clases usar nomenclatura de camello iniciando con mayúscula `System.Console`
* Para métodos usar nomenclatura de camello iniciando con un verbo en minúscula que indique si es para establecer o obtener un valor `ClassName.getAge` o `ClassName.setAge`


<a name="toc-hola"></a>
##Hola Mundo y Consola
Como todo inicio en un lenguaje saludemos al mundo, el siguiente es un código completamente funcional, lo que nos importa es la línea donde se encuentra `Console.Write` que son la clase y método que nos permite escribir algo en la consola del sistema:

```c#
using System;

class Hola {
	static void Main() {
		Console.Write("Hola");
		Console.WriteLine("Mundo");
	} 
} 
```

La consola también sirve para requerir valores usando `Console.ReadLine()`

```c#
using System;

class Hola {
	static void Main() {
		Console.WriteLine("¿De que año nos visitas?:");
		string año = Console.ReadLine();
		Console.WriteLine("Nos visitas del año " + año);
	} 
} 
```


<a name="toc-variables"></a>
##Variables
Las variables sirven para almacenar datos de distintos tipos, se declaran antes de usarse. El nombre o *identificador* debe estar compuesto de letras unicode, números y guiones bajos, pero no puede iniciar con números, no pueden usarse algunas palabras reservadas o *keywords*, las cuales pueden consultarse en [la documentación oficial](http://msdn.microsoft.com/en-us/library/x53a06bb.aspx).

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


<a name="toc-consonantes"></a>
##Consonantes
Las consonantes se declaran casi igual que una variable, la regla de los nombres es igual, también se debe especificar que tipo de dato almacenan, la diferencia es que al inicio llevan la palabra reservada o *keyword* `cons`. Por la misma naturaleza de ser una constante se debe establecer su valor en el momento en que se define.

```c#
cons int A = 15;
```

Como buen práctica se recomienda establecer su nombre todas en mayúsculas para saber que su valor es inmutable a lo largo del código.


<a name="toc-enteros"></a>
##Números Enteros
Además de las *keywords* reservadas en el lenguaje también tenemos *literales* en este caso todos los números son literales, por lo que `1` realmente es la representación del valor binario `0000-0000-0000-0000-0000-0000-0000-0001` en 32 bits.

Existen dos formas de declarar una variable numérica, una es con el alias que es la más común y la otra es usando su clase.

```c#
int A = 1;
System.Int32 A = 1;
```

Solo con los tipos numéricos se puede hacer una conversión simple, es muy útil por ejemplo para almacenar en una variable el módulo de una división de enteros.

A continuación una tabla con los distintos valores numéricos existentes en C#:

Alias | Clase | Nombre | Mínimo | Máximo
----- | ----- | ------ | ------
sbyte | System.Sbyte | Signed Byte o Byte con signo | -128 | 127
short | System.Int16 | Short Int o Entero Corto | -32,768 | 32,767
int | System.Int32 | Integer o Entero | -2,147,483,648 | 2,147,483,647
long | System.Int64 | Longer o Largo | -9,223,372,036,854,775,808 | 9,223,372,036,854,775,808
byte | System.Byte | Byte | 0 | 255
ushort | System.UInt16 | Unsigned Short o Corto sin signo | 0 | 65,535
uint | System.UInt32 | Unsigned Integer o Entero sin signo | 0 | 4,294,483,647
ulong | System.UInt64 | Unsigned Longer o Largo sin signo | 0 | 18,446,744,073,709,551,615

El valor `0` también se debe almacenar, por eso por ejemplo el tipo de dato `sbyte` el valor mínimo es `-128` y el máximo `127` por que solo se dispone de 8 bits o 255 posibles valores a almacenar.

Un tipo de dato no puede almacenar un valor superior al mismo, si se suma un valor superior se reinicia el conteo:

```c#
byte B = 255;
B += 55; // B no tiene 310, sino 54
```

<a name="toc-flotantes"></a>
##Números Flotantes


<a name="toc-operadores"></a>
##Operadores

Operador | Acción | Ejemplo
---------|--------|--------
 `=` | Asignación | `A = 6`
 `+` | Suma, Concatena o marca como positivo | `A + B; +1; "Edad:" + 30;`
 `-` | Resta, marca como negativo | `A - B; -1;`
 `--` | Decrementa | `--A; A--;`
 `++` | Incrementa | `++A; A++;`
 `*` | Multiplica | `4 * 8; A * B;`
 `/` | Divide | `32 / 6; A / B;`
 `%` | Módulo o residuo de división | `13 / 6`
 `+=` | Suma y asigna | `A += 10;`
 `-=` | Resta y asigna | `A -= 10;`
 `*=` | Multiplica y asigna | `A *= 10;`
 `/=` | Divide y asigna | `A /= 10;`
 
Los operadores que realizan un incremento o decremento de un valor tienen una variación en su uso dependiendo su posición.

Cuando se usa al lado izquierdo del valor a modificar, la modificación se hace antes de que el valor se asigne al contexto.

```c#
A = 1;
B = --A; // El valor de B es 0
```

Si el operador se encuentra del lado derecho la modificación se hace posterior a la asignación, por lo que el contexto se queda con el valor inicial.

```c#
A = 1;
B = A++;
C = B * 10; // El valor es 10
D = A * 10; // El valor es 20
```

En una misma línea se pude hacer una operación aritmética y asignar el valor a la variable.

```c#
A = 10;
A += 10; // El valor de A es 20
A -= 10; // El valor de A es 10
A *= 10; // El valor de A es 100
A /= 10; // El valor de A es 10
```


<a name="toc-cadenas"></a>
##Cadenas
Las cadenas es un tipo de dato para almacenar un conjunto de caracteres Unicode. Todas son una instancia de la clase `System.String` y su alias es `string`. El valor a almacenar puede ser desde una cadena vacía hasta el tamaño que se desee.

El contenido de las cadenas se engloban por `"` al inicio y al final, no pueden contener saltos de línea así como tampoco el carácter `"`, para ello se deben usar secuencias de escape.

Secuencia de Escape | Secuencia en Unicode | Elemento a escapar
--------------------|-------------------------|---------------------
`\0` | `\u0000` | `Null`
`\a` | `\u0007` | `Campana`
`\b` | `\u0008` | `Backspace`
`\t` | `\u0009` | `Tab`
`\n` | `\u000A` | `Salto de Línea`
`\v` | `\u000B` | `Tab vertical`
`\f` | `\u000C` | `Avance de página`
`\r` | `\u000D` | `Retorno de cursor`
`\"` | `\u0022` | `Comillas dobles`
`\'` | `\u0027` | `Comillas simples`
`\\` | `\u005C` | `Diagonal invertida`

Dentro del ámbito de las cadenas el operador `+` sirve para concatenarlas. También se puede usar en conjunto a `+=`;

```c#
string miCadena = "Los pingüinos son aves que no viven en los árboles";
System.String saludo = "Hola terrícola";

Console.WriteLine(saludo + ", sabías que:\n" + miCadena);
```

También se pueden declarar las cadenas anteponiendo un `@` antes de las `"`, de esta forma las diagonales invertidas no se interpretan como una secuencia de escape y para ingresar `"` debemos indicarles de manera doble `""""`.

```c#
string miCadena = "Los pingüinos son aves que no viven en los árboles";
System.String saludo = "Hola terrícola";
string cadenaVerbatim = saludo + ", sabías que: """ + miCadena + """";

Console.WriteLine(cadenaVerbatim);
```

<a name="toc-conversiones"></a>
##Conversiones
Cadenas y Números se pueden convertir entre si, de forma automática cuando se concatenan cadenas y números el compilador convierte estos últimos en cadena, eso se hace usando el operador `+`.

```c#
string felicidad = 40 + 2 + " es el número de la felicidad";
string no = "El número de la felicidad no es " + 40 + 2;
```

La conversión también se puede hacer manual, todos los objetos cuentan con el método `toString` para pasarlos a cadena.

```c#
int año = 2014;
string saludo = "Saludos desde el año " + año.toString();
```

Los números también pueden convertirse desde cadena, se respeta su signo y es útil cuando se trabaja con datos que ingresa el usuario desde una consola, una interface y/o un formulario.

Para tal acción las clases de los tipos numéricos cuentan con un método estático llamado `Parse` y que reciben por argumento una cadena y la clase cadena cuenta con métodos para cada tipo numérico.

```c#
string número = " -55 ";
int valor = número.ToInt();
int igual = Int32.Parse(número);
```


<a name="toc-memoria"></a>
##Memoria y Recolector de Basura
Los valores numéricos al almacenarse en variables que tienen un largo fijo en su tipo de dato, al declararse se bloquea el total de bits definido. Es por ello que una variable numérica no puede contener un número mayor o inferior al que define su tipo.

En el caso de las cadenas se hace dos bloqueos en memoria, el primero solo es para almacenar la referencia de la ubicación en memoria del segundo bloque que cambia su tamaño de forma dinámica dependiendo la longitud de la cadena.

Cuando una aplicación se ejecuta cada cierto tiempo o cada ciertos eventos el *Runtime* acciona su recolector de basura o *Garbage Collector* el cual su función primaria es liberar memoria de datos que ya no se utilicen, por ejemplo cada vez que una cadena cambia de tamaño sobre todo de un mayor tamaño a un menor el GC libera la memoria que previamente se utilizo, también se acciona cuando una variable pasa a `Null`.


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
* Última Actualización: 28 de Julio de 2014
* Derechos Reservados: Alex Galindo bajo la [Licencia Creative Commons Atribución-NoComercial-CompartirIgual 4.0 Internacional.](http://creativecommons.org/licenses/by-nc-sa/4.0/)
