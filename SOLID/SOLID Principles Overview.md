### What the Heck is SOLID?
**SOLID** is an acronym representing five object-oriented design principles. These principles aim to improve software design by promoting **modularity, flexibility, and maintainability.**

---
### Single Responsibility Principle (SRP)
Single Responsibility Principle states that a class should have only one job or responsibility.

for example, here is a code that violates SRP
```csharp
class Report{
    void Generate(){}
    void Confirm(){}
    void Save(){}
}
```
here is the correct one that follows SRP :
```csharp
class ReportGenerator {
    void Generate() {
        // Logic to generate the report
    }
}
```
```csharp
class ReportConfirmation{
    void Confirm() {
        // Logic to confirm the report
    }
}
```
```csharp
class ReportSaver {
    void Save() {
        // Logic to save the report
    }
}
```
---
### Open/Closed Principle (OCP)
Open/Closed Principle Principle states that class should be open for extension but closed for modification.

for example, here is a code that violates OCP
```csharp
class CustomerMainPage{
    void GreetCustomer(Customer c){
        if (c.type == "premium")
            Console.Writeline("Hello Premium User.");
        else if (c.type == "regular")
            Console.Writeline("Hello Regular User.");
        else if (c.type == "free trial")
            Console.Writeline("Hello Free Trial User.");
    }
}
```
In the example above adding a new user type will force developer to modify existing if-else structure, here is the solution without modification exisiting code headache:
```csharp
interface ICustomerGreeter
{
    void Greet();
}
```
```csharp
class PremiumCustomerGreeter : ICustomerGreeter
{
    public void Greet() => Console.WriteLine("Hello Premium User.");
}
```
```csharp
class RegularCustomerGreeter : ICustomerGreeter
{
    public void Greet() => Console.WriteLine("Hello Regular User.");
}
```
```csharp
class FreeTrialCustomerGreeter : ICustomerGreeter
{
    public void Greet() => Console.WriteLine("Hello Free Trial User.");
}
```
```csharp
class CustomerMainPage
{
    public void GreetCustomer(ICustomerGreeter greeter)
    {
        greeter.Greet();
    }
}
```
In the code above adding a new customer type will not change existing code, you just need to add its ```Greater``` class and implement ```ICustomerGreeter``` interface.

---
### Liskov Substitution Principle (LSP)
Liskov Substitution Principle (LSP) states that a child class should work anywhere its parent class works, without corrupt program behaviour.

for example, here is a code that violates LSP
using System;

```csharp
class Parent
{
    public virtual int ReturnValue()
    {
        return 4000;
    }
}
```
```csharp
internal class Child : Parent
{
    public new int ReturnValue() // new keyword means creating a new one with the same name
    {
        return 8000;
    }
}
```
```csharp
class Program
{
    static void Main(string[] args)
    {
        Parent parent = new Child();
        
        // this line should fire Child's 'ReturnValue()' to apply LSP
        Console.WriteLine(parent.ReturnValue()); // Print 4000 
    }
}
```
#### Why the example above violates LSP?
Because ```Child``` cannot substitute ```Parent```, when statemnt ```csharp parent.ReturnValue()``` execute it sees first if child have an **overriden** ```ReturnValue()``` function, then it go back and execute the ```Parent```'s ```ReturnValue()```, so here ```Child``` does not substitute ```Parent``` it does not have its own ```ReturnValue()``` function and calls the ```Parent```'s one.

#### Solution
Replace ```new``` with ```override```.

---
### Interface Segregation Principle (ISP)
ISP states that clients (e.g. classes) should not be forced to depend upon interfaces that they do not use.
> Classes should only use the methods they need

for example, here is a code that violates ISP
```csharp
interface ICreature{
    void Fly();
    void Swim();
    ... other methods
}
```
```csharp
class Bird : ICreature{
    void Fly(){
        // fly logic
    }
    void Swim() {
        // Birds does not swim 
    }
}
```

Solution :
```csharp
interface IFlyingCreature{
    void Fly();
}
```
```csharp
interface ISwimmingCreature{
    void Swim();
}
```
```csharp
class Bird : IFlyingCreature{
    void Fly(){
        // fly logic
    }
}
```

---
### Dependency Inversion Principle (DIP)
DIP states that high-level modules should not depend on low-level modules, and both should depend on abstractions.

#### Concepts you need to know first : Coupling & Cohesion

- **Coupling**: The degree of dependency between modules.  
  - Loose coupling → Changes in one module rarely affect others (low dependency between modules).
  - Tightly coupling → Changes in one module may affect other (high depedency between modules).

- **Cohesion**: elements within a module work together to achieve a specific purpose,
  - High cohesion → elements work together to do specfic task
  - Low cohesion →  elements are loosely related and serve multiple purposes

- **Good design**: Loose coupling + High cohesion.


> DIP keep your modules Loose coupled

for examples, here is violation of DIP :

```csharp
Class RegularMan{
    public virtual void SayHello(){
        Console.Writeline("Hello from a regular man who works from 8 to 5");
    }
}
```
```csharp
Class SuperMan : RegularMan{
    public override void SayHello(){
        Console.Writeline("Hello from a superman who saves regular man who works from 8 to 5");
    }
}
```

Solution : 
```csharp
inteface IHuman{
    void SayHello()
}
```
```csharp
Class RegularMan : IHuman{
    public void SayHello(){
        Console.Writeline("Hello from a regular man who works from 8 to 5");
    }
}
```
```csharp
Class SuperMan : IHuman{
    public void SayHello(){
        Console.Writeline("Hello from a superman who saves regular man who works from 8 to 5");
    }
}
```



