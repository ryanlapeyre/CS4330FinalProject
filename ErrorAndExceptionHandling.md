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
