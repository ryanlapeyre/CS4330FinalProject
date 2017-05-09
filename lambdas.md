# C#
In C#, delegates are similar to function pointers.  This allows a reference to a method to be encapsulated in a delegate object and passed around with the delegate to do work.  This syntax can be simplified in many cases by using lambda expressions.  For example:
```c#
// anonymous delegate
var evens = Enumerable
                .Range(1, 100)
                .Where(delegate(int x) { return (x % 2) == 0; })
                .ToList();

// lambda expression
var evens = Enumerable
                .Range(1, 100)
                .Where(x => (x % 2) == 0)
                .ToList();
```
In the above example, you can see how using a delegate, we return only the even numbers by iterating through the Enumerable.  The same thing can be completed by using a lambda expression in place of the anonymous delegate.

# Ruby
In Ruby, procs and lambdas are very similar.  They are also similar in many ways to delegates and lambdas in C#.  Lambdas are actually proc objects in Ruby.  This is why they are so similar.  They can both be used to complete work anonymously.  For example:
```ruby
lam = lambda { |x| puts x }    # creates a lambda that takes 1 argument
proc = Proc.new { |x| puts x } # creates a proc that takes 1 argument
lam.call(2)
proc.call(2)    
```
In the above example, each of these will print '2'.  A lambda must be given the correct number of arguments. A proc will execute regardless of the number of arguments, leaving off extra arguments and returning null if there are too few arguments.  Each of these types also treats the return keyword differently.  For example:
```ruby
def lambda_test
  lam = lambda { return }
  lam.call
  puts "Hello world"
end

def proc_test
  proc = Proc.new { return }
  proc.call
  puts "Hello world"
end

lambda_test 
proc_test 
```
In the above example, the lambda will print "Hello world", and the proc will print nothing.
