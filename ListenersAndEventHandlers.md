# C#
In my search for information about event handlers in C#, I stumbled upon the following answer on Stack Overflow:

>To understand event handlers, you need to understand delegates. In C#, you can think of a delegate as a pointer (or a reference) to a >method. This is useful because the pointer can be passed around as a value.
>
>The central concept of a delegate is its signature, or shape. That is (1) the return type and (2) the input arguments. For example, if >we create a delegate void MyDelegate(object sender, EventArgs e), it can only point to methods which return void, and take an object >and EventArgs. Kind of like a square hole and a square peg. So we say these methods have the same signature, or shape, as the delegate.
>
>So knowing how to create a reference to a method, let's think about the purpose of events: we want to cause some code to be executed >when something happens elsewhere in the system - or "handle the event". To do this, we create specific methods for the code we want to >be executed. The glue between the event and the methods to be executed are the delegates. The event must internally store a "list" of >pointers to the methods to call when the event is raised.* Of course, to be able to call a method, we need to know what arguments to >pass to it! We use the delegate as the "contract" between the event and all the specific methods that will be called.
>
>So the default EventHandler (and many like it) represents a specific shape of method (again, void/object-EventArgs). When you declare >an event, you are saying which shape of method (EventHandler) that event will invoke, by specifying a delegate:
>```c#
>//This delegate can be used to point to methods
>//which return void and take a string.
>public delegate void MyEventHandler(string foo);
>
>//This event can cause any method which conforms
>//to MyEventHandler to be called.
>public event MyEventHandler SomethingHappened;
>
>//Here is some code I want to be executed
>//when SomethingHappened fires.
>void HandleSomethingHappened(string foo)
>{
>    //Do some stuff
>}
>
>//I am creating a delegate (pointer) to HandleSomethingHappened
>//and adding it to SomethingHappened's list of "Event Handlers".
>myObj.SomethingHappened += new MyEventHandler(HandleSomethingHappened);
>```
>(*This is the key to events in .NET and peels away the "magic" - an event is really, under the covers, just a list of methods of the >same "shape". The list is stored where the event lives. When the event is "raised", it's really just "go through this list of methods >and call each one, using these values as the parameters". Assigning an event handler is just a prettier, easier way of adding your >method to this list of methods to be called).

http://stackoverflow.com/a/803320

This approach could also be simplified using lambda expressions:
```c#
myObj.SomethingHappened += (s) => 
{
  // Do some stuff
}
```

# Ruby
Ruby does not natively support event handlers, so there are many ways to go about implementing them.  The simplest of which is to implement the observable module included in Ruby's standard library.  
```ruby
require "observer"

class Observed
  include Observable

  def run
    for i in (0..10)
      notify_observers(i)
    end
  end
end

class Observer
  def initialize(thing)
    thing.add_observer(self)
  end

  def update(num)
    if num > 5
      print num
    end
  end
end

observed = Observed.new()
observer = Observer.new(observed)
observed.run
```
This example would output:
> 6, 7, 8, 9, 10
