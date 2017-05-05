# C# 
Exception handling in C# is similar to how it is handled in Java. There are three keywords to be aware of, which are "try," "catch," and "finally" keywords. The "try" keyword is to be used when you think there will be an exception raised by the code. Note that after a "try" block, you need either a "finally" block, some "catch" blocks, or both. The "finally" block is a chunk of code that will be executed after the code is examined through the "catch" blocks. "Catch" blocks are used to catch specific errors, and to handle those with the correct protocols. 


    try
    {
        // Code to try for an exception goes here.
    }
    catch (SomeSpecificException ex) //specify what exception will occur. 
    {
        // Code goes here to handle the exception that will be raised.
    }
    catch (SomeOtherSpecificException ex) //specify what other exception will occur. 
    {
        // Code goes here to handle the exception that will be raised.
    }
    finally
    {
        // Code to execute after the try (and possibly catch) blocks 
        // goes here.
    }
    

# Ruby
Compared to C#, Ruby handles errors and exception handling a bit differently.  The three keywods to be aware of are "rescue" , "ensure" , and "begin." The "begin" keyword is similar to the "try" keyword in C#, "rescue" is similar to "catch", and "ensure" is akin to "finally." "Begin" is where to start the code that is likely to cause an error. The "rescue" block takes in the error to check for, as well as what block of code to excecute when that error happens. Finally, the "ensure" code is to be used for code that will execute at the end of the "rescue" blocks. Just like in C#, you can have just one "ensure" block, or multiple "rescue" blocks, or both. A new keyword available to Ruby is the "retry" keyword, which will recheck any "rescue" instance. You can then check for the number of "retries" and then have the code continuing its usual error checking should that number raise to a certain amount. 

    //program reads in articles on Wikipedia on each year from 1900 to 2000. 
    require 'open-uri'
    require 'timeout'

    remote_base_url = "http://en.wikipedia.org/wiki"

    start_year = 1900
    end_year = 2000

    (start_year..end_year).each do |yr|
     begin //start the code that will cause an error
       rpage = open("#{remote_base_url}/#{yr}")
     rescue StandardError=>e //specify the error type to check for and give it a parameter. 
                             // If none is specified, all error checks will occur.
       puts "Error: #{e}"
     else
       rdata = rpage.read
     ensure //code to be executed no matter what. 
       puts "sleeping"
       sleep 5
     end

     if rdata
       File.open("copy-of-#{yr}.html", "w"){|f| f.write(rdata) }
     end
    end   
    
    
    
    
