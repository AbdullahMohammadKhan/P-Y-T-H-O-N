Python : How to convert a list to dictionary ?Varun June 30, 2018 Python : How to convert a list to dictionary ?2019-10-19T13:46:38+05:30dictionary, Python No Comment
In this article we will discuss different ways to convert a single or multiple lists to dictionary in Python.

Following conversions from list to dictionary will be covered here,

Convert a List to Dictionary with same values
Convert List items as keys in dictionary with enumerated value
Convert two lists to dictionary
Convert a list of tuples to dictionary
Convert a List to Dictionary with same values
Suppose we have a list of strings i.e.

# List of strings
listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
1
2
# List of strings
listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
Now we want to create a dictionary with all elements in this list as keys. For each key value will be same i.e. 5. Let’s see how to do that i.e.

Using dictionary comprehension

'''
Converting a list to dictionary with list elements as keys in dictionary
All keys will have same value
''' 
dictOfWords = { i : 5 for i in listOfStr }
1
2
3
4
5
'''
Converting a list to dictionary with list elements as keys in dictionary
All keys will have same value
''' 
dictOfWords = { i : 5 for i in listOfStr }
Dictionary contents will be,

hello  ::  5
here  ::  5
this  ::  5
test  ::  5
at  ::  5
now  ::  5
1
2
3
4
5
6
hello  ::  5
here  ::  5
this  ::  5
test  ::  5
at  ::  5
now  ::  5
Using dict.fromKeys()

'''
Converting a list to dictionary with list elements as keys in dictionary
using dict.fromkeys()
''' 
dictOfWords = dict.fromkeys(listOfStr , 1)
1
2
3
4
5
'''
Converting a list to dictionary with list elements as keys in dictionary
using dict.fromkeys()
''' 
dictOfWords = dict.fromkeys(listOfStr , 1)
dict.fromKeys() accepts a list and default value. It returns a dictionary with items in list as keys. All dictionary items will have same value, that was passed in fromkeys().

If no default value was passed in fromKeys() then default value for keys in dictionary will be None.

Convert List items as keys in dictionary with enumerated value
Suppose we have a list of strings i.e.

# List of strings
listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
1
2
# List of strings
listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
Let’s create a dictionary from this list with list elements as keys and values as integers from 0 to n-1 (n is size of list) i.e.

'''
Converting a list to dictionary with list elements as values in dictionary
and keys are enumerated index starting from 0 i.e. index position of element in list
''' 
dictOfWords = { i : listOfStr[i] for i in range(0, len(listOfStr) ) }
1
2
3
4
5
'''
Converting a list to dictionary with list elements as values in dictionary
and keys are enumerated index starting from 0 i.e. index position of element in list
''' 
dictOfWords = { i : listOfStr[i] for i in range(0, len(listOfStr) ) }
Dictionary contents will be,

0  ::  hello
1  ::  at
2  ::  test
3  ::  this
4  ::  here
5  ::  now
1
2
3
4
5
6
0  ::  hello
1  ::  at
2  ::  test
3  ::  this
4  ::  here
5  ::  now
Convert two lists to a dictionary
Suppose we have two lists i.e.

# List of strings
listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
# List of ints
listOfInt = [56, 23, 43, 97, 43, 102]
1
2
3
4
5
# List of strings
listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
    
# List of ints
listOfInt = [56, 23, 43, 97, 43, 102]
Let’s create a dictionary with elements of listOfStr as keys and elements of listOfInt as values using zip() i.e

# Create a zip object from two lists
zipbObj = zip(listOfStr, listOfInt)
# Create a dictionary from zip object
dictOfWords = dict(zipbObj)
1
2
3
4
5
# Create a zip object from two lists
zipbObj = zip(listOfStr, listOfInt)
 
# Create a dictionary from zip object
dictOfWords = dict(zipbObj)
Zip() accepts a number of iterable objects and returns a list of tuples. Each entry in tuple contains an element from each iterable object.
We have passed two lists objects in zip() , so it will return a list of tuples, where each tuple contains an entry from both the lists. Then we created a dictionary object from this list of tuples.

Dictionary contents are,

