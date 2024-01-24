---
tags: [Import-8d0a]
title: Manual C
created: '2024-01-24T08:28:52.548Z'
modified: '2024-01-24T08:41:25.275Z'
---

# Manual C#

## ¿Que es C#?

C# es un lenguaje de programacion creado por Microsoft orientado a objetos que utiliza .NET Framework.
Es de la familia de C. Es parecido a C++ y a JAVA.

La primera version fue lanzada en 2002. La ultima es la 12, lanzada en noviembre de 2023.


## Instalar C# IDE en Windows

Lo primero es instalar .NET. https://visualstudio.microsoft.com/es/vs/community/

![imagen](.\imagen1.png)

Luego creamos proyecto

![imagen](.\imagen2.png)

Instalamos mas herramietas y caracteristicas.

![imagen](.\imagen3.png)

Instalamos desarrollo de escritorio .NET

![imagen](.\imagen4.png)

En crear proyecto elegimos Aplicacion de consola

![imagen](.\imagen5.png)

Le damos a continuar y ya lo tenemos

![imagen](.\imagen6.png)

## Instalar C# en Linux

Descargar el script con wget:

```
wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
```

Darle permiso de ejecucion el script:

```
chmod +x ./dotnet-install.sh
```

Ejecutamos con el parametro --version latest para instalar la ultima version:

```
./dotnet-install.sh --version latest
```

Ponemos las variables de entorno:

```
export DOTNET_ROOT=$HOME/.dotnet
```

```
export PATH=$PATH:$DOTNET_ROOT:$DOTNET_ROOT/tools
```

## Creacion de Hola mundo

Escribir en el terminal este comando:

```
dotnet new console --framework net6.0 --use-program-main
```

Crear archivo Program.cs y poner este codigo:

```
namespace HelloWorld; 

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Hello, World!");
    }
}
```

Escribe `dotnet run` en la consola para ejecutarlo:

```
dotnet run                                              
Hello, World!
```

### Explicacion del codigo

Linea 1: `using System` significa que podemos usar clases del namespace System.

Linea 2: Linea en blanco. C# ignora las ignora.

Linea 3: `namespace` se usa para organizar el codigo. 

Linea 4: Las llaves `{}` marcan el inicio y el fin del bloque de codigo.

Linea 5: `class` es un contenedor de datos y métodos, que aporta funcionalidad al programa. Cada línea de código que se ejecuta en C# debe estar dentro de una clase. En el ejemplo, llamamos a la clase `Program`.

Linea 7: Otra cosa que siempre aparece en un programa C# es el método `Main`. Se ejecutará cualquier código dentro de las llaves `{}`.

Linea 9: `Console` es una clase del espacio de nombres `System`, que tiene un método `WriteLine()` que se utiliza para imprimir texto. En el ejemplo, aparece "¡Hello World!".

## Salidas

Para generar valores o imprimir texto en C#, puede utilizar el método `WriteLine()`:

```
Console.WriteLine("Hello World!");
```

Puede agregar tantos métodos `WriteLine()` como quieras. Ten en cuenta que aparecera una nueva línea para cada método:

```
Console.WriteLine("Hello World!");
Console.WriteLine("I am Learning C#");
Console.WriteLine("It is awesome!");
```

También puedes generar números y realizar cálculos matemáticos:

```
Console.WriteLine(3 + 3);
```

### El metodo Write

También existe un método `Write()`, que es similar a `WriteLine()`.

La única diferencia es que no inserta una nueva línea al final de la salida:

```
Console.Write("Hello World! ");
Console.Write("I will print on the same line.");
```

## Comentarios

Los comentarios se pueden utilizar para explicar el código C# y hacerlo más legible. También se puede utilizar para evitar la ejecución al probar código alternativo.

### Comentarios de una linea

Los comentarios de una linea comienzan con dos barras diagonales `//`.

C# ignora cualquier texto entre `//` y el final de la línea (no se ejecutará):

```
// This is a comment
Console.WriteLine("Hello World!");
```

Este ejemplo utiliza un comentario de una linea al final de una linea de código:

```
Console.WriteLine("Hello World!");  // This is a comment
```

## Comentarios de varias líneas

Los comentarios de varias líneas comienzan con `/*`y terminan con `*/`

C# ignorará cualquier texto entre `/*` y `*/`

Este ejemplo utiliza un comentario de varias líneas para explicar el código:

```
/* The code below will print the words Hello World
to the screen, and it is amazing */
Console.WriteLine("Hello World!");
```

## Variables

Las variables son contenedores para almacenar valores de datos.

En C#, existen diferentes tipos de variables, por ejemplo:

- `int`- almacena números enteros, sin decimales, como 123 o -123

- `double`- almacena números de coma flotante, con decimales, como 19,99 o -19,99

- `char`- almacena caracteres individuales, como 'a' o 'B'. Los valores de caracteres están entre comillas simples.

