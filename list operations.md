Consider <h6> a list (list = []). You can perform the following commands:

insert i e: Insert integer  at position .
print: Print the list.
remove e: Delete the first occurrence of integer .
append e: Insert integer  at the end of the list.
sort: Sort the list.
pop: Pop the last element from the list.
reverse: Reverse the list.
Initialize your list and read in the value of  followed by  lines of commands where each command will be of the  types listed above.
Iterate through each command in order and perform the corresponding operation on your list.
Concept

You have already used lists in previous hacks. List comprehensions are an elegant way to build a list without having to
use different for loops to append values one by one. These examples might help.

The simplest form of a list comprehension is:

[ expression-involving-loop-variable for loop-variable in sequence ]

This will step over every element in a sequence, successively setting the loop-variable equal to every element one at a time.
It will then build up a list by evaluating the expression-involving-loop-variable for each one.
This eliminates the need to use lambda forms and generally produces a much more readable code than using map() and
a more compact code than using a for loop.

>> ListOfNumbers = [ x for x in range(10) ] # List of integers from 0 to 9
>> ListOfNumbers
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
List comprehensions can be nested where they take the following form:

[ expression-involving-loop-variables for outer-loop-variable in outer-sequence for inner-loop-variable in inner-sequence ]

This is equivalent to writing:

results = []
for outer_loop_variable in outer_sequence:
    for inner_loop_variable in inner_sequence:
        results.append( expression_involving_loop_variables )

The final form of list comprehension involves creating a list and filtering it similar to using the filter() method. 
The filtering form of list comprehension takes the following form:

[ expression-involving-loop-variable for loop-variable in sequence if boolean-expression-involving-loop-variable ]

This form is similar to the simple form of list comprehension, but it evaluates boolean-expression-involving-loop-variable for every item.
It also only keeps those members for which the boolean expression is True.

>> ListOfThreeMultiples = [x for x in range(10) if x % 3 == 0] # Multiples of 3 below 10
>> ListOfThreeMultiples
[0, 3, 6, 9]


 Generator Functions in Python


# We will generate the cubes of (1-10) using a simple generator function of our own, and using a python generator which uses the Yield keyword for lazy evaluation


def cube(n):
	return n**3

def simplifiedGenerator(n):
	generatedResults = []
	currentN = 1
	while currentN <= n:
		generatedResults.append(cube(currentN))
		currentN += 1
	return generatedResults


# This is an example of Lazy evaluation- using Python's Generators
# This code does not run when called initially
# It will only return a "Generator" object
# From that object we can collect the list items, one by one
def generatorUsingYield(n):
	currentN = 1
	while currentN <= n:
		yield cube(currentN)
		currentN += 1		
	


# Using the Simplified Generator Code, we start with numbers x = (1..10) and for each of them, we generate x^3
print "Using the Simplified Generator Code, we start with numbers x = (1..10) and for each of them, we generate x^3"
# Resulting list using simplified generator
print simplifiedGenerator(10)


# Now we use the generator code which uses yield
# After this, only the generator object will be returned
print "Result using the Generator function with Yield"
generatedValues = generatorUsingYield(10)

print "We will traverse through the values from the generator object"
# Now, we actually compute and display the values from the generator object
print [i for i in generatedValues]


Output from the above program:

~/work/pythontutorials$ python generators.py 
Using the Simplified Generator Code, we start with numbers x = (1..10) and for each of them, we generate x^3
[1, 8, 27, 64, 125, 216, 343, 512, 729, 1000]
Result using the Generator function with Yield
We will traverse through the values from the generator object
[1, 8, 27, 64, 125, 216, 343, 512, 729, 1000]
