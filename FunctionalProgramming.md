# C#
#### LINQ - Language Integrated Query
* LINQ provides C# with functional programming facilities such as list comprehensions, filtering lists, mapping functions to list, right and left folds, and more.

##### Example: Aggregate (left fold)
Applies an accumulator function over a sequence

    double product = doubles.Aggregate(1.0, (prod, next) => prod * next);
    
##### Example: Filtering
    var queryLondonCustomers = from cust in customers
                                         where cust.City == "London"
                                         select cust;
Note that C#'s LINQ borrows naming and syntax conventions heavily from SQL, as you can see in the code example above. Compare the syntax to functional Java, for example:

    String dale = strings.stream().filter(string -> string.startsWith("d")).findFirst();
This resembles most other functional languages a lot more closely.

<hr/>

#### Closures
C# uses the "fat arrow" syntax to represent lambdas:
    Func<string, string> myFunc = var1 => "some value";
    
#### Higher order functions
C# provides support for higher order functions, that is, functions can return other functions receive them as parameters.

    List<b> map<a>(Func<a, b> f, List<a> list) {
      foreach (a x in list) {
        yield return f(x);
      }
    }

# Ruby 
#### Higher order functions
    def adder(a, b)
        lambda { a + b }
    end
    adder_fn = adder(1, 2)
    adder_fn.call
    
    (5..10).reduce(:+)
    (5..10).inject { |sum, n| sum + n }
    (5..10).reduce(1, :*)
    (5..10).inject(1) { |product, n| product * n }
#### Currying
Ruby provides support for currying, which is the technique of translating the evaluation of a function that takes multiple arguments into evaluating a sequence of functions, each with a single argument.

    apply_math = lambda do |fn, a, b|
        a.send(fn, b)
    end
    add = apply_math.curry.(:+)
