# C#



# Ruby 
Inheritance works in the traditional sense as other programming languages. Ruby supports single inheritance, as well as overriding methods. Since Ruby is a dynamically typed language, it doesn't make sense to support overloading of methods. Other than that, Ruby is pretty traditional when it comes to inheritance. 

    class Animal
     def speak
      "Hello!"
     end
    end

     class GoodDog < Animal //GoodDog is inheriting from the animal class via this syntax
      def speak
        super + " from GoodDog class" //notice the call to the parent class with the super reserved word
      end
    end

    sparky = GoodDog.new
    sparky.speak 
