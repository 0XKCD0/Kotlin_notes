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

### Loops ( Control Flow Statements)
_____________________________________________________

1. while loop

It consists of a block of code and a condition. First of all the condition is evaluated and if it is true then execute the code within the block. It repeats until the condition becomes false because every time the condition is checked before entering into the block.
```
fun main(){
    var count = 5
    while (count<9){
        println("hi")
        count ++
    }
}
```

2. do while loop

do-while loop is a control flow statement which executes a block of code at least once without checking the condition.

```
fun main(){
    var index = 5
    do{
        println("hii")
    }while (index>5)
}
```

3. for loop

 The for loop is used to loop through arrays, ranges, and other things that contains a countable number of values.
 It is used to iterate through the following because all of them provides iterator.

+ Range
+ Array
+ String
+ Collection

```
fun main(){
    // in
    println("in")
    for (i in 1..10){
        println(i)
    }

    // until
    println("until")
    for( i in 1 until 10){
        println(i)
    }

    // step
    println("step")
    for(i in 1..10 step 2){
        println(i)
    }

    // down to
    println("down to")
    for (i in 10 downTo 1){
        println(i)
    }
}

```
**Table of 2 using for loop**

```
fun main(){
    val number = 2
    for(i in 1..10){
        println(number*i)
    }
    println()
    for ( i in 1..10){
        println(number.toString() + "x" + i + "=" + (number*i))
    }

    println()
    println("String templating")
    for (i in 1..10){
        println("$number * $i = ${number*i}")
    }
}
```

**String Templating ----> String templates are string literals that contain embedded expressions. The template expression starts with a $. Since string literals cannot be modified after creation, using string templates gives us a simpler way to add expressions in strings without creating multiple strings.**

### Function Overloading
__________________________________

The function name are same but has different parameters. Either number of parameters are different or type of parameter is different.

```
import kotlin.math.pow

fun main(){
    println(addition(3,5))
    println(addition(23.0, 24.0))
    var fn = ::power
    println(fn(2.0, 20.0))
//This feature is called "function reference" or "method reference." It allows you to reference a function
// or method without actually invoking it, and you can store the reference for later use.
}

fun addition(a: Int, b: Int) : Int {
    return a+b
}

fun addition (a: Double, b: Double) : Double {
    return a+b
}

fun power(a: Double, b: Double) : Double {
    return a.pow(b)
}
```

### Arrays
_______________________________________

It is an object that stores multiple values of same type.

```
fun main(){
    var arr = arrayOf("one", "two","three")
    var arr1 = arrayOf(1,2,3)

    var arr2 = arrayOf<Int>(3,5,8) // explicit decleration

    for((i, e) in arr.withIndex()){
        println("$i - $e")
    }

    println(arr[0]) //or
    println(arr.get(2))
    arr.set(0, "hello")
    println(arr[0])
    println(arr.size)
}
```
# Kotlin - OOP language
________________________

Paradigm which allows us to solve problems with the help of object which represents real world entities.
___________________________________________________

### Classes And Objects
__________________________
 - Class is a blueprint/template.
 - Objects are the real thing.
 - We create objects in our program and they interact with each other to complete work.

```
fun main(){
    val mustang = Car("Mustang", "Petrol", 1200)
    val BMW = Car("BMW", "Diesel", 3900)

    println(mustang.name)
    println(BMW.kmRun)
    mustang.drive()
    BMW.appliedBrakes()

}

class Car(val name: String, val type: String, var kmRun: Int){
    fun drive(){
        println("$name car is driving.")
    }

    fun appliedBrakes(){
        println("$name car applied their fucking brakes.")
    }
}
```
Extended :-
```
fun main(){
    val i:Int = 20
    println(i.plus(30))
    println(i.toFloat())

    val P1 = Person("Vishal", 34) // object creation
    val p2 = Person("meah", 12)

    println(P1.canVote())
    println(p2.canVote())
}

class Person(val name: String, val age: Int){
    fun canVote(): Boolean{
        return age>18
    }
}
```
### Constructors
_________________________________________

A constructor is a special member function that is invoked when an object of the class is created primarily to initialize variables or properties. A class needs to have a constructor and if we do not declare a constructor, then the compiler generates a default constructor. Kotlin has two types of constructors:

