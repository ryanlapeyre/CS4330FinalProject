# C#
In C#, to refer to the instance of your object you use the 'this' keyword.  For example:
```c#
public class Employee
{
  public Employee(string name, string alias)
  {
      // Use this to qualify the fields, name and alias:
      this.name = name;
      this.alias = alias;
  }
}
```
In the above example, this is used to qualify the fields name and alias because they are hidden by the names of the parameters passed into the constructor.

# Ruby
In Ruby, to refer to the instance of your object you use the 'self' keyword.  For example:
```ruby
class Thing
  def self.run
    for i in (0..10)
      print i
    end
  end
end

thing = Thing.new
thing.run
```
In the above example, the run method is defined with self in front of it.  This is declaring run as an instance method.  Without using self when defining the method, run would be a class method.  This would allow you to call the method on the class without instantiating an object:
```ruby
Thing.run
```
In the above example, run is being called directly on the Thing class and not on an instance of the thing class.
