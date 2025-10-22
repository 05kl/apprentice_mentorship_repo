**Abstraction vs. Encapsulation – What exactly is the difference?**
 
Encapsulation is the practice of bundling data and the methods that operate on that data into a single unit, and restricting direct access to the data through access modifiers.
 
Abstraction is the practice of exposing only the essential features of an object while hiding the implementation details behind a simpler interface.
 
Basically: Encapsulation is about hiding the internal state and controlling access to it, while Abstraction is about hiding the implementation details and showing only what’s necessary.
 
 
**I know that encapsulation hides attributes and methods using access modifiers, and abstraction hides implementation details — but how exactly is that achieved?**
 
Both of them are able to be achieved when using classes. Encapsulation is achieved by using the `private` or similar access modifiers in a class, and abstraction can be achieved by defining `abstract` classes with `abstract` methods that are defined by the derived classes.
 
 
**Inheritance – Is multiple inheritance allowed in C#?**
 
No, multiple inheritance is not allowed in C#.
 
 
**Polymorphism – Could you show a small code snippet where we can see both method overriding and method overloading?**
 
```csharp
 
class overridable
}
    public virtual void virtualmeth(){}
 
    public void Method(){
        // first method
    }
    public void Method(string s){
        // second method (overloading)
    }
}
 
class overriding : overridable
{
    public override void virtualmeth(){
        // overriding virtual method
    }
}
 
 
```
 
 
**Recursion – When using recursive functions, where are variables stored? What exactly happens in memory during recursion?**
 
Each time a recursive function is called, new storage is allocated for the variables in the stack so that their values are not overwritten. In the Stack memory, all variables are saved. If the recursion is not controlled this can lead to having a size that is too big for the stack and then the program will crash as it cant use more memory than what is available.
 
**Anonymous Classes – Have you heard about them? What happens if we create code like this:**
**(check branch anonymous-classes-example)**
 
Anonymous classes are used to create a public read-only class without having to define a class first. In the code example a anonymous class named "anonymousSquare" is created using the new keyword and curly brackets. The two Square objects are compared with == and return true, and the same is done to the anonymousSquares, this time returning false. this happens because the square object overloads == and makes it compare the two squares, while the anonymous class doesnt have that and just compares it by reference which returns false.
 
**Hashing vs. Encryption – What’s the difference between them?**
 
Hashing is a one way operation. There is no way of returning the data back after hasing. It is used to check if a value is the same as the hashed value. In encryption there is a way of getting the data back after encryption. This means that encryption is used to transfer data securely.
 
 
**Garbage Collection – Can developers trigger the garbage collector manually? Also, what is the purpose of IDisposable?**
 
Yes, developers can trigger the garbage collector using the System.GC class with the GC.Collect() command.
The purpose of IDisposable is to release unmanaged resources (resources not managed by the garbage collector) such as acessing files & networks, talking with the os, etc. It is used to close SQL connections when an exception happens because otherwise it would stay open and use up server resources.
 
 
**Aggregation vs. Composition – Could you provide a code example using a House and Room class to show both relationships?**
 
 
```csharp
class Room
{
}
 
class Address{}
 
class House
{
    // composition
    private Room room = new Room();
 
    // aggregation
    private Address address;
 
    public House(Address address)
    {
        this.address = address;
    }
}
```
 
## Feedback
 
Abstraction vs. Encapsulation – Excellent explanation. You correctly pointed out that encapsulation is achieved through access modifiers, while abstraction is implemented via abstract classes and interfaces. 
 
encapsulation restricts access to certain parts of a class, whereas abstraction hides the implementation details and exposes only what’s necessary for the user to interact with to get result.
 
Inheritance – Correct! 
C# does not allow multiple inheritance for classes, but we can simulate it using interfaces, since they can be chained together.
 
Polymorphism – Nicely done.
 
Recursion – Very detailed explanation. You correctly described that each recursive call creates a stack frame containing variables and a pointer to the previous frame.
 
Garbage Collection – Great
 
Aggregation vs. Composition – The example with the House and Room classes was really well done.
