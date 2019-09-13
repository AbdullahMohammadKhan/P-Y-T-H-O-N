Nested List Comprehensions in Python
List Comprehensions are one of the most amazing features of Python. It is a smart and concise way of creating lists by iterating over an iterable object. Nested List Comprehensions are nothing but a list comprehension within another list comprehension which is quite similar to nested for loops.

Let’s take a look at some examples to understand what nested list comprehensions can do:

Example 1:

I want to create a matrix which looks like below:

matrix = [[0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4]]
The below code uses nested for loops for the given task:

filter_none
edit
play_arrow

brightness_4
matrix = [] 
  
for i in range(5): 
      
    # Append an empty sublist inside the list 
    matrix.append([]) 
      
    for j in range(5): 
        matrix[i].append(j) 
          
print(matrix) 
Output:
[[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]
The same output can be achieved using nested list comprehension in just one line:

filter_none
edit
play_arrow

brightness_4
# Nested list comprehension 
matrix = [[j for j in range(5)] for i in range(5)] 
  
print(matrix) 
Output:
[[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]
Explanation:

The syntax of the above program is shown below:

[expression for i in range(5)] –> which means that execute this expression and append its output to the list until variable i iterates from 0 to 4.

For example:- [i for i in range(5)] –> In this case, the output of the expression
is simply the variable i itself and hence we append its output to the list while i
iterates from 0 to 4.

Thus the output would be –> [0, 1, 2, 3, 4]

But in our case, the expression itself is a list comprehension. Hence we need to first
solve the expression and then append its output to the list.

expression = [j for j in range(5)] –> The output of this expression is same as the
example discussed above.

Hence expression = [0, 1, 2, 3, 4].

Now we just simply append this output until variable i iterates from 0 to 4 which would
be total 5 iterations. Hence the final output would just be a list of the output of the
above expression repeated 5 times.

Output: [[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]

Example 2:

Suppose I want to flatten a given 2-D list:

matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

Expected Output: flatten_matrix = [1, 2, 3, 4, 5, 6, 7, 8, 9]
This can be done using nested for loops as follows:

filter_none
edit
play_arrow

brightness_4
# 2-D List 
matrix = [[1, 2, 3], [4, 5], [6, 7, 8, 9]] 
  
flatten_matrix = [] 
  
for sublist in matrix: 
    for val in sublist: 
        flatten_matrix.append(val) 
          
print(flatten_matrix) 
Output:
[1, 2, 3, 4, 5, 6, 7, 8, 9]
Again this can be done using nested list comprehension which has been shown below:

filter_none
edit
play_arrow

brightness_4
# 2-D List 
matrix = [[1, 2, 3], [4, 5], [6, 7, 8, 9]] 
  
# Nested List Comprehension to flatten a given 2-D matrix 
flatten_matrix = [val for sublist in matrix for val in sublist] 
  
print(flatten_matrix) 
Output:
[1, 2, 3, 4, 5, 6, 7, 8, 9]
Explanation:

In this case, we need to loop over each element in the given 2-D list and append it
to another list. For better understanding, we can divide the list comprehension into
three parts:

flatten_matrix = [val
                  for sublist in matrix
                  for val in sublist]
The first line suggests what we want to append to the list. The second line is the
outer loop and the third line is the inner loop.

‘for sublist in matrix’ returns the sublists inside the matrix one by one which would be:

[1, 2, 3], [4, 5], [6, 7, 8, 9]

‘for val in sublist’ returns all the values inside the sublist.

Hence if sublist = [1, 2, 3], ‘for val in sublist’ –> gives 1, 2, 3 as output one by one.

For every such val, we get the output as val and we append it to the list.

Example 3:

Suppose I want to flatten a given 2-D list and only include those strings whose lengths are less than 6:

planets = [[‘Mercury’, ‘Venus’, ‘Earth’], [‘Mars’, ‘Jupiter’, ‘Saturn’], [‘Uranus’, ‘Neptune’, ‘Pluto’]]

Expected Output: flatten_planets = [‘Venus’, ‘Earth’, ‘Mars’, ‘Pluto’]

This can be done using an if condition inside a nested for loop which is shown below:

filter_none
edit
play_arrow

brightness_4
# 2-D List of planets 
planets = [['Mercury', 'Venus', 'Earth'], ['Mars', 'Jupiter', 'Saturn'], ['Uranus', 'Neptune', 'Pluto']] 
  
flatten_planets = [] 
  
for sublist in planets: 
    for planet in sublist: 
          
        if len(planet) < 6: 
            flatten_planets.append(planet) 
          
print(flatten_planets) 
Output:
['Venus', 'Earth', 'Mars', 'Pluto']
This can also be done using nested list comprehensions which has been shown below:

filter_none
edit
play_arrow

brightness_4
# 2-D List of planets 
planets = [['Mercury', 'Venus', 'Earth'], ['Mars', 'Jupiter', 'Saturn'], ['Uranus', 'Neptune', 'Pluto']] 
  
# Nested List comprehension with an if condition 
flatten_planets = [planet for sublist in planets for planet in sublist if len(planet) < 6] 
          
print(flatten_planets) 
Output:
['Venus', 'Earth', 'Mars', 'Pluto']
Explanation:

This example is quite similar to the previous example but in this example, we just
need an extra if condition to check if the length of a particular planet is less than
6 or not.

This can be divided into 4 parts as follows:

flatten_planets = [planet 
                   for sublist in planets 
                   for planet in sublist 
                   if len(planet) < 6] 
                   
                   
                   
                   
If I had two strings, 'abc' and 'def', I could get all combinations of them using two for loops:

for j in s1:
  for k in s2:
    print(j, k)
    
    
    
lst = [j + k for j in s1 for k in s2]
or

lst = [(j, k) for j in s1 for k in s2]


if you want tuples.

Like in the question, for j... is the outer loop, for k... is the inner loop.

Essentially, you can have as many independent 'for x in y' clauses as you want in a list comprehension just by sticking one after the other.


Since this is essentially a Cartesian product, you can also use itertools.product. I think it's clearer, especially when you have more input iterables.

itertools.product('abc', 'def', 'ghi')



Double Iteration in List Comprehension
July 14, 2012

This post is a few years old now, so some details (or my opinions) might be out of date.
I would still love to hear your feedback in the comments below. Enjoy!
Here’s something I didn’t know possible in Python: iteration over more than one iterable in a list comprehension:

>>> seq_x = [1, 2, 3, 4]
>>> seq_y = 'abc'
>>> [(x,y) for x in seq_x for y in seq_y]
[(1, 'a'), 
 (1, 'b'), 
 (1, 'c'), 
 (2, 'a'), 
 (2, 'b'), 
 (2, 'c'), 
 (3, 'a'), 
 (3, 'b'), 
 (3, 'c'), 
 (4, 'a'), 
 (4, 'b'), 
 (4, 'c')]
Cool, isn’t it? It’s equivalent to the following snippet:

>>> result = [] 
... for x in seq_x: 
...     for y in seq_y:  
...         result.append((x,y)) 
>>> result 
[(1, 'a'), 
 (1, 'b'), 
 (1, 'c'), 
 (2, 'a'), 
 (2, 'b'), 
 (2, 'c'), 
 (3, 'a'), 
 (3, 'b'), 
 (3, 'c'), 
 (4, 'a'), 
 (4, 'b'), 
 (4, 'c')]
It also supports both “if” statements and referencing the outer iterator from the inner one, like so:

>>> seq = ['abc', 'def', 'g', 'hi'] 
... [y for x in seq if len(seq) > 1 for y in x if y != 'e'] 
['a', 'b', 'c', 'd', 'f', 'g', 'h', 'i']
This is equivalent to the snippet:

>>> result = [] 
... for x in seq: 
...     if len(seq) > 1: 
...         for y in x: 
...             if y != 'e': 
...                 result.append(y) 
... result 
['a', 'b', 'c', 'd', 'f', 'g', 'h', 'i']
The thing you should notice here, is that the outer loop is the first ‘for’ loop in the list comprehension. This was a little confusing for me at first because when I nest list comprehensions it’s the other way around.

To read more about this feature, check out this StackOverflow thread or the Python Manual.




Refs:
1.https://amir.rachum.com/blog/2012/07/14/double-iteration-in-list-comprehension/
2.https://www.geeksforgeeks.org/nested-list-comprehensions-in-python/
