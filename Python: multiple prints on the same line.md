How to print without newline in Python?
Generally people switching from C/C++ to Python wonder how to print two or more variables or statements without going into a new line in python. Since the python print() function by default ends with newline. Python has a predefined format if you use print(a_variable) then it will go to next line automatically.
For examples:



print("geeks") 
print("geeksforgeeks") 
will result into this

geeks
geeksforgeeks
But sometime it may happen that we don’t want to go to next line but want to print on the same line. So what we can do?
For Example:

Input : print("geeks") print("geeksforgeeks")
Output : geeks geeksforgeeks

Input : a = [1, 2, 3, 4]
Output : 1 2 3 4 
The solution discussed here is totally dependent on the python version you are using.

Print without newline in Python 2.x


# Python 2 code for printing 
# on the same line printing 
# geeks and geeksforgeeks  
# in the same line 
  
print("geeks"), 
print("geeksforgeeks") 
  
# array 
a = [1, 2, 3, 4] 
  
# printing a element in same 
# line 
for i in range(4): 
    print(a[i]),  
Output:

geeks geeksforgeeks
1 2 3 4
Print without newline in Python 3.x


# Python 3 code for printing 
# on the same line printing  
# geeks and geeksforgeeks  
# in the same line 
  
print("geeks", end =" ") 
print("geeksforgeeks") 
  
# array 
a = [1, 2, 3, 4] 
  
# printing a element in same 
# line 
for i in range(4): 
    print(a[i], end =" ")  
Output:

geeks geeksforgeeks
1 2 3 4




This simple example will print 1-10 on the same line.

for i in range(1,11):
    print (i, end=" ")
    
    
    
    sources:
    1.https://www.geeksforgeeks.org/print-without-newline-python/
    2.https://stackoverflow.com/questions/5598181/python-multiple-prints-on-the-same-line
