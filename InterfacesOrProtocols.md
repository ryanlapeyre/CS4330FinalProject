# C#
Much like Java, C# has intefaces. An interface is a list of methods that a class must implement in Java, which is almost the same as it is in C#, with no limits to how many can be applied to a class. A key difference is that interfaces can also apply to structs in C#, which cannot be done in Java as structs do not exist in that language. You first must initialize as an interface, and give it a interface name along with the data type that it takes in. Within that interface, you then list the methods you wish the class/struct to implement. You use the ":" after the class/struct name and list interface name along with the name of the data type parameter it takes in, should it need one. Within your class/struct, you then implement the method as it is in the interface the class/struct is implementing, witht the proper return type, name, and input type.

    interface PrintIt
    {
        void PrintText();
    }

    public class Car : PrintIt//replace class with struct for the struct version
    {
        public string Make {get; set;}
        public string Model { get; set; }
        public string Year { get; set; }

        // Implementation of PrintIt interface
        public void PrintText()
        {
            Console.WriteLine("This is text");   
        }
    }



# Ruby
There are no interfaces/protocols in Ruby. However, you can make rough substitue of them by declaring a module and having that module raise exceptions when it is not implemented. 

    module CSV

    def to_csv
      raise "Not implemented"
    end

      def from_csv(line)
        raise "Not implemented"
      end

    end

Then we have to implement the methods in that module for it to "act" as an interface/protocol, or else exceptions will occur.

    class User
     include CSV

     def to_csv
       "#{@name},#{@age}"
     end

     def from_csv(line)
       parts = line.split(",")

       @name = parts[0]
       @age = parts[1]
     end
    end
