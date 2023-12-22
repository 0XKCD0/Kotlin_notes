# Kotlin_notes
Notes for Kotlin 

### What is Kotlin?
__________________________

* New programming language by JetBrains.
* JetBrains developed software like Android Studio, IntelliJ, Idea, pyCharm, etc.
* It Targets JVM, Android, Native and Js.


### Features of Kotlin
_____________________________

1. Statically typed language - It means before source code is compiled, the type associated with each and every single variable must be known. or Kotlin is a statically typed language which means that it does most the check at compile time rather being dependent on runtime.
2. Object Oriented - Abstraction, Encapsulation, Inheritance and Polymorphism.
3. Functional Lnguage (Higher Order Function) - If your function accepts function as a parameter or returns function as a result than it’s called high order function.
```
fun addValue(operation:(Int,Int) -> Int):Int {
  return operation(10,20)
}
addValue{num1,num2 -> num1 * num2} //This will print 200
addValue{num1,num2 -> num1 - num2} //This will print -10
```
4. Interoperable - It is 100% interoperable with Java.
5. Concise - Less lines of code.
6. Safe - Kotlin's type system is aimed at eliminating the danger of null references, also known as The Billion Dollar Mistake.

<mark>Null Pointer exception - It is a runtime exception in Java that occurs when a variable is accessed which is not pointing to any object and refers to nothing or null.</mark>

7. Open Source - Anyone can use it.


### Why JAVA (JDK) ?
________________________________________

KOTLIN FILES(.kt) -----(compile)------->  Byte Code -----(run)---->     JVM

### Hello Program
____________________________________________

```
fun firstProgram(){
  println("Hello")
}
```

### Function
____________________________________________

Functions are a set of instructions to perform some task.

Syntax:
```
fun fun_name(input arguements)
{
  some task
  //....
  //...
}
```
### Compilation
____________________________

Kotlin ----(KotlinC-JVM)---> Byte code(.class files) ---------> JVM --------> OUTPUT

### Variables
___________________________

* Simple box to store and hold data.
* Each variable has a name to access its data.
* var and val
    + var can be reassigned.
    + val cannot be reassigned.


 ### Operators
 ________________________________________

 1. Arithematic Operators:
     + Addition(+)
     + Subtraction(-)
     + Multiplication(*)
     + Division(/)
     + Modulous(%)

2. Relational Operators:
      + Less than (<)
      + Greather than (>)
      + Less than equal to (<=)
      + Greather than equal to (>=)
      + Structural Equality (==)
      + Not equals (!=)

  3. Logical Operators:
     + AND (&&)
     + OR (||)
     + NOT (!)

  4. Short Circuiting: It refers to the behavior of logical operators (e.g., && for AND and || for OR) where the second operand is only         evaluated if the result can be determined from the first operand. This means that in certain situations, the second operand is not         evaluated at all, which can improve performance and prevent potential errors.
```
Short Circuiting (AND)
val x = false
val y = true
val result = x && y  // 'y' is not evaluated because 'x' is false

```
```
Short Circuiting (OR)
val x = true
val y = false
val result = x || y  // 'y' is not evaluated because 'x' is true

```

### if-else 
___________________________

In Kotlin **if** is an expression. It is called an expression because it compares the value.

```
fun main(){
    val a=4
    if (a % 2 == 0){
        println("It is divisible by 2")
    }
    else{
        println("It is not divisible by 2")
    }
}
```
if-else ladder
_____________________

A user can put multiple conditions. All the ‘if’ statements are executed from the top to bottom. One by one all the conditions are checked and if any of the conditions is found to be true then the code associated with the if statement will be executed and all other statements bypassed to the end of the block. If none of the conditions is true, then by default the final else statement will be executed. 

```
fun main(){
    val age = 12
    if (age > 18){
        println("eligible to vote and drive")
    }
    else if (age<18){
        println("not eligible to vote")
    }
    else{
        println("invalid choice")
    }
}
```
if-else expression
__________________________

```
fun main(){
    val a = 22
    val b = 42
    val result = if (a>b){
        "a is greater than b"
    }
    else if(a<b){
        "a is less than b"
    }
    else{
        "a equals b"
    }
    println(result)
    //Call the alternate fun
   alternate()
}

fun alternate(){
    val num=21
    val res = if (num%2==0) "even" else "odd"
    println(res)
}
```

### Kotlin when expression
_______________________________________

**when** replaces the switch operator of Java. The argument of when expression compares with all the branches one by one until some match is found. After the first match is found, it reaches to end of the when block and executes the code next to the when block.

```
fun main(){
    val num = 15
    // in is an operator and .. is used for defining the range
    val result = num in 1..6
    println(result)
    when_operator()
    until_operator()
}
// when can be also used as an expression
fun when_operator(){
    val animal = "Dog"
    when(animal){
        "Horse" -> println("Animal is horse")
        "cat" -> println("Animal is cat")
        "Dog" -> println("Animal is dog")
        "lion" -> println("Animal is lion")
        else -> println("animal not found")
    }
}
fun until_operator(){
    val number = 42
    val res = number until 42
    println(res)
}

```

### Loops
_______________________________________________

1. while loop

Checks for condition then executes.
```
fun main(){
    var count = 5
    while (count<9){
        println("hi")
        count ++
    }
}
```
---------------------------------------------------
2. do while loop

First executes the statement minimum for 1 time and the checks for condition.

```
fun main(){
    var index = 5
    do{
        println("hii")
    }while (index>5)
}
```
---------------------------------------------------
3. for loop










