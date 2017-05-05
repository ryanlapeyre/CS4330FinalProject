# C#
Much like Java, C# has intefaces. An interface is a list of methods that a class must implement in Java, which is almost the same as it is in C#. A key difference is that interfaces can also apply to structs in C#, which cannot be done in Java as structs do not exist in that language. To use an interface, you first must initialize it as an interface, and give it a inteface name along with the data type that it takes in. Within that interface, you then define the interface you wish the class/struct to implement. You use the ":" and the name of the data type parameter it takes in, should it need one.

    interface IEquatable<T>
    {
        bool Equals(T obj);
    }

    public class Car : IEquatable<Car> //replace class with struct for the struct version
    {
        public string Make {get; set;}
        public string Model { get; set; }
        public string Year { get; set; }

        // Implementation of IEquatable<T> interface
        public bool Equals(Car car)
        {
            if (this.Make == car.Make &&
                this.Model == car.Model &&
                this.Year == car.Year)
            {
                return true;
            }
            else
                return false;
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
