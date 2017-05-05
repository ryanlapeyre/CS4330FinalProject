# C#
Since C# was originally based upon Java, the way it achieves inheritance is extremely similar. A key difference is that although C# implements structs as another data type similar to classes, they do not support inheritance (although they do support interfaces). To overwrite a method in C#, the parent class has to have its method clarified with the keyword "virtual."You cannot overwrite a method in C# that does not have the "virtual" keyword attached to it. C# does support overloading methods as well, just like Java. 

    public class Animal
    {
        public virtual void Greet() //virtual keyword in action
        {
           Console.WriteLine("Hello, I'm some sort of animal!");
        }
    }

    public class Dog : Animal //instead of using the keyword extends, we use a colon to denote inheritance
    {
        public override void Greet() //this would not be possible without the virtual keyword in the parent class
        {
            Console.WriteLine("Hello, I'm a dog!");
        }
    }




# Ruby 
Inheritance works in the traditional sense as other programming languages. Ruby supports single inheritance, as well as overriding methods. Since Ruby is a dynamically typed language, it doesn't make sense to support overloading of methods. Other than that, Ruby is pretty traditional when it comes to inheritance. 

    class Animal
     def speak
      "Hello!"
     end
    end

     class GoodDog < Animal //GoodDog is inheriting from the animal class via this syntax, a "<" / less than sign
      def speak
        super + " from GoodDog class" //notice the call to the parent class with the super reserved word
      end
    end

    sparky = GoodDog.new
    sparky.speak 
