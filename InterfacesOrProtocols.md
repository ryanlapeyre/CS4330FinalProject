
# Ruby
There are no interfaces in Ruby. However, you can make rough substitue of them by declaring a module and having that module raise exceptions when it is not implemented. 

    module CSV

    def to_csv
      raise "Not implemented"
    end

      def from_csv(line)
        raise "Not implemented"
      end

    end

Then we have to implement that module in code for it to "act" as an interface, or else exceptions will occur.

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