+ Primary Constructor
+ Secondary Constructor
```
  fun main(){

    var car = Automobile("Mercedes", "Petrol", 4, 2)
    var person = Individual("rohit", 39)
    println(person.age)
    println(person.name)

    var person1 = Individual("bunny", 19)
    println(person1.age)
    println(person1.name)
    println(person1.CanVote)
}


class Automobile(val name: String, val type: String, val Tyres: Int, val MaxSeating: Int ){ //primary constructor
    fun drive(){}
    fun applyBrakes(){}
}

class Empty{}

class Individual (nameParam: String, ageParam: Int){ // we can perform task with this approach
    val name: String = nameParam  
    val age: Int = ageParam
    var CanVote: Boolean= age>20
}
```

### Getters and Setters
_______________________________________

Setter is used to set the value of any variable and Getter is used to get the value.
```
fun main(){
    val ob = Calculator()
    println(ob.add(3,3))

    val ob1 = Person1("cheezy", 12)
    println(ob1.age)
    ob1.age = 23
    ob1.age = -13
    println(ob1.name)
}

class Calculator(){
    fun add(a : Int, b: Int): Int{
        return a+b
    }
    fun multiply(a : Int, b: Int): Int{
        return a*b
    }

}

class Person1 (nameParam: String, ageParam: Int){
    var name: String = nameParam
        get() {
            println("Name getter is called")
            return field.toUpperCase()
        }
    var age: Int = ageParam
        set(value) {
            if (value>0){
                field = value
            }
            else{
                println("Age can't be negative")
            }
        }
}

```
### Inheritance
___________________________________

It allows you to define a new class based on an existing class. The existing class is known as the superclass or base class, and the new class is known as the subclass or derived class. The subclass inherits all the properties and functions of the superclass, and can also add new properties and functions or override the properties and functions inherited from the superclass.

```
fun main(){
    val objmyChild = Child()
    objmyChild.myMethod()
    objmyChild.myMethod2()

    val objchild = Child()

}

open class Parent(){

    init {
        println("Parent constructor is called")
    }
    val name: String = ""
    fun myMethod(){
        println("I'm in parent")
    }
}

class  Child(): Parent(){

    init {
        println("Child constructor is called")
    }
    val name2: String = ""
    fun myMethod2(){
        println("I'm in child")
    }
}
```
### Overriding in Kotlin - INHERITANCE
_______________________________________________

If the base class and derived class contain a member function with the same name, then we can override the base member function in the derived class using the override keyword and also need to mark the member function of the base class with open keyword.

```
fun main(){
    val onePlus = onePlus("SmartPhone")
    onePlus.display()
    val generalMobile = Mobile("General Mobile")
    generalMobile.makeCall()
    println(onePlus.toString())
}

open class Mobile(val type: String){
    open val name: String = ""
    open val size: Int =5
    fun makeCall() = println("Calling from mobile")
    fun powerOff() = println("Shutting down")
    open fun display() = println("Simple mobile display")
}

class onePlus(typeParam: String): Mobile(typeParam)
{
    override val name: String = "onePlus"
    override val size: Int = 6
//    override fun display() = println("OnePlus Display")
    override fun display(){
        super.display()
        println("One Plus Display")
    }

    override fun toString(): String {
        return "Name - $name   Size - $size"
    }
}
```

### Polymorphism
_____________________________________

Parent can hold a reference to its child. Parent can also call methods of child classes (which are common).
```
fun main(){
//    val circle: Circle = Circle(6)
//    val Square: Square = Square(4)
    val circle: Shape = Circle(6.0) //Polymorphism
    val Square: Shape = Square(4.0)

//    println(circle.area())
//    println(Square.area())
    val shapes = arrayOf(Circle(3.0), Square(7.0), Circle(2.0), Square(2.0), Triangle(4.0,5.0))
    calculateAreas(shapes)
    
}

fun calculateAreas(shapes: Array<Shape>){
    for (shape in shapes){
        println(shape.area())
    }
}

open class  Shape{
    open fun area(): Double{
        return 0.0
    }
}

class Circle(val radius: Double): Shape(){
    override fun area(): Double {
        return Math.PI * radius * radius
    }
}

class  Square(val side: Double): Shape(){
    override fun area(): Double {
        return side*side
    }
}

class Triangle(val base: Double, val height: Double): Shape(){
    override fun area(): Double {
        return 0.5 * base * height
    }
}
```

### Abstraction
_________________________

An abstract class is a class that cannot be instantiated and is meant to be subclassed. An abstract class may contain both abstract methods (methods without a body) and concrete methods (methods with a body). An abstract class is used to provide a common interface and implementation for its subclasses. When a subclass extends an abstract class, it must provide implementations for all of the abstract methods defined in the abstract class.

