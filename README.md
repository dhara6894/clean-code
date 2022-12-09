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
		
```python
# Not recommended
# The au variable is the number of active users
au = 105

# Recommended 
total_active_users = 105
		
# Not recommended
expired = True
		
# Recommended
is_expired = True
```

2. Avoid using ambiguous shorthand. 
- A variable should have a long descriptive name than a short confusing name.	
		
```python
# Not recommended
fn = 'John'
ln = 'Doe'
cre_tmstp = 1621535852

# Recommended
first_name = 'John'
last_name = 'Doe'
creation_timestamp = 1621535852
```

3. Don’t use magic numbers.
- Magic numbers are numbers with special, hardcoded semantics that appear in code but do not have any meaning or explanation. Usually, these numbers appear as literals in more than one location in our code.
		
```python
import random

# Not recommended
def roll_dice():
	return random.randint(0, 4)  # what is 4 supposed to represent?

# Recommended
DICE_SIDES = 4

def roll_dice():
	return random.randint(0, DICE_SIDES)
```

4. Avoid Double Negatives
- Let’s agree that a double negative is plain confusing.

```python
# Example to check if a user's membership is valid or not:

# Not recommended
is_invalid = False
if not is_invalid:
	print("User's membership is valid!")

# Recommended
is_valid = True
if not is_valid:
	print("User's membership is invalid!")
```

## Functions
1. Keep simple, small functions with descriptive names
- Split big functions into multiple, meaningful functions, and make the code more readable
- Don’t be afraid to make a name long. A long descriptive name is better than a short enigmatic name.

1. Be consistent with your function naming convention.
- As seen with variables above, stick to a naming convention when naming functions. Using different naming conventions would confuse other developers.

```python
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
```

3. Functions should do one thing and do it well. 
- Write short and simple functions that perform a single task. A good rule of thumb to note is that if your function name contains “and” you may need to split it into two functions.

```python
# Not recommended
def fetch_and_display_users():
	users = [] # result from some api call

	for user in users:
		print(user)


# Recommended
def fetch_user():
	users = [] # result from some api call
	return users

def display_users(users):
	for user in users:
		print(user)
```

4. Fewer arguments, better readability
## Classes
1. Do not add redundant context

```python
# Not recommended
class employee:
	employee_name = ' '
	employee_age = ' '

# Recommended
class employee:
	name = ' '
	age = ' '
```

# How to Use Code Comments
## Comments rules
- Always try to explain yourself in code.

```python
## student is eligible for blood donation
if student.age >= 17 and student.weight >= 58.0 and student.height >= 1.55:
	schedule_blood_donating_session_with(student)
```
- Don't be redundant.

```python
## if the student is at least 18 years of age
if student.age >= 18: 
	## send meeting invitation to the student 
	send_message_to(student, meeting_invitation)
else: ## if the student is younger than 18 years 
	## sends a meeting invitation to the student’s legal guardian 
	send_message_to(student.parent,meeting_invitation)
```

- Don't add obvious noise.
		
```python
i++ ## increment i

numbers = [1, 2, 3, 4, 5]

# This variable stores the average of list of numbers.
average = sum(numbers) / len(numbers)
print(average)
```
- Don't use closing brace comments.
- Use as explanation of intent or clarification of code.
- Use as TODO comments
- Avoid "journaling" comments
- Use as warning of consequences.
		
		Often we know that certain code lines are very necessary and that the program,
		for example, could crash without them. In this situation, other developers might be warned
		of the value of certain code lines.
- Don't comment out code. Just remove.

		The worst thing you can do is to leave code commented out in your programs.
		All the debug code or debug messages should be removed before pushing to a version control system,
		otherwise, your colleagues will be scared of deleting it and your commented code will stay there forever.

  

