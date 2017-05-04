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
