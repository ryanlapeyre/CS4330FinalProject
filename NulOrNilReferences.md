# C#
- C# uses the "null" keyword
- Attempting to use a null variable generates a compiler error
- Method calls on null variables raise runtime Null Reference Exceptions
- Objects can be garbage collected once they are declared null
- Value types (primitive types) cannot be declared null; nullable value types must be used instead:

    int? i = null;

# Ruby
- Ruby uses the "nil" keyword
- Ruby provides the safe navigation operator:

    obj&.foo # method foo is called on object obj; if obj is nil, then foo will not be executed and the return value of the expression is nil
