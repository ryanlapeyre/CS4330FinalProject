# C#







# Ruby
Ruby does not explicity call its namespaces "namespaces" such as in C#. However, it does implement them via modules. A module contains a group of methods for which you can call using the proper syntax. Modules in Ruby achieve this, as seen in the sample below. To implement a module in your program, you use the keyword "require" along with that module's name in quotes.


    module Trig //defining our "namespace" AKA module
      PI = 3.141592654
       def Trig.sin(x)  //defining our methods 
       # ..
       end
       def Trig.cos(x)
       # ..
      end 
    end
        
    require "trig"
     y = Trig.sin(Trig::PI/4) //using the sin method encapsulated in the Trig module 
