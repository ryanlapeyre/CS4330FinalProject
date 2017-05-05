# C#
Much like Java, C# has intefaces. An interface is a list of methods that a class must implement in Java, which is almost the same as it is in C#. A key difference is that interfaces can also apply to structs in C#, which cannot be done in Java as structs do not exists.





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