```
fun main(){
    val circle = circle1(4.0)
    println(circle.area())
    circle.display()

}

//abstract class A{
//    fun method1() {
//        println("i am method")
//    }
//}

abstract class shape(){
    var name: String = ""
    abstract fun area(): Double
    abstract fun display()
}

class circle1(val radius: Double) : shape(){
    override fun area(): Double = Math.PI * radius * radius
    override fun display() {
        println("cIRCLE IS GETTING DISPLAYED.")
    }
}

```
### Interface
___________________________

An interface is a collection of abstract methods and properties that define a common contract for classes that implement the interface. An interface is similar to an abstract class, but it can be implemented by multiple classes, and it cannot have state.

Interfaces are custom types provided by Kotlin that cannot be instantiated directly. Instead, these define a form of behavior that the implementing types have to follow. With the interface, you can define a set of properties and methods, that the concrete types must follow and implement.

```
fun main(){
    dragObjects(arrayOf(Circle2(9.0), Square1(3.0), Triangle1(3.0,4.0), Player("Smiley")))
}

fun dragObjects(objects: Array<draggable>){
    for (obj in objects){
        obj.drag()
    }
}

interface draggable{
    fun drag()
}

abstract class Shape1: draggable{
    abstract fun area(): Double
}

class Circle2(val radius: Double) : Shape1(){
    override fun area(): Double = Math.PI * radius * radius
    override fun drag() = println("Circle is dragging")
}

class Square1(val sides: Double) : Shape1(){
    override fun area(): Double = sides * sides
    override fun drag() = println("Square is dragging")
}

class Triangle1(val base: Double, val height: Double): Shape1(){
    override fun area(): Double = 0.5 * base* height
    override fun drag() = println(" Triangle is dragging")
}

class Player(val name: String): draggable{
    override fun drag() = println("$name is dragging")
}

```

### Visibility Modifiers
____________________________________________


|    Modifiers       | Top Level Decleration  |    Class Members     |
| ------------------ | ---------------------- | -------------------- |
|    Public          |      Everywhere        |      Everywhere      |
|    Internal        |    Within a module     |    Within a module   |
|    Private         |      Within file       |    Within class      |
|    Protected       |          n/a           |    Subclasses        |


### Object Declaration
_____________________________________

It always has a name following the object keyword. Just like a variable declaration, an object declaration is not an expression, and it cannot be used on the right-hand side of an assignment statement.

```
fun main(){
    println(A.num)
    B.test()
}

object A{
    val num: Int = 10
}

object B{
    val p: Int = 20
    fun test(){
        println("I am object B")
    }
} 
```

```
fun main(){
    sharing_widget.increment_facbook_likes()
    sharing_widget.increment_twitter_likes()
    sharing_widget.increment_twitter_likes()
    sharing_widget.display()
    sharing_widget.increment_facbook_likes()
}

object sharing_widget{
    private var twitter_likes=0
    private var facebook_likes=0

    fun increment_twitter_likes()= twitter_likes++
    fun increment_facbook_likes()= facebook_likes++
    fun display()= println("facebook - $facebook_likes -- Twitter - $twitter_likes")
}
```

### Object Expression
_______________________________

Object expressions create objects of anonymous classes, that is, classes that aren't explicitly declared with the class declaration. Such classes are useful for one-time use. We can define them from scratch, inherit from existing classes, or implement interfaces. Instances of anonymous classes are also called anonymous objects because they are defined by an expression, not a name.

```
fun main(){
    var obj = object : person0("shivangi"){
        override fun fullName() {
            super.fullName()
            println("anonymous - $name")
        }
    }
    obj.fullName()
}

interface cloneable{
    fun clone()
}

open class person0(val name: String){
    open fun fullName() = println("Full Name - $name")
}
```

### Companion Object
____________________________

An object declaration inside a class can be marked with the companion keyword. Members of the companion object can be called simply by using the class name as the qualifier. Class members can access the private members of the corresponding companion object.

```
fun main(){
    myClass.myobject.f() // redundancy can be seen
    myClass.anotherobject.g()
    myClass.f()
}

class myClass{
    companion object myobject{
        fun f(){
            println("I am object f from myobject")
        }
    }

    object anotherobject{
        fun g(){
            println("I am object g from anotherobject")
        }
    }
}
```








