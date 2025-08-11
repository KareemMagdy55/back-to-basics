### What the Heck is SOLID?
**SOLID** is an acronym representing five object-oriented design principles. These principles aim to improve software design by promoting modularity, flexibility, and maintainability.

---
### Single Responsibility Principle (SRP)
Single Responsibility Principle states that a class should have only one job or responsibility.
SRP help in reduce code compleixity and enhance maintainability, and class reusability.

for examples, here is a code that violates SRP
```csharp
class Report{
    void generate(){}
    void confirm(){}
    void save(){}
}
```
here is the correct one that follows SRP :
```csharp
class ReportGenerator {
    void generate() {
        // Logic to generate the report
    }
}
```
```csharp
class ReportConfirmation{
    void confirm() {
        // Logic to confirm the report
    }
}
```
```csharp
class ReportSaver {
    void save() {
        // Logic to save the report
    }
}
```
---
### Open/Closed Principle (OCP)
Open/Closed Principle Principle states that class should be open for extension but closed for modification.





