# C#
#### LINQ - Language Integrated Query
* LINQ provides C# with functional programming facilities such as list comprehensions, filtering lists, mapping functions to list, right and left folds, and more

##### Example: Aggregate (left fold)
###### Applies an accumulator function over a sequence
    double product = doubles.Aggregate(1.0, (prod, next) => prod * next);
    
##### Example: Filtering
    var queryLondonCustomers = from cust in customers
                                         where cust.City == "London"
                                         select cust;
Note that C#'s LINQ borrows naming and syntax conventions heavily from SQL, as you can see in the code example above. Compare the syntax to functional Java, for example:

    String dale = strings.stream().filter(string -> string.startsWith("d").findFirst());
This resembles most other functional languages a lot more closely.

<hr/>

#### Closures
###### C# uses the "fat arrow" syntax to represent lambdas:
    Func<string, string> myFunc = var1 => "some value";

# Ruby
