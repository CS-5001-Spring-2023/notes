Exam 2 Study Guide
==================

## Format

Exam 2 will take place in person on Wednesday, Mar 15 from 3-4:40pm. It will be 8-12 questions in length. You may be asked to define terminology, trace code, explain code, and write code. 

The exam will be *on paper*. Your solutions must be handwritten; however, you will be permitted to use any resources you wish (including the internet and/or a Python interpreter) to test your code or look up syntax. You are not permitted to look up entire solutions to problems (or ask ChatGPT to give you the solution). I expect you to use resources as you would for your homework problems. If I suspect that any part of your solution has been copied in whole or in part from another source I reserve the right to require an additional, oral code review of your solutions. Failure to explain your solution may result in a 0 on the exam and/or a report to the academic integrity committee.

Note, the exam will end promptly at 4:40pm. Though you may use a computer, if you rely entirely on the computer you are not likely to have sufficient time to complete all of the questions for the exam. Time management will be crucial!

## Topics

The topics covered on the exam will include the following:

* Recursion
  - Given a recursive function, describe what it does
  - Given a recursive function, identify the base case
  - Given a recursive function, describe how the recursive call makes progress toward the base case
  - Identify and fix a bug in a recursive function
  - Write a recursive function to solve a given problem
* Errors/Error Handling
  - Use try/except to handle an error
  - Write a function that raises errors
* Dictionaries
  - Insert a new item into a dictionary
  - Determine if a value exists in a dictionary
  - Find a data item stored in a dictionary
* Classes
  - Create an instance of a class
  - Call a method on an object


## Example Problems

**Question 1**

```python
def mystery(n):
	if n == 1:
		return 1
	return n + mystery(n-1)

```

Given the code above, answer the following questions:

1. What does the function do? Provide an English explanation of the behavior.
2. What is the base case of the function?
3. What would the output be if the function were called as follows: mystery(-3)?

**Question 2**

```python
def print_string_backward(string):
	"""
	Implement a recursive function that takes as input a str and prints 
	the characters of the str *in reverse* one per line *without using a loop*. 
	"""
	if len(string) == 1:
		return

	print_string_backward(string[1:])
	print(string[0])
```

Identify the bug in the function above. For full credit, your solution must (1) describe the bug in English and (2) provide the modified code that would fix the bug.

**Question 3**
Given a string, compute recursively a new string where all the 'x' chars have been removed.

**Question 4**
Given a non-negative int n, return the sum of its digits recursively (no loops). 

sum\_digits(126) → 9; sum\_digits(49) → 13; sum\_digits(12) → 3

**Question 5**
Write a function called validation that behaves as follows:

Function: validation
   perform multiplication with different types
Parameters:
   one. an negative integer value
   two. a positive floating point number less than 1000
Returns the product of the two parameter values

The function will raise an error if one is not a negative integer or if two is not a postive floating point numebr less than 1000.

**Question 6**
Write a function called get\_key\_string that receives a dictionary and returns the keys of the dictionary as a string separated by the character '-'.

**Question 7**
Write a function called initialize that creates and returns a dictionary that contains the following data:

|Keys| Values	                    |
|---|----------------------------|
| Maria | Associate Professor |
| Jodi | Professor of the Practice |
| Beth | Dean of Khoury |

**Question 8**

```python
class Pair:

	def __init__(self, x, y):
		self.x = x
		self.y = y	
				
	def sum(self):
		return self.x + self.y
```

Given the class definition above write a code fragment that does the following:

1. Create an instance of Pair
2. Call the sum method and print the result