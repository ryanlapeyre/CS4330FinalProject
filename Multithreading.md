# C#
- Threads are the basic unit of concurrency in C#
- Multitasking
- Thread pools

```
using System;
using System.Threading;

public class Alpha {
   public void Beta() {
      while (true) {
         Console.WriteLine("Alpha.Beta is running in its own thread.");
      }
   }
};

public class Theading {
   public static int Main() {
      Alpha oAlpha = new Alpha();
      Thread oThread = new Thread(new ThreadStart(oAlpha.Beta));
      oThread.Start();
      oThread.Abort();
      return 0;
   }
}
```

# Ruby
- Ruby has supported threads natively since version 1.9
- Ruby uses a Global Interpreter Lock, which aims to preserve data integrity by only allowing data to be modified by one thread at a time
  - Because of this, Ruby threads cannot corrupt data
  - However, Ruby threads are not truly concurrent
- Ruby also supports "fibers", which behave like miniature threads
  - Fibers can be paused and resumed from outside or from within themselves
  - Fibers are more lightweight than threads - that is, they are faster and use less memory

```
fiber = Fiber.new do
  Fiber.yield 1
  2
end

puts fiber.resume # 1
puts fiber.resume # 2
puts fiber.resume # FiberError: dead fiber called
```
