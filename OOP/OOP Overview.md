## 1. Programming Paradigms: An Overview
Before diving into Object-Oriented Programming (OOP) concepts, it's important to understand the broader umbrella under which OOP falls which called "Programming Paradigms"

The term 'paradigm' refers to the way you write and design your code. There are two primary types of programming paradigms:

### Imperative Programming Paradigm 
In the imperative paradigm, you explicitly define the sequence of operations, focusing on how each task is accomplished (e.g. OOP, Produral Programming, Structured Programming).

```csharp
// Initialize the sum variable
int sum = 0;
var arr = [3, 1, 9, 5];

// Calculate the sum by iterating through the array
for (int i = 0; i < arr.Length; i++) {
    sum += arr[i];
}

// Print the result
Console.WriteLine(sum);
```
### Declarative Programming Paradigm

In the declarative paradigm, you focus on describing the desired outcome rather than detailing the steps to achieve it. The "how" is handled by the system (e.g. Database Proccessing approach, Logical Programming, Funcitonal programming).

```csharp
var arr = [3, 1, 9, 5];
int sum = arr.Aggregate((i, j) => i + j); // Perform aggregation and obtain the result

Console.WriteLine(sum);
```

```sql
-- The query specifies: "Return numbers greater than five" without needing to define how it's done (~ loop on numbers and check the condition....)
SELECT num FROM numbers WHERE num > 5;
```
---
## 2. Philosphy behind OOP
In the early days, paradigms like Procedural and Functional were commonly used in programming languages such as C and Fortran.
In these paradigms, systems were typically modeled as a sequence of steps (like in the first example of this document), or by breaking the program into smaller functions (as in the second example).

However, with the advent of Object-Oriented Programming (OOP) and languages like Smalltalk and Simula, a new approach emerged.
OOP introduced the idea of thinking about programs as collections of classes. These classes have both attributes (characteristics) and methods (behaviors).

The `class` keyword defines a blueprint that specifies the structure and behavior of objects.  
A class itself is not stored in memory; instead, **objects** (instances or live version of the class) are saved in memory, and these objects hold their own attributes and can use the methods defined by the class.
```csharp

class Customer{ // Class
    // attributes (characteristics) 
    int age;
    int Balance;
    bool hasPremiumAccount; 

    // methods (behaviors)
    void Purchase(Product product){
        // Purchase logic...
    }
}
class Program{
    public static void Main(){
        Customer c = new Customer() ; // Object
    }
}

```
> Languages like **C#** and **Java** are primarily **object-oriented** and encourage OOP as the main programming paradigm, while languages like
**C++** and **Python** are **multi-paradigm**, meaning they support OOP but also allow other styles like procedural and functional programming, while languages like ***C*** does not support OOP at all.

---
Some languages provide **special member functions** that control the lifecycle of an object, such as ```constructors``` and (in languages like C++) ```destructors```.

- ```Constructor``` — A special function automatically called immediately after an object is created. Used to initialize the object.  
- ```Destructor``` — A special function automatically called just before an object is destroyed. Used for cleanup tasks.

