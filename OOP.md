## Programming Paradigms: An Overview
Before diving into Object-Oriented Programming (OOP) concepts, it's important to understand the broader umbrella under which OOP falls. That umbrella is called Programming Paradigms.

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

// Output the result
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
