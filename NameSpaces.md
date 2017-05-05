# C#
Namespaces in C# are not renamed to module like they are in Ruby. Other than that, namespaces work the same way they do in C++. You define a namespace and the classes/methods within it by using the "namespaces" keyword. To use that namespace, you write the "using" keyword at the top of your program. Note that namespaces can include structs, interfaces, enums, delegates, and other namespaces as well.

     using System; // a list of namespaces we are going to use. We are going to define the bottom two.
     using first_space;
     using second_space;

    namespace first_space //defining the classes and methods within the first_space namespace
    {
        class abc
        {
            public void func()
            {
                Console.WriteLine("Inside first_space");
            }
        }   
    }

    namespace second_space
    {
       class efg
       {
          public void func()
          {
             Console.WriteLine("Inside second_space");
          }
       }
    }   

    class TestClass
    {
       static void Main(string[] args)
       {
          //if we were not explicity "using" the first_space while also defining it; 
          //the class implementation below would look like below:
          //first_space.namespace_cl fc = new first_space.namespace_cl();
          
          abc fc = new abc(); 
          efg sc = new efg();
          fc.func();
          sc.func();
          Console.ReadKey();
       }
    }






# Ruby
Ruby does not explicity call its namespaces "namespaces" such as in C#. However, it does implement them via modules. A module contains a group of methods for which you can call using the proper syntax. Modules in Ruby achieve this, as seen in the sample below. To implement a module in your program, you use the keyword "require" along with that module's name in quotes. You need the module name followed by the method name and parameter for it to take in when using a module. 


    module Trig //defining our "namespace" AKA module and defining its methods
      PI = 3.141592654
       def Trig.sin(x)  //defining our methods 
       # ..
       end
       def Trig.cos(x)
       # ..
      end 
    end
        
    require "trig" //using the module within a program. Allows us to access sin(x) and cos(x) methods.
     y = Trig.sin(Trig::PI/4) //using the sin method encapsulated in the Trig module 
