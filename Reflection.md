# C#
- Use reflection to get information about assemblies, modules, and types
- Reflection can also be used to dynamically create instances of types, invoke methods, or access fields and properties

```
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type); // System.Int32
```

# Ruby
- Ruby also provides reflection facilities (called "introspection")

```
obj.methods
obj.instance_variables
obj.class_variables
```
