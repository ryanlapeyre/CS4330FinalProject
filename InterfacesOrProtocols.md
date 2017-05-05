
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
