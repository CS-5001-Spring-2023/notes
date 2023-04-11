Exam 3 Study Guide
==================

## Format

Exam 3 will take place in person on Monday, Apr 17 from 3-4:40pm. It will be 8-12 questions in length. You may be asked to define terminology, trace code, explain code, and write code. 

The exam will be *on paper*. Your solutions must be handwritten; however, you will be permitted to use any resources you wish (including the internet and/or a Python interpreter) to test your code or look up syntax. You are not permitted to look up entire solutions to problems (or ask ChatGPT to give you the solution). I expect you to use resources as you would for your homework problems. If I suspect that any part of your solution has been copied in whole or in part from another source I reserve the right to require an additional, oral code review of your solutions. Failure to explain your solution may result in a 0 on the exam and/or a report to the academic integrity committee.

The exam will primarily focus on topics covered since Exam 2; however, there may be questions related to topics discussed in the first part of the semester. For example, it is likely there will be a recursion question on the exam!


## Topics

The exam may cover any topics we have discussed this semester. It is recommended that you review the Exam 1 and Exam 2 study guides as well.

The topics *emphasized* on Exam 3 will include the following:

* Stacks
  - Describe the result of applying one or more push/pop operations
  - Identify and fix bugs in a Stack implementation
  - Add additional operations to a Stack implementation
  - Use a Stack to solve a problem (e.g., determining whether parens are matching)
* Queues
  - Describe the result of applying one or more enqueue/dequeue operations
  - Identify and fix bugs in a Queue implementation that uses a circular buffer
* Efficiency
  - Determine the runtime bounds of an algorithm or code snippet (e.g., understand running time of operations on lists versus dictionaries)
  - Design a data structure to ensure a particular runtime bound for a given operation 
* Linear search
  - Find an item in a list
* Binary search
  - Identify and fix bugs in a binary search implementation
  - Trace the execution of a binary search implementation
* Sorting
  - Trace the execution of a sorting algorithm -- insertion, selection, or bubble sort

## Example Problems

**Question 1**
What is the result of applying the following operations on a ```Stack```? Provide the output of the code fragment.

```python
stack = Stack(5)
stack.push(23)
stack.push(37)
stack.push(92)
print(stack.pop())
stack.push(45)
print(stack.pop())
print(stack.pop())
```

**Question 2**
What is the result of applying the following operations on a ```Queue```? Provide the output of the code fragment.

```python
queue = Queue(5)

queue.enqueue(23)
queue.enqueue(37)
queue.enqueue(92)
print(queue.dequeue())
queue.enqueue(45)
print(queue.dequeue())
print(queue.dequeue())
```

**Question 3**
Consider a ```Stack``` implementation that uses a list to store the items in the ```Stack```. One possible implementation for ```push``` is to insert the new item at the beginning of the list. The implementation of ```pop``` then removes the item at position 0. Another possible implementation for ```push``` is to append the new item at the end of the list. The implementation of ```pop``` then removes the last item. Which approach is better *and why*?

**Question 4**
Given a ```Queue``` implemented using a circular buffer, what is the big-oh running time of the ```enqueue``` operation and the ```dequeue``` operation?

**Question 5**
The web-based Message Board application we implemented in class used a list to store all messages that had been posted to the server. To display a single message we used the following code:

```python
	elif len(message_id) > 0:
		for i in message_list:
			if i.message_id == int(message_id[0]):
				result = i
				break
		return render_template('message.html', item=result)

```

What is the big-oh running time of this code fragment?

**Question 6**
The ```Gradebook``` application we implemented in class used a list to store ```Student``` objects. Following is the logic we used to add a new score to a student's record.

```python

	def add_score(self, first, last, score):
		for student in self.students:
			if student.first == first and student.last == last:
				student.add_score(score)
				break
```
What is the big-oh running time of this method?

**Question 7**
Consider the ```Gradebook``` application described in Question 6. Would it be possible to modify the data structure(s) that store the student records such that the add_score method as shown above could be implemented to execute in O(1) time? If so, describe how. If not, describe why not.

**Question 8**
Consider an email application. Assume the top-level data structured used in the application is a dictionary that maps a username to a data structure that stores a collection of individual messages. Would you choose to store the collection of individual messages in a list or a dictionary? Explain your answer.

**Question 9**
The ```selection_sort``` implementation we discussed in class is as follows:

```python
def selection_sort(things):
    '''
    Function: selection_sort -- sorting the elements of a list by inserting
                                each element into a list in order
    Parameters:
       things -- the elements to be sorted
    Returns a new list with all of the elements in sorted order
    '''
    for i in range(len(things) - 1):
        # select the next element by finding it in things
        min = i
        for j in range(i + 1, len(things)):
            if things[j] < things[min]:
                min = j
        things[i], things[min] = things[min], things[i]
    return things
```

Given the following input, show the state of the list things after every iteration of the outer for loop:

```things = [5, 2, 6, 1, 7, 3, 4]```

**Question 10**
Write a recursive function ```check_wordle``` that takes as input a wordle word and a guess and returns the number of *green* letters -- that is, the number of letters that are the same letter in the same position in both the wordle word and the guess.