- `string`- almacena texto, como "Hola mundo". Los valores de cadena están entre comillas dobles.

- `bool`- almacena valores con dos estados: verdadero o falso

### Declaración de variables

Para crear una variable, debe especificar el tipo y asignarle un valor:

```
type variableName = value;
```

Donde `type` es un tipo de C# (como `int` o `string`) y `variableName` es el nombre de la variable (como x o nombre ). El signo igual se utiliza para asignar valores a la variable.

Para crear una variable que debería almacenar texto: Creamos una variable llamada `name` de tipo `string` y le asignamos el valor "John":

```
string name = "John";
Console.WriteLine(name);
```

Para crear una variable que debería almacenar un número: Creamos una variable llamada `myNum` de tipo `int` y le asignamos el valor 15 :

```
int myNum = 15;
Console.WriteLine(myNum);
```

También puedes declarar una variable sin asignar el valor y asignar el valor más tarde:

```
int myNum;
myNum = 15;
Console.WriteLine(myNum);
```

Ten en cuenta que si asignamos un nuevo valor a una variable existente, sobrescribirá el valor anterior:

```
int myNum = 15;
myNum = 20; // myNum is now 20
Console.WriteLine(myNum);
```

#### Otros tipos

```
int myNum = 5;
double myDoubleNum = 5.99D;
char myLetter = 'D';
bool myBool = true;
string myText = "Hello";
```

## Constantes

Si no quieres que se sobrescriban los valores existentes, puede agregar la palabra clave `const` delante del tipo de variable.

Esto declarará la variable como "constante", lo que significa que no se puede cambiar y es de solo lectura:

```
const int myNum = 15;
myNum = 20; // error
```

La palabra clave `const` es útil cuando quieres que una variable almacene siempre el mismo valor, para no estropear el código. Un ejemplo que a menudo se hace referencia como constante es PI (3,14159...).

Nota: No se puede declarar una variable constante sin asignar el valor. Si lo haces, se producirá un error: un campo constante requiere que se proporcione un valor .

## Variables de visualización

### Mostrar variables

El método `WriteLine()` se utiliza a menudo para mostrar valores de variables en la ventana de la consola.

Para combinar texto y una variable, use el `+` carácter:

```
string name = "John";
Console.WriteLine("Hello " + name);
```

También puedes usar el carácter `+` para agregar una variable a otra variable:

```
string firstName = "John ";
string lastName = "Doe";
string fullName = firstName + lastName;
Console.WriteLine(fullName);
```

Para valores numéricos, el carácter `+` funciona como un operador matemático:

```
int x = 5;
int y = 6;
Console.WriteLine(x + y); // Print the value of x + y
```

## Múltiples variables

### Declarar muchas variables

Para declarar más de una variable del mismo tipo , utilice una lista separada por comas:

```
int x = 5, y = 6, z = 50;
Console.WriteLine(x + y + z);
```

También puedes asignar el mismo valor a varias variables en una línea:

```
int x, y, z;
x = y = z = 50;
Console.WriteLine(x + y + z);
```

## Identificadores

Todas las variables de C# deben identificarse con nombres únicos .

Estos nombres únicos se denominan identificadores .

Los identificadores pueden ser nombres cortos (como x o y) o nombres más descriptivos (age, sum, totalVolume).

**Nota**: Se recomienda utilizar nombres descriptivos para crear código comprensible y mantenible:

```
// Bien
int minutesPerHour = 60;

// OK, pero no es facil de entender
int m = 60;
```

Las reglas generales para nombrar variables son:

- Los nombres pueden contener letras, dígitos y el carácter de subrayado

- Los nombres deben comenzar con una letra o un guión bajo.

- Los nombres deben comenzar con una letra minúscula y no pueden contener espacios en blanco.

- Los nombres distinguen entre mayúsculas y minúsculas ("myVar" y "myvar" son variables diferentes).

- Las palabras reservadas (como palabras clave de C#, como `int` o `double`) no se pueden utilizar como nombres.

## Tipos de datos

Como se explica en el capítulo de variables, una variable en C# debe ser un tipo de datos específico:

```
int myNum = 5;               // Integer
double myDoubleNum = 5.99D;  // Floating point number
char myLetter = 'D';         // Character
bool myBool = true;          // Boolean
string myText = "Hello";     // String
```

Un tipo de datos especifica el tamaño y el tipo de valores de variables.

Es importante utilizar el tipo de datos correcto para la variable correspondiente; para evitar errores, ahorrar tiempo y memoria, pero también hará que su código sea más fácil de mantener y legible. Los tipos de datos más comunes son:

| Tipo de dato | Tamaño | Descripcion |
|----------|----------|----------|
| Row 1    | Cell 2   | Cell 3   |
| Row 2    | Cell 5   | Cell 6   |
| Row 3    | Cell 8   | Cell 9   |
