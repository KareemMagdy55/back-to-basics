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




