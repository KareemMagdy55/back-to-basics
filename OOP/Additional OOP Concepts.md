## Additional OOP Concepts
In this section, we will explore concepts that were introduced later in OOP, such as **association, aggregation, and composition**, which describe various types of relationships between objects.

#### Relationships types
- **One to one:** One object is associated with exactly one other object.
- **One to many:** One object is associated with many objects.
- **Many to many:** Many objects are associated with many other objects.

---
### Association
An association is a "using" relationship between two or more objects, where each object has its own independent lifecycle and no object owns the other.

For example a "Teacher" and a "Student" can have an association since a teacher can teach many students, and a student can learn from many teachers, but neither owns the other.

```csharp
class Teacher{
    Student[] stuents; // 0 or more student
    // ... rest of logic
}
class Student{
    Teacher[] teachers; // 0 or more teachers
    // ... rest of logic
}
```
> Note that : Association can be one-way (teachers have students only) or two-way (teachers and students have each other).

---
### Aggregation
Aggregation is a special form of association that represents a "whole-part" relationship, where one object (the whole) contains or is composed of other objects (the parts).

For example "Library" (the whole), and "Books" (The part), so library **aggeragates** books, and books can exist without a library.
```csharp
class Library{
    Book[] Books; // 0 or more student
    // ... rest of logic
}
```
---
### Composition
Composition is a form of association where the child’s lifecycle is dependent on the parent’s lifecycle.

For example, consider "Cars" and "CarEngine", "CarEngine" cannot exist independently without a "Car".
```csharp
class Car{
  private CarEngine _Engine; 
}
```