Dictionary from two Lists 
hello  ::  56
here  ::  43
this  ::  97
test  ::  43
at  ::  23
now  ::  102
1
2
3
4
5
6
7
Dictionary from two Lists 
hello  ::  56
here  ::  43
this  ::  97
test  ::  43
at  ::  23
now  ::  102
If length of keys list is less than list of values then remaining elements in value list will be skipped.
Convert a list of tuples to dictionary
Suppose we have a list of tuples with two columns in each entry i.e.

# List of tuples    
listofTuples = [("Riti" , 11), ("Aadi" , 12), ("Sam" , 13),("John" , 22),("Lucy" , 90)]
1
2
# List of tuples    
listofTuples = [("Riti" , 11), ("Aadi" , 12), ("Sam" , 13),("John" , 22),("Lucy" , 90)]
We can directly pass this list of tuples to dictionary constructor i.e

# Convert a list of tuple to dictionary
studentsDict = dict(listofTuples)
1
2
# Convert a list of tuple to dictionary
studentsDict = dict(listofTuples)
Entries in first column will become the key and entries in second column will the values in the new dictionary. Contents of dictionary will be,

Dictionary from List of Tuples
John  ::  22
Lucy  ::  90
Riti  ::  11
Aadi  ::  12
Sam  ::  13
1
2
3
4
5
6
Dictionary from List of Tuples
John  ::  22
Lucy  ::  90
Riti  ::  11
Aadi  ::  12
Sam  ::  13
Learn more about Dictionaries in Python,
The Modern Python 3 Bootcamp
The Python Bible Everything You Need to Program in Python
Programming for Everybody (Getting Started with Python)
Python for Beginners with Examples
Python 3 Programming
Complete example is as follows,

'''
Display contents of dictionary with each key/value pair in seperate line
'''
def displatDict(text, dictOfElements) :
print("*************")
print(text)
for key , value in dictOfElements.items():
print(key, " :: ", value)
def main():
# List of strings
listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
'''
Converting a list to dictionary with list elements as keys in dictionary
All keys will have same value
''' 
dictOfWords = { i : 5 for i in listOfStr }
displatDict("Dictionary with same value " , dictOfWords)   
'''
Converting a list to dictionary with list elements as keys in dictionary
using dict.fromkeys()
''' 
dictOfWords = dict.fromkeys(listOfStr , 1)
displatDict("Dictionary with given default value " , dictOfWords) 
dictOfWords = dict.fromkeys(listOfStr)
displatDict("Dictionary with same default value None " , dictOfWords)
'''
Converting a list to dictionary with list elements as values in dictionary
and keys are enumerated index starting from 0 i.e. index position of element in list
''' 
dictOfWords = { i : listOfStr[i] for i in range(0, len(listOfStr) ) }
displatDict("Dictionary with enumerated keys" , dictOfWords)
'''
Converting multiple lists to dictionary using zip
list1 will be used as keys and list2 as values
''' 
# List of strings
listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
# List of ints
listOfInt = [56, 23, 43, 97, 43, 102]
# Create a zip object from two lists
zipbObj = zip(listOfStr, listOfInt)
# Create a dictionary from zip object
dictOfWords = dict(zipbObj)
displatDict("Dictionary from two Lists " , dictOfWords)
'''
If list of keys is greater than list of values then extra keys will be skipped
'''
# List of strings
listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
# List of ints
listOfInt = [56, 23, 43, 97, 43]
zipbObj = zip(listOfStr, listOfInt)
dictOfWords = dict(zipbObj)
displatDict("Dictionary from two Lists " , dictOfWords)
'''
Convert a list of tuples to Dictionary
'''
# List of tuples    
listofTuples = [("Riti" , 11), ("Aadi" , 12), ("Sam" , 13),("John" , 22),("Lucy" , 90)]
# Convert a list of tuple to dictionary
studentsDict = dict(listofTuples)
displatDict("Dictionary from List of Tuples" , studentsDict)
if __name__ == '__main__':
main()
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
83
84
85
86
87
88
89
90
91
92
93
94
95
96
97
98
99
100
'''
Display contents of dictionary with each key/value pair in seperate line
'''
def displatDict(text, dictOfElements) :
    print("*************")
    print(text)
    for key , value in dictOfElements.items():
        print(key, " :: ", value)
 
