# C#
In C#, ```Equals``` and ```==``` both compare by reference by default.  They can be overridden to compare by value.  ```ReferenceEquals``` will always compare by reference.  ```==``` is overridden for the String type to compare by value.  

# Ruby
Ruby's Object class has three methods, ```equals```, ```eql```, and ```==```.  By default, each of these methods compares by reference by default.  Any of these methods can be overrridden to have different behavior.  By convention, the ```equals``` method is usually left alone and the other two methods are overridden to compare by value or some other criteria.  ```==``` and ```eql``` are overridden on strings in Ruby to compare by value.  In addition, an operator known as the spaceship operator, ```<==>``` can be used to compare strings in Ruby as well.  This operator returns 0 if the two strings are the same, -1 if the left string is less than the right string, and 1 if the left string is greater than the right string.
