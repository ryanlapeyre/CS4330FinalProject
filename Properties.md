# C#
Properties in C# have built-in getters and setters.  You can define getters and setters for a property using the get and set keywords rather than writing methods for them.  This allows you to define computed properties using get and set and a backing variable. For example: 
```c#
private double seconds;

public double Hours
{
   get { return seconds / 3600; }
   set { seconds = value * 3600; }
}
```
In this example, seconds would be the backing variable and Hours is the computed property.  The logic for getting and setting Hours is defined in the get and set blocks rather than in separate methods.

# Ruby
Properties in Ruby do not have built-in getters and setters, at least not in the same sense as C#.  Getters and setters must be defined through other methods.  Similarly, computed properties can be defined through the use of backing variables and other methods.  For example: 
```ruby
class Customer
  def initialize
    @age = 18
  end

  def age
    @age
  end

  def age=(value)
    @age = value
  end
end
```
In the above example, age is defined as an instance variable within the class, Customer.  To access age outside of class, getter and setter methods must be defined as above.  Next we will look at how computed properties are done in ruby: 
```ruby
class Customer
  def initialize
    @first_name = "Claudio"
    @last_name = "Lassala"
  end

  def full_name
    "#{@first_name} #{@last_name}"
  end
end
```
In this example, two instance variables, first_name and last_name, are defined and initialized in the class, Customer.  A method is defined called full_name which contcatenates first_name and last_name and returns the result.  In this example, full_name is the computed property and first_name and last_name are the backing variables.
