# C#
C# is an object-oriented language.  As such, C# contains object-oriented principles such as polymorphism, encapsulation, abstraction, and inheritance.  Because of this, programming in C# can utilize these principles to help organize and structure code.  It is possible for large portions of code, especially a console application, to be written procedurally.  The code may appear procedrual in appearance, but behind the scenes the code is actually object-oriented.  For example, even primitive data types (double, int, float, etc.) are objects in C#.  The following is an example of procedural-looking code in C#: 
```c#
public class Hello
{
   public static void Main()
   {
      System.Console.WriteLine("Hello, World!");
   }
}
```
In this example, the Main method can be thought of as the point of execution.  Each method following would be procedurally executed to return a result.  However, it is also obvious to see that C# is inherently object-oriented and cannot be solely procedural.  For example, the main method must be contained inside of the Hello class.  Main must also be a static method on the Hello class, which, once again, ties back to object-oriented concepts.  

# Ruby
Unlike C#, Ruby natively supports procedural programming.  Ruby is completely object-oriented.  When you write a procedural program in Ruby, the code actually belongs to a global object.  This supports the notion that object-oriented programming languages do support procedural programming; they just add more flexibility.  
```ruby
puts "Hello, World!"
```
In this example, we write a Hello World program in Ruby.  The user can write code in this way without creating classes or objects.  This code can be much more complex with additional functions.  This is how to write procedural code in Ruby.
