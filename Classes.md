# C#

# Ruby 
An example of a class in the Ruby language would be as follows. We'll dissect the code and go over Ruby's various class syntax.

    class Account
	    attr_reader :name
	    attr_reader :balance

	def initialize(name , balance = 100)
		@name = name
		@balance = balance
	end

	private
	def pin
		@pin = 1234
		return @pin
	end

	private
	def pin_error
		return "Access denied: incorrect PIN."
	end

	public
	def display_balance(pin_number)
		if pin_number == pin
			puts "Balance: $#{@balance}."

		else
			pin_error
		end

	end

	public
	def withdraw(pin_number , amount)
		if pin_number == pin
			@balance -= amount
			puts "Withdraw $#{amount}. New balance: $#{@balance}"
		else
			puts pin_error
		end
	end
    end
    
    checking_account = Account.new("Ryan" , 20)

<pre>
	In Ruby, we define a class by using the reserved word "class" followed by the namescheme you wish, and then Ruby's reserved word "end", when you're finished. To create a new instance of a class, like the example at the bottom we have, is to just call the class and use the "new" method to initialize it. Make sure to give it a variable to initialize to on the left hand side! Static variables in Ruby are defined with the "@@" and are outside of the methods (denoted by the "public/private" reserved words as well as the "def" word when choosing to define a method). An instance variable is marked by an "@" symbol, while a static variable has "@@" in front of it. The "attr_reader" and "attr_writer" are ruby shortcuts for getting and settings variables, instead of making the methods for it. Garbage collection is handled by Ruby, so there is no method to destroy an instantiated class.
</pre>
