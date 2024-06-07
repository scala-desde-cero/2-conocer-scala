# 2-conocer-scala
1. [Introducción a REPL. Herramienta en modo comando](#schema1)
2. [Tipos de Datos](#schema2)
3. [VAR y VAL. Variables](#schema3)
4. [Crear variable en modo Lazy](#schema4)
5. [Comentarios](#schema5)
6. [Operadores](#schema6)
7. [Condiciones. Comando IF](#schema7)
8. [Bucles](#schema8)
9. [Rangos](#schema9)
10. [Inicializar variables por defecto](#schema10)
11. [Pattern Matching](#schema11)
12. [Trabajar con Strings](#schema12)
13. [Trabajar con Números](#schema13)

<hr>

<a name="schema1"></a>

## 1. Introducción a REPL. Herramienta en modo comando


### **REPL**
- Significa `Read-Eval-Print Loop (Bucle Leer-Evaluar-Imprimir)`, y es una característica común en muchos lenguajes de programación, incluido Scala. Un REPL proporciona un entorno interactivo donde puedes escribir código, ejecutarlo inmediatamente, ver los resultados y luego escribir más código.

- Aquí está cómo funciona el proceso en un REPL:

    - **Leer (Read):** El REPL lee la entrada del usuario, que puede ser una expresión, una declaración o un comando.

    - **Evaluar (Evaluate):** Luego, el REPL evalúa la entrada del usuario, es decir, interpreta y ejecuta la entrada.

    - **Imprimir (Print):** Después de evaluar la entrada, el REPL imprime el resultado de la evaluación en la pantalla.

    - **Bucle (Loop):** Una vez que se completa la evaluación y la impresión, el REPL regresa al paso de lectura, donde espera la siguiente entrada del usuario. Este proceso se repite continuamente, de ahí el término "bucle".

En el contexto de Scala, puedes iniciar el REPL de Scala ejecutando el comando `scala` en tu terminal. Esto abrirá una sesión interactiva donde puedes escribir y ejecutar código Scala directamente en la terminal.

![](./img/scala.png)


<hr>

<a name="schema2"></a>

## 2. Tipos de Datos

![](./img/datos_1.png)
![](./img/datos_2.png)

<hr>

<a name="schema3"></a>

## 3. VAR y VAL. Variables


## Declarar Variables

**val nombre_variable : tipo_datos = valor**

```scala
val hola : String = "Hola"
```
![Hola](./img/hola.png)

### **val (Valor Inmutable):**

Una variable declarada con `val` es **inmutable**, lo que significa que su valor no puede ser cambiado después de ser asignado.

Una vez que se asigna un valor a una variable val, ese valor no puede ser modificado ni reasignado.

Se recomienda utilizar val siempre que sea posible, ya que promueve un estilo de programación más funcional y reduce la posibilidad de errores.
```scala
val pi = 3.14
pi = 3.14159
```
![Error](./img/error_val.png)

### **var (Variable Mutable):**

Una variable declarada con `var` es **mutable**, lo que significa que su valor puede ser cambiado después de ser asignado.

Puedes reasignar un nuevo valor a una variable var en cualquier momento.

Aunque puede ser útil en ciertos casos, el uso excesivo de var puede dificultar la comprensión del código y aumentar la posibilidad de errores.
```scala
var x = 10

x = 20
```
![Var](./img/var.png)

<hr>

<a name="schema4"></a>

## 4. Crear variable en modo Lazy

La instanciación en modo `lazy` se refiere a la evaluación diferida de una variable. Una variable lazy se inicializa solo cuando se accede a ella por primera vez. Esto puede ser útil para mejorar el rendimiento en situaciones donde la inicialización de un valor es costosa y puede no ser necesaria en todos los casos.


### **Sintaxis y Comportamiento**
Para declarar una variable lazy, se usa la palabra clave lazy antes de la definición de la variable. Aquí tienes un ejemplo para ilustrar cómo funciona:

```scala
val x=1/0
```
![](./img/lazy_1.png)
Si la declaramos com `lazy`
```scala
lazy val x1=1/0
```
![](./img/lazy_2.png)

```scala
print(x1)
```
![](./img/lazy_3.png)

- **Declaración de lazy val**: La variable x1 se declara, pero no se inicializa inmediatamente.
- **Acceso a x1**: Al intentar acceder a x1 con print(x1), Scala intenta evaluar 1 / 0.
- **Excepción:** La evaluación de 1 / 0 lanza una ArithmeticException debido a la división por cero.
- **Manejo de Excepción:** La excepción se captura en el bloque try-catch y se imprime el mensaje de la excepción.

<hr>

<a name="schema5"></a>

## 5. Comentarios

```scala
// de una sola línea
```
```scala
/*varias
lineas
*/
```
Comentario para documentación
```scala
/*
*doc1
*doc2
*/
```
<hr>

<a name="schema6"></a>

## 6. Operadores

**1. Operadores Aritméticos**

Estos operadores se utilizan para realizar operaciones aritméticas básicas.

- Adición: +
- Sustracción: -
- Multiplicación: *
- División: /
- Módulo: %

**2. Operadores Relacionales**

Estos operadores se utilizan para comparar dos valores.

- Igual a: ==
- No igual a: !=
- Mayor que: >
- Menor que: <
- Mayor o igual que: >=
- Menor o igual que: <=


**3. Operadores Lógicos**

Estos operadores se utilizan para realizar operaciones lógicas.

- AND Lógico: &&
- OR Lógico: ||
- NOT Lógico: !


**4. Operadores de Asignación**

Estos operadores se utilizan para asignar valores a variables.

- Asignación simple: =
- Asignación de suma: +=
- Asignación de resta: -=
- Asignación de multiplicación: *=
- Asignación de división: /=
- Asignación de módulo: %=
**5. Operadores Bit a Bit**

Estos operadores se utilizan para realizar operaciones a nivel de bits.

- AND bit a bit: &
- OR bit a bit: |
- XOR bit a bit: ^
- Negación bit a bit: ~
- Desplazamiento a la izquierda: <<
- Desplazamiento a la derecha: >>
- Desplazamiento a la derecha sin signo: >>>

**6. Operadores de Comparación de Identidad**

Estos operadores se utilizan para comprobar la identidad de referencia de los objetos.

- Igual a: eq
- No igual a: ne

**7. Operadores de Composición de Funciones**

Estos operadores se utilizan para componer funciones.

- Composición hacia adelante: andThen
- Composición hacia atrás: compose

<hr>

<a name="schema7"></a>

## 7. Condiciones. Comando IF


**Sintaxis Básica del if**

La estructura básica de un if en Scala es:

```scala
if (condición) {
  // bloque de código si la condición es verdadera
}
```

**if-else**

El if puede ser seguido por un bloque else para manejar el caso en el que la condición es falsa.

```scala
if (x > 0) {
  println("x es positivo")
} else {
  println("x no es positivo")
}
```

**if-else if-else**

Para manejar múltiples condiciones, puedes usar else if:

```scala
if (x > 0) {
  println("x es positivo")
} else if (x < 0) {
  println("x es negativo")
} else {
  println("x es cero")
}
```

**Expresiones if**

En Scala, las condiciones if son expresiones, lo que significa que devuelven un valor. Puedes asignar el resultado de una condición if a una variable.

```scala
val y = if (x > 0) 1 else -1
println(y) // y será 1 si x es mayor que 0, de lo contrario, -1
```

**Condiciones if Anidadas**

Puedes anidar condiciones if dentro de otras condiciones if:

```scala
if (x > 0) {
  if (x < 10) {
    println("x es un número positivo de un solo dígito")
  } else {
    println("x es un número positivo de dos o más dígitos")
  }
} else {
  println("x no es positivo")
}
```
**Uso de Expresiones Booleanas**

Las condiciones en un if deben ser expresiones booleanas (es decir, que devuelvan true o false):

```scala
val isEven = (x % 2 == 0)

if (isEven) {
  println("x es par")
} else {
  println("x es impar")
}
```
<hr>

<a name="schema8"></a>

## 8. Bucles


**Bucle while**

El bucle while ejecuta un bloque de código mientras una condición sea verdadera. La condición se evalúa antes de cada iteración.

```scala

var i = 0
while (i < 5) {
  println(i)
  i += 1
}
```
**Bucle do-while**

El bucle do-while es similar a while, pero garantiza que el bloque de código se ejecute al menos una vez, ya que la condición se evalúa después de cada iteración.

```scala
var j = 0
do {
  println(j)
  j += 1
} while (j < 5)
```
**Bucle for**

El bucle for en Scala es muy poderoso y puede usarse de varias maneras, incluyendo rangos, colecciones, y con comprensiones (for comprehensions).

- Iteración sobre un rango
```scala
for (i <- 1 to 5) {
  println(i)
}
```
- Iteración sobre una colección
```scala
val nums = List(1, 2, 3, 4, 5)
for (n <- nums) {
  println(n)
}
```
- Comprehensions

Las comprehensions de for son muy potentes y permiten incluir condiciones y generar nuevas colecciones.

```scala
val nums = List(1, 2, 3, 4, 5)
val evenNums = for {
  n <- nums
  if n % 2 == 0
} yield n

println(evenNums) // List(2, 4)
```

<hr>

<a name="schema9"></a>

## 9. Rangos

**Creación de Rangos**

Puedes crear rangos utilizando el operador to o until.

- to: Incluye el valor final.
- until: Excluye el valor final.

```scala
val range1 = 1 to 5    // Incluye 1, 2, 3, 4, 5
val range2 = 1 until 5 // Incluye 1, 2, 3, 4 (no incluye 5)
```

**Especificar el Paso**

Puedes especificar un paso diferente al valor predeterminado de 1 usando by.

```scala
val range3 = 1 to 10 by 2  // Incluye 1, 3, 5, 7, 9
val range4 = 10 to 1 by -1 // Incluye 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
```

**Rangos con Bucles for**

Los rangos son comúnmente utilizados en bucles for para iterar sobre secuencias de números.

```scala
for (i <- 1 to 5) {
  println(i)  // Imprime 1, 2, 3, 4, 5
}
```
```scala
for (i <- 1 until 5) {
  println(i)  // Imprime 1, 2, 3, 4
}
```

**Operaciones con Rangos**

Los rangos en Scala soportan varias operaciones útiles que se pueden realizar sobre ellos como cualquier otra colección.

- Convertir un rango a una lista:
```scala
val rangeList = (1 to 5).toList  // List(1, 2, 3, 4, 5)
```
- Filtrar elementos en un rango:
```scala
val evenNumbers = (1 to 10).filter(_ % 2 == 0)  // Vector(2, 4, 6, 8, 10)
```
- Mapear sobre un rango:
```scala
val squaredNumbers = (1 to 5).map(x => x * x)  // Vector(1, 4, 9, 16, 25)
```


<hr>

<a name="schema10"></a>

## 10. Inicializar variables por defecto

Puedes inicializar variables directamente con valores por defecto al declararlas.
**Usar var para Variables Inmutables**
```scala
val intVar: Int = 0
val doubleVar: Double = 0.0
val stringVar: String = ""
val boolVar: Boolean = false
val listVar: List[Int] = List()
```


**Usar var para Variables Mutables**

Si necesitas una variable que pueda cambiar de valor, usa var en lugar de val. Aún así, puedes proporcionar un valor por defecto.

```scala
var mutableIntVar: Int = 0
var mutableStringVar: String = ""
```
**Valores por Defecto en Clases**

En las clases, puedes proporcionar valores por defecto para los parámetros del constructor. Esto es útil para evitar la necesidad de múltiples constructores.

```scala
class Person(val name: String = "John Doe", val age: Int = 30)

val defaultPerson = new Person()      // Usará los valores por defecto
val customPerson = new Person("Alice", 25)  // Usará los valores proporcionados
```
**Valores por Defecto en Métodos**

También puedes proporcionar valores por defecto para los parámetros de los métodos.

```scala
def greet(name: String = "Guest"): Unit = {
  println(s"Hello, $name!")
}

greet()          // Usará el valor por defecto "Guest"
greet("Alice")   // Usará el valor proporcionado "Alice"
```

**Usar Option para Valores que Pueden ser Nulos**

Para manejar valores que pueden ser nulos o no estar presentes, es una buena práctica usar Option en lugar de valores nulos (null).

```scala
val maybeInt: Option[Int] = None  // Representa un valor opcional que puede estar presente o no

// Inicializando con un valor
val someInt: Option[Int] = Some(42)
```

<hr>

<a name="schema11"></a>

## 11. Pattern Matching 


El `Pattern Matching` (o coincidencia de patrones) es una característica poderosa y expresiva de Scala que permite comprobar un valor contra un patrón y, en función de ese patrón, ejecutar un bloque de código.

**Conceptos Básicos**

La coincidencia de patrones se usa principalmente con la construcción match en Scala. Aquí tienes un ejemplo básico:

```scala
val x: Int = 10

x match {
  case 1 => println("One")
  case 2 => println("Two")
  case _ => println("Other number")
}
```
En este ejemplo, x se compara con los patrones 1, 2, y un comodín _ (que coincide con cualquier otro valor). Dependiendo del valor de x, se ejecutará uno de los bloques de código correspondientes.


**Patrones Comunes**
- Literales: Coinciden con valores específicos.

```scala
val x: Int = 10

x match {
  case 10 => println("Ten")
  case _  => println("Not Ten")
}
```
- Comodín _: Coincide con cualquier valor y generalmente se usa como un caso predeterminado.

```scala
val x: Int = 10

x match {
  case 1 => println("One")
  case _ => println("Other number")
}
```
- Variables: Coinciden con cualquier valor y lo asignan a una variable.

```scala
val x: Int = 10

x match {
  case y => println(s"Got $y")
}
```
- Constructor de clases: Coincide con la estructura de un objeto.

```scala
case class Person(name: String, age: Int)

val person = Person("Alice", 25)

person match {
  case Person(name, age) => println(s"Name: $name, Age: $age")
}
```
- Listas: Coincide con estructuras específicas de listas.

```scala
val list = List(1, 2, 3)

list match {
  case List(1, 2, 3) => println("List is 1, 2, 3")
  case _ => println("Other list")
}
```
- Tipos: Coincide con tipos específicos.

```scala
def describe(x: Any): String = x match {
  case i: Int => "an integer"
  case s: String => "a string"
  case _ => "something else"
}

println(describe(42))      // Output: an integer
println(describe("hello")) // Output: a string
println(describe(2.0))     // Output: something else
```


### **Uso Avanzado**
**Guardas**

Puedes agregar condiciones adicionales a un patrón usando guardas (if).

``scala
val x: Int = 10

x match {
  case n if n % 2 == 0 => println(s"$n is even")
  case n if n % 2 != 0 => println(s"$n is odd")
}
```
**Patrones Anidados**

Puedes tener patrones anidados para coincidir con estructuras de datos más complejas.

```scala
case class Address(city: String, zip: String)
case class Person(name: String, address: Address)

val person = Person("Alice", Address("Wonderland", "12345"))

person match {
  case Person(name, Address(city, _)) => println(s"$name lives in $city")
}
```
**Scala 3 Mejoras**

Scala 3 trae mejoras y nuevas características a Pattern Matching, manteniendo la compatibilidad con la sintaxis y funcionalidad de Scala 2.

- Patrones de Tipos Sellados

Scala 3 introduce mejores verificaciones exhaustivas para tipos sellados, lo que hace que el compilador sea más inteligente en detectar patrones no cubiertos.

```scala
sealed trait Animal
case class Dog(name: String) extends Animal
case class Cat(name: String) extends Animal

def describeAnimal(animal: Animal): String = animal match {
  case Dog(name) => s"This is a dog named $name"
  case Cat(name) => s"This is a cat named $name"
}
```

<hr>

<a name="schema12"></a>

## 12. Trabajar con Strings

### **Declaración de Strings**

En Scala, las strings se pueden declarar de manera sencilla usando comillas dobles:

```scala
val greeting: String = "Hello, Scala!"
```
### **Operaciones Básicas**
- **Concatenación**

Puedes concatenar strings usando el operador +:

```scala
val firstName = "John"
val lastName = "Doe"
val fullName = firstName + " " + lastName  // "John Doe"
```
También puedes usar la interpolación de strings, que es más legible y flexible:

```scala
val fullName = s"$firstName $lastName"  // "John Doe"
```
- **Interpolación de Strings**

  Scala ofrece tres tipos de interpolación de strings:

  * s-interpolator: Permite embedir variables y expresiones directamente en la string.

  ```scala
  val name = "Alice"
  val age = 25
  val greeting = s"Hello, my name is $name and I am $age years old."
  ```
  - f-interpolator: Similar a s-interpolator, pero permite formatear la salida.

  ```scala
  val height = 1.75
  val formatted = f"$name%s is $height%2.2f meters tall."
  ```
  - raw-interpolator: Similar a s-interpolator, pero no interpreta secuencias de escape.

  ```scala
  val rawString = raw"This is a \n raw string."
  ```
### **Métodos Comunes**
- **Obtener Longitud**
```scala
val str = "Hello, Scala!"
val length = str.length  // 13
```
- **Acceder a Caracteres**
Puedes acceder a un carácter específico usando el índice (los índices comienzan en 0):

```scala
val char = str(0)  // 'H'
```
- **Substrings**
Para obtener una subcadena:

```scala
val substr = str.substring(7, 12)  // "Scala"
```
- **Conversión de Mayúsculas/Minúsculas**
```scala
val upper = str.toUpperCase  // "HELLO, SCALA!"
val lower = str.toLowerCase  // "hello, scala!"
```
- **División**
Dividir una string en partes:

```scala
val parts = str.split(",")  // Array("Hello", " Scala!")
```
- **Reemplazo**
Reemplazar partes de una string:

```scala
val replaced = str.replace("Scala", "World")  // "Hello, World!"
```
- **Eliminación de Espacios**
Eliminar espacios en blanco al principio y al final:

```scala
val trimmed = str.trim  // "Hello, Scala!"
```
### **Comparación de Strings**
Comparar strings en Scala:

```scala
val str1 = "Scala"
val str2 = "scala"

val isEqual = str1 == str2  // false
val isEqualIgnoreCase = str1.equalsIgnoreCase(str2)  // true
```
### **Strings Multilínea**

Scala permite definir strings multilínea usando triple comillas:

```scala
val multiline = """This is a
                  |multiline
                  |string.""".stripMargin
```
### **Uso Avanzado**
- **Patrones y Expresiones Regulares**
Puedes usar expresiones regulares para coincidencia de patrones en strings:

```scala
val pattern = "Scala".r
val str = "I love Scala programming"

pattern.findFirstIn(str) match {
  case Some(_) => println("Found")
  case None => println("Not Found")
}
```
- **Formateo de Strings**
Formatear strings de manera similar a printf en otros lenguajes:

```scala
val name = "Alice"
val age = 25
val formatted = "%s is %d years old".format(name, age)  // "Alice is 25 years old"
```
<hr>

<a name="schema13"></a>

## 13. Trabajar con Números

### **Tipos Numéricos en Scala**
Scala tiene varios tipos de datos numéricos que se corresponden con los tipos de datos primitivos de Java:

- Byte: Entero de 8 bits con signo.
- Short: Entero de 16 bits con signo.
- Int: Entero de 32 bits con signo.
- Long: Entero de 64 bits con signo.
- Float: Número de coma flotante de 32 bits.
- Double: Número de coma flotante de 64 bits.
- Char: Caracter Unicode de 16 bits.
### **Declaración de Variables Numéricas**
Puedes declarar variables numéricas de manera sencilla:

```scala
val intNum: Int = 42
val doubleNum: Double = 3.14
val longNum: Long = 123456789L
val floatNum: Float = 2.5f
```
### **Operaciones Aritméticas**
Scala soporta las operaciones aritméticas básicas:

```scala
val a = 10
val b = 20

val sum = a + b        // 30
val diff = a - b       // -10
val product = a * b    // 200
val quotient = b / a   // 2
val remainder = b % a  // 0
```
### **Métodos Numéricos**
Scala proporciona varios métodos útiles para trabajar con números:

- **Conversión de Tipo**
Puedes convertir entre tipos numéricos:

```scala
val x: Int = 10
val y: Double = x.toDouble  // 10.0
val z: String = x.toString  // "10"
```
- **Comparaciones**
Puedes comparar números utilizando los operadores estándar:

```scala
val x = 10
val y = 20

val isEqual = x == y       // false
val isNotEqual = x != y    // true
val isGreater = x > y      // false
val isLess = x < y         // true
val isGreaterOrEqual = x >= y  // false
val isLessOrEqual = x <= y  // true
```
- **Métodos Matemáticos**
Scala también tiene métodos matemáticos más avanzados a través del objeto scala.math:

```scala
import scala.math._

val piValue = Pi               // 3.141592653589793
val sqrtValue = sqrt(16)       // 4.0
val powValue = pow(2, 3)       // 8.0
val absValue = abs(-5)         // 5
val maxValue = max(10, 20)     // 20
val minValue = min(10, 20)     // 10
```
### **Números Aleatorios**
Puedes generar números aleatorios usando scala.util.Random:

```scala
import scala.util.Random

val random = new Random()
val randomInt = random.nextInt()      // Un número entero aleatorio
val randomIntBounded = random.nextInt(100)  // Un número entero aleatorio entre 0 y 99
val randomDouble = random.nextDouble()  // Un número doble aleatorio entre 0.0 y 1.0
```