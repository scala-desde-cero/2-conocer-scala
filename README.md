# 2-conocer-scala
1. [Introducción a REPL. Herramienta en modo comando](#schema1)
2. [Tipos de Datos](#schema2)
3. [VAR y VAL. Variables](#schema3)

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