#### Example in C++
```cpp
#include <iostream>

class Factory {
public:
    Factory() {
        std::cout << "Factory is opening...\n";
    }

    ~Factory() {
        std::cout << "Factory is closing...\n";
    }
};
```
> Note that : In languages with automatic garbage collection (like Java or C#), explicit destructors are typically unnecessary because memory cleanup is handled by the garbage collector.
---
## 3. OOP concepts
Object-Oriented Programming (OOP) is built on four main concepts: encapsulation, abstraction, inheritance, and polymorphism. Additional concepts like association, aggregation, and composition were introduced later. This section will focus on the four core principles.

---
### Inheritance 
Inheritance is the mechanism that allows a class (```child``` or ```subclass```) to acquire the attributes and methods of another class (```parent``` or ```superclass```)

```cpp
class Parent{
    public int x;
    public void func(){}
}

class Child : Parent{

}
int main(){
    Child c = new Child();

    cout << c.x << ' ' ; // var 'x' can be accessed from child 'c'
    cout << c.func() ; // function 'func()' can be accessed from child 'c'
}
```

> Languages like `C#` and `Java` support **single inheritance** (inheriting from one superclass), whereas languages like `C++` allow **multiple inheritance** (inheriting from more than one superclass).

---
### Abstraction 
Abstraction involves showing only the essential methods and attributes of an object, while hiding the unnecessary details.

#### Abstract classes & Interfaces
```Abstract classes``` and ```Interfaces``` are tools used to implement abstraction in OOP-based languages. Both serve as blueprints or contracts for the classes that use them.

- ```Abstract Class``` : a class that cannot be instantiated on its own, meaning you cannot create an object directly from it. Its main role is to act as a base class for other classes, called subclasses or derived classes.

It can have both implemented and non-implemented function 
```csharp
public abstract class A
{
    private int _x;

    public abstract int setX(int x); // non-implemented function

    public int getX() // implemented function
    {
        return _x; 
    }
}
```

- ```Interface``` : a contract with method headers (non-implemented functions) only but no ```attributes```, ```constructors```, or ```destructors```. Some languages (like C# and Java *latest versions*) allow default method implementations.

```csharp
public interface ITrial // intefraces naming should be start with 'I'
{
    public int A(); // non-implemented function

    public int B() // implemented function
    {
        return 0;
    }
}
```
#### **```A class can implement one or more interface.```**

---
#### Two types of Abstraction
- Data Abstraction : make data is not visible to the outer world, and access it through some methods.
```csharp
class A{
    private int _a;
    public getA(){ return _a;}
    public setA(int a){_a = a;}
}
```
- Process Abstraction : hide the internal implementation of the different functions involved in a user operation.
```csharp
abstract class BeverageMachine
{
    public abstract void BoilWater();
    public abstract void AddIngredients();
    public abstract void Pour();

    public void MakeBeverage()
    {
        BoilWater();
        AddIngredients();
        Pour();
        Console.WriteLine("Your beverage is ready!");
    }
}
```
```csharp
// Concrete class that implements the abstract steps for tea
class TeaMachine : BeverageMachine
{
    public override void BoilWater() => Console.WriteLine("Boiling water for tea...");

    public override void AddIngredients() => Console.WriteLine("Adding tea leaves to boiling water...");

    public override void Pour() => Console.WriteLine("Pouring tea into the cup...");
}
```
```csharp
class Program
{
    static void Main()
    {
        TeaMachine teaMachine = new TeaMachine();
        teaMachine.MakeBeverage();
    }
}
```
---
### Encapsulation
Encapsulation is about combining attributes and functions in one single unit (class).

#### Why ? 
- Data Hiding: Encapsulation keeps an object's data safe by hiding it from outside access. Only specific methods can access it.
- Better Security: By limiting direct access to data, encapsulation helps prevent accidental changes and protects against security issues.
- Code Reusability: Encapsulation groups related code into one class, making it easy to reuse in other programs.

#### How ?
In most object-oriented programming (OOP) languages, there are access modifiers—keywords like ```public```, ```protected```, and ```private``` used to control the visibility and accessibility of class members (attributes, methods, etc.).

Typically, ```private``` attributes are accessed and modified through ```getter``` and ```setter``` methods. Here's an example to help clarify:

```csharp
class ExampleClass {
    public int a;         // 'a' is public: accessible from anywhere in the code.
    private int _b;       // '_b' is private: accessible only within this class.
    protected int c;      // 'c' is protected: accessible within this class and its subclasses.

    // Getter for _b 
    public int GetB() {
        // logic can be added here to control read access.
        return _b;
    }

    // Setter for _b
    public void SetB(int b) {
        // logic can be added here to validate or restrict assignment.
        _b = b;
    }
}
```
> **Note:** Prefixing private fields with an underscore (e.g., `_b`) is a common naming convention for private attributes.

> **Note:** Encapsulation can be seen as a complementary tool to achieve abstraction. While abstraction focuses on *what* to hide, encapsulation deals with *how* to hide it.

---
### Polymorphism 
Polymorphism : The ability of the same function or interface to operate differently based on the object or data type it is acting upon.

For example, in the code below, the ```+``` operator adds integers when used with numbers, but concatenates values when used with strings.
```cpp
int main(){
    string str = "";
    int num = 0;

    str += "something";
    num += 2;

    cout << str << '\n' << num; 
    return 0;
}
```

#### Two types of Polymorphism
- Static Polymorphism (resolved at compile time) can be implemented using ```function overloading``` which allows multiple functions to have the same name but differ in the number, type, or order of their parameters.

```cpp
void print(string str);
void print(int x);
```

- Dynamic Polymorphism (resolve at runtime) can ve implemented using ```function overriding``` which allows sub-classes to implement parent function with different implementation;

```csharp
class Parent{
    void virtual DoSomething(){ // Virtual keyword to annotate that this function can be overriden
        System.Console.Writeline("Hello from parent");
    }
}
```
```csharp
class Child : Parent{
    void override DoSomething(){
        System.Console.Writeline("Hello from child");
    }

}
```