def main():
    
    
    # List of strings
    listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
 
 
    '''
    Converting a list to dictionary with list elements as keys in dictionary
    All keys will have same value
    ''' 
    dictOfWords = { i : 5 for i in listOfStr }
    
    displatDict("Dictionary with same value " , dictOfWords)   
 
    '''
    Converting a list to dictionary with list elements as keys in dictionary
    using dict.fromkeys()
    ''' 
    
    dictOfWords = dict.fromkeys(listOfStr , 1)
    
    displatDict("Dictionary with given default value " , dictOfWords) 
    
    dictOfWords = dict.fromkeys(listOfStr)
    
    displatDict("Dictionary with same default value None " , dictOfWords)
 
    
    '''
    Converting a list to dictionary with list elements as values in dictionary
    and keys are enumerated index starting from 0 i.e. index position of element in list
    ''' 
    dictOfWords = { i : listOfStr[i] for i in range(0, len(listOfStr) ) }
    
    
    displatDict("Dictionary with enumerated keys" , dictOfWords)
    
    
    
    '''
    Converting multiple lists to dictionary using zip
    list1 will be used as keys and list2 as values
    ''' 
    
    # List of strings
    listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
        
    # List of ints
    listOfInt = [56, 23, 43, 97, 43, 102]
    
    # Create a zip object from two lists
    zipbObj = zip(listOfStr, listOfInt)
    
    # Create a dictionary from zip object
    dictOfWords = dict(zipbObj)
    
    displatDict("Dictionary from two Lists " , dictOfWords)
    
    '''
    If list of keys is greater than list of values then extra keys will be skipped
    '''
    
    # List of strings
    listOfStr = ["hello", "at" , "test" , "this" , "here" , "now" ]
 
    # List of ints
    listOfInt = [56, 23, 43, 97, 43]
    
    zipbObj = zip(listOfStr, listOfInt)
    
    dictOfWords = dict(zipbObj)
    
    displatDict("Dictionary from two Lists " , dictOfWords)
    
    '''
    Convert a list of tuples to Dictionary
    '''
 
    # List of tuples    
    listofTuples = [("Riti" , 11), ("Aadi" , 12), ("Sam" , 13),("John" , 22),("Lucy" , 90)]
    
    # Convert a list of tuple to dictionary
    studentsDict = dict(listofTuples)
        
    displatDict("Dictionary from List of Tuples" , studentsDict)
   
            
            
if __name__ == '__main__':
    main()
Output

Vim
*************
Dictionary with same value 
now  ::  5
here  ::  5
test  ::  5
at  ::  5
this  ::  5
hello  ::  5
*************
Dictionary with given default value 
now  ::  1
here  ::  1
test  ::  1
at  ::  1
this  ::  1
hello  ::  1
*************
Dictionary with same default value None 
now  ::  None
here  ::  None
test  ::  None
at  ::  None
this  ::  None
hello  ::  None
*************
Dictionary with enumerated keys
0  ::  hello
1  ::  at
2  ::  test
3  ::  this
4  ::  here
5  ::  now
*************
Dictionary from two Lists 
now  ::  102
here  ::  43
test  ::  43
at  ::  23
this  ::  97
hello  ::  56
*************
Dictionary from two Lists 
test  ::  43
at  ::  23
this  ::  97
hello  ::  56
here  ::  43
*************
Dictionary from List of Tuples
John  ::  22
Lucy  ::  90
Riti  ::  11
Aadi  ::  12
Sam  ::  13
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
*************
Dictionary with same value 
now  ::  5
here  ::  5
test  ::  5
at  ::  5
this  ::  5
hello  ::  5
*************
Dictionary with given default value 
now  ::  1
here  ::  1
test  ::  1
at  ::  1
this  ::  1
hello  ::  1
*************
Dictionary with same default value None 
now  ::  None
here  ::  None
test  ::  None
at  ::  None
this  ::  None
hello  ::  None
*************
Dictionary with enumerated keys
0  ::  hello
1  ::  at
2  ::  test
3  ::  this
4  ::  here
5  ::  now
*************
Dictionary from two Lists 
now  ::  102
here  ::  43
test  ::  43
at  ::  23
this  ::  97
hello  ::  56
*************
Dictionary from two Lists 
test  ::  43
at  ::  23
this  ::  97
hello  ::  56
here  ::  43
*************
Dictionary from List of Tuples
John  ::  22
Lucy  ::  90
Riti  ::  11
Aadi  ::  12
Sam  ::  13
