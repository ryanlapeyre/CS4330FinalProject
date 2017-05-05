# C#
* C# DOES have unary operators. While this is not a unique feature of C#, it does put it in a contrasting light to Ruby, which does not have them.

       x = 0
       x++
       //x is now 1
* C# supports both explicit and implicit typing. While most languages tend to favor one or another, C# allows the user to use the "var" keyword and allow the compiler to determine what type to evaluate the variable as. Swift does this as well, which shows the industry moving to flexible typing when it can be used. Functions and methods still require strongly type parameters in C#. 

      var i = 10; // implicitly typed  
      int i = 10; //explicitly typed 

* Methods follow PascalCasing in C#. A lot of other languages follow CamelCasing for their methods, whereas C# follow its casing from the Pascal language (as shown in the example). 

        static void Main()
        {
            TestMotorcycle moto = new TestMotorcycle();
            moto.StartEngine();
            moto.AddGas(15);
            moto.Drive(5, 20);
            double speed = moto.GetTopSpeed();
            Console.WriteLine("My top speed is {0}", speed);            
        }

* LINQ is a way to add query expressions to C#. This allows programs in C# to stores the results from a query in a database and relate that data back, or modify and express it in different ways. 

       using (ServiceContext svcContext = new ServiceContext(_serviceProxy)) //connection to database
       {
       var query_where1 = from a in svcContext.AccountSet //queried instruction and storing it in a "var" variable.
                    where a.Name.Contains("Contoso")
                    select a;
       foreach (var a in query_where1) //we can now easily cycle through and print the results.
         {
            System.Console.WriteLine(a.Name + " " + a.Address1_City);
         }
       }




# Ruby
* Everything is an object in Ruby, including primitive numbers. Here's a quick example of a number using a method.
      
      5.times { print "Hello World" }
* Code Blocks
Blocks are a way to pass a chunk of code to a method. Using this, you can easily define program logic for an object inline!

      //printing out all elements in an array 
      sample_array.each { |element| print element } 
      //the pipes define the variables given to the code block.

* The only values that evaluate to false in Ruby are false and nil. It does not in Ruby, as the example below shows.
     
        if (0) then //will print Hello World
          print "Hello World"
        end
* Implicit return is also a unique feature of Ruby. Instead of explicity saying what a method returns, Ruby will automatically return the last expression in a method. 
   
      def testMethod
       x = 4+4 //x will be returned even though it is not explicity stated. 
      end

