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
OOP introduced the idea of thinking about programs as collections of objects. These objects have both attributes (characteristics) and methods (behaviors).

The keyword ```class``` as a blueprint for defining the structure of objects, including their attributes and methods.
```csharp

class Customer{
    // attributes (characteristics) 
    int age;
    int Balance;
    bool hasPremiumAccount; 

    // methods (behaviors)
    void Purchase(Product product){
        // Purchase logic...
    }
}

```
---
## 3. OOP concepts
Object-Oriented Programming (OOP) is built on four main concepts: encapsulation, abstraction, inheritance, and polymorphism. Additional concepts like association, aggregation, and composition were introduced later. This section will focus on the four core principles.

---
### Encapsulation
Encapsulation is about combine attributes and functions in one single unit (class).

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
```note that : Prefixing private fields with an underscore (_b) is a common naming convention for private attributes```




