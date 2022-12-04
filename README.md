# How To Name Classes, Variables, and Functions
## Naming Standard
- Camel Case?
- Pascal Case?
- Lower Case with Underscores?
		
		It doesn’t matter
		Have a Standard
		Be Consistent
## Naming convention:
	
1. Use long descriptive and intention revealing names that are easy to read.
		
		# Not recommended
		# The au variable is the number of active users
		au = 105

		# Recommended 
		total_active_users = 105
2. Avoid using ambiguous shorthand. 
- A variable should have a long descriptive name than a short confusing name.
		
		# Not recommended
		fn = 'John'
		Ln = ‘Doe’
		cre_tmstp = 1621535852

		# Recommended
		first_name = ‘JOhn’
		Las_name = ‘Doe’
		creation_timestamp = 1621535852
3. Don’t use magic numbers.
- Magic numbers are numbers with special, hardcoded semantics that appear in code but do not have any meaning or explanation. Usually, these numbers appear as literals in more than one location in our code.
		
		import random

		# Not recommended
		def roll_dice():
			return random.randint(0, 4)  # what is 4 supposed to represent?

		# Recommended
		DICE_SIDES = 4

		def roll_dice():
			return random.randint(0, DICE_SIDES)
		
### Functions
4. Be consistent with your function naming convention.
- As seen with variables above, stick to a naming convention when naming functions. Using different naming conventions would confuse other developers.

		# Not recommended
		def get_users(): 
			# do something
			pass

		def fetch_user(id): 
			# do something
			pass

		def retrieve_posts(): 
			# do something
			pass

		def fetch_post(id):
			# do something
			pass

		# Recommended
		def fetch_users(): 
			# do something
			pass

		def fetch_user(id): 
			# do something
			pass

		def fetch_posts(): 
			# do something
			pass

		def fetch_post(id):
			# do something
			pass
5. Functions should do one thing and do it well. 
- Write short and simple functions that perform a single task. A good rule of thumb to note is that if your function name contains “and” you may need to split it into two functions.

		# Not recommended
		def fetch_and_display_users():
			users = [] # result from some api call

			for user in users:
				print(user)


		# Recommended
		def fetch_usersl():
			users = [] # result from some api call
			return users

		def display_users(users):
			for user in users:
				print(user)
### Classes
6. Do not add redundant context

		# Not recommended
		class Person:
			def __init__(self, person_username, person_email, person_phone, person_address):
				self.person_username = person_username
				self.person_email = person_email
				self.person_phone = person_phone
				self.person_address = person_address

		# Recommended
		class Person:
			def __init__(self, username, email, phone, address):

				self.username = username
				self.email = email
				self.phone = phone
				self.address = address
# How to Use Code Comments
## Comments rules
- Always try to explain yourself in code.
- Don't be redundant.
- Don't add obvious noise.
		
		numbers = [1, 2, 3, 4, 5]

		# This variable stores the average of list of numbers.
		average = sum(numbers) / len(numbers)
		print(average)
- Don't use closing brace comments.
- Use as explanation of intent.
- Use as clarification of code.
- Use as warning of consequences.
- Don't comment out code. Just remove.

		The worst thing you can do is to leave code commented out in your programs. All the debug code or debug messages should be removed before pushing to a version control system, otherwise, your colleagues will be scared of deleting it and your commented code will stay there forever.

