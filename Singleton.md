# C#
A singleton may be created in C# using the following example:
```c#
public sealed class Singleton
{
    private static Singleton instance = null;

    private Singleton() { }

    public static Singleton Instance
    {
        get
        {
            if (instance == null)
            {
                instance = new Singleton();
            }
            return instance;
        }
    }
}
```
In this example, only one instance of the singleton will be created and returned.  However, this pattern is not thread-safe.  Two threads could create a new singleton simultaneously, thus violating the only rule of a singleton, "single-ness."  Therefore, it is not recommended to use the above pattern.  Next, we will look at how to create a singleton that is thread-safe:
```c#
public sealed class Singleton
{
    private static Singleton instance = null;
    private static readonly object padlock = new object();

    Singleton() { }

    public static Singleton Instance
    {
        get
        {
            lock (padlock)
            {
                if (instance == null)
                {
                    instance = new Singleton();
                }
                return instance;
            }
        }
    }
}
```
Unlike the previous pattern, this pattern is thread-safe because of its use of a thread-safe locking mechanism.  This prevents two threads from creating separate instances of the singleton.  This pattern is fine to use in situations where lazy instantiation is not required.  Next, we will look at how to create a singleton that is lazy:
```c#
public sealed class Singleton
{
    private static readonly Lazy<Singleton> lazy = new Lazy<Singleton>(() => new Singleton());
    
    public static Singleton Instance { get { return lazy.Value; } }

    private Singleton() { }
}
```
In this example, we use the Lazy type.  We pass a delegate to the constructor which calls singleton's constructor using a lambda expression.  The Lazy type is inherently thread-safe and lazily instantiates objects.  Upon a call to get the Instance, the singleton is intantiated and returned.  This ensures a lazy and thread-safe singleton.  This is the simplest and most recommended pattern to use for singletons in C#.

# Ruby
Creating a singleton with Ruby is very simple as ruby contains a module in its standard library that does the work for you:
```ruby
require 'singleton'

class Thing
  include Singleton
end
```
In this example, we create a class, Thing, that will return the sole instance of Thing.  For example, an instance method could be accessed by calling "Thing.instance.method".  This is a thread-safe pattern for singletons in Ruby.  Without the use of the singleton module in the standard library, you would create a singleton as following:
```ruby
class Thing
  private_class_method :new
  @@instance = new
  def Thing.instance
    @@instance
  end
end
```
In this example, we create a singleton without use of the singleton module in the standard library.  To create a lazily instantiated singleton, we would do the following:
```ruby
class Aardvark
  private_class_method :new
  def Thing.instance
    @@instance = new unless @@instance
    @@instance
  end
end
```
In this example, we create a singleton that is lazily instantiated. The following demonstrates a module that will create a lazy, thread-safe singleton when implemented:
```ruby
module ThreadSafeSingleton
  def self.append_features(clazz)
    require 'thread'
    clazz.module_eval { 
      private_class_method :new
      @instance_mutex = Mutex.new
      def self.instance 
        @instance_mutex.synchronize {
          @instance = new unless @instance
          @instance
        }
      end
    }
  end
end

class ThreadSafeSingletonClass
  include ThreadSafeSingleton
end
```
In this example, the ThreadSafeSingletonClass implements the module above, ThreadSafeSingleton.  In doing so, we have created a lazy, thread-safe singleton with Ruby.
