



Consider a list (list = []). You can perform the following commands:

insert i e: Insert integer  at position .
print: Print the list.
remove e: Delete the first occurrence of integer .
append e: Insert integer  at the end of the list.
sort: Sort the list.
pop: Pop the last element from the list.
reverse: Reverse the list.
Initialize your list and read in the value of  followed by  lines of commands where each command will be of the  types listed above. Iterate through each command in order and perform the corresponding operation on your list.

Input Format

The first line contains an integer, , denoting the number of commands.
Each line  of the  subsequent lines contains one of the commands described above.

Constraints

The elements added to the list must be integers.
Output Format

For each command of type print, print the list on a new line.

Sample Input 0

12
insert 0 5
insert 1 10
insert 0 6
print
remove 6
append 9
append 1
sort
print
pop
reverse
print
Sample Output 0

[6, 5, 10]
[1, 5, 9, 10]
[9, 5, 1]


```python
import random 
L=[] 
N = int(input())

for row in range(N): 
  inputs = input().split() 
  if len(inputs)==1: 
    command =inputs[0]
  if len(inputs)==2:
     command = inputs[0] 
  e = int(inputs[1]) 
  if len(inputs)==3: 
      command = inputs[0] 
i = int(inputs[1]) 
e = int(inputs[2])

if command=="insert":
    L.insert(i,e)
elif command=="remove":
    L.remove(e)
elif command=="append":
     L.append(e)
elif command=="sort":
     L.sort()
elif command=="pop":
if len(list)!=0:
     L.pop()
elif command=="reverse":
     L.reverse()
elif command=="print":
     print(L)

#or


if __name__ == '__main__':
    N = int(input())
    result = []
    for n in range(N):
        x = input().split(" ")
        command = x[0]
        if command == 'append':
            result.append(int(x[1]))
        if command == 'print':
            print(result)
        if command == 'insert':
            result.insert(int(x[1]), int(x[2]))
        if command == 'reverse':
            result == result[::-1]
        if command == 'pop':
            result.pop()
        if command == 'sort':
            result == sorted(result)
        if command == 'remove':
            result.remove(int(x[1]))
        print(result)
        
#or 
if __name__ == '__main__':
    N = int(input())
    array = []
    for i in range(N) :
        inputs = input().split()
        if len(inputs) == 3 :
            array.insert(int(inputs[1]),int(inputs[2]))
        elif len(inputs) == 2 :
            if inputs[0] == "append" :
                array.append(int(inputs[1]))
            else :
                array.remove(int(inputs[1]))
        else :
            if inputs[0] == "print" :
                print(array)
            elif inputs[0] == "sort" :
                array.sort()
            elif inputs[0] == "pop" :
                array.pop()
            else :
                array.reverse()
            
```


**result.append(elem) -- adds a single element to the end of the list, just modifies the original.

result.insert(index, elem) -- inserts the element at the given index, shifting elements to the right.


The eval function lets a python program run python code within itself. Let me explain you the entire code :) 1.First we take input of how many instruction user will enter. 2.We declare an array. 3.Then loop starts ,which will run n times. 4.s=input().split()....... it takes multiple input at one go.(Remember it takes input in string format, you need to convert it according to your use) What split does is explicitly specify split(‘ ‘) because split() uses any whitespace characters as delimiter as default. 5.As per the format of question the first item of 's' will be the command i.e insert ,append , print etc. 6.And starting from item 1 onwards we will get our argument eg. insert 0 1... which means item0 which is our command viz "insert" and item one onwards we get our arguments viz 0,1 . 7.Now we check whether or not the command is "Print".I f it is "print" we simply print the list. else 8.we join our command and arguments . so our final command becomes insert(0,1). (refer point 6) 9.Now, eval run l.insert(0,1) within itself what is happening in eval("l."+cmd) is: l(which is our list) we concat list with the command , and we all know the use of'.' l.command(attributes)


I am new to Python, but eval() is considered bad practice and contains a security hole: http://stackoverflow.com/a/9384005

This is how I made mine and it avoids that security hole:

cmd = "l.{}({},{})".format(cmd, num[0], num[1])

exec(cmd)

Can someone explain this line?

cmd += "("+ ",".join(args) +")"

I'm also trying to understand this, and am picking it appart one piece at a time. ---------------Number one--------------

cmd +=
here he is appending some text to the 'command' string that gets evaluated later in the code.

---------------Number two--------------

cmd += "("+ ",".join(args) +")"
Here the brackets on the far left and right sides have quotes around them because he is trying to construct the part where the two numbers(arguments) are used by the function. The comma also has quotes because it is needed between those two numbers.

the plus signs simply join the pieces of text together, and the .join(args) is used to insert the numbers into the argument section of the function.

my problem in understanding is that I would have assumed that the .join(args) would need to be written befor and after the comma in that line of text.

The reason why it's written before is that .join() is a function you call on a string. The string is what joins the arguments. The string here being a comma the result of ",".join(args) is 2,3 (in the case that args = [2,3])

join() is string method which takes either a string or List of strings as parameters ex:- join("hai") or join(["hai","bye"])

the "," before .join() is delimiter. means by using comma JOIN joins the hai and bye

so ",".join(["hai","bye"])

gives you hai,bye

same way here he is passing ",".join(args) args = s[1:] means some list

cmd += "(" + ",".join(args) + ")" the string cmd receive the following string: "(" added of ",".join(args) added of ")"

The function join links 2 strings, in this case : "," and args. It separates all the variables in args with "," and turns it in a string.

It's the same of: cmd = cmd + "(" + ",".join(args) + ")"

if your input is "insert 0 5", the result will be: insert = insert(0,5)

This command joins cmd plus ( plus args comma separated and )

Hope you understand!

tl;dr ;) Two-liner:

l=[]
[getattr(l,s[0])(*map(int,s[1:])) if hasattr(l,s[0]) else print(l) for s in [input().split() for _ in range(int(input()))]]

For newbie like me, below is the breakdown of the code.

l=[]
for x in range(int(input())):
	s = input().split()
	if hasattr(l,s[0]):
		getattr(l,s[0]) (*map(int,s[1:]))
	else:
		print (l)
    
    
hasattr checks if the input operation to be performed is valid or not .

getattr(l,s[0]) (*map(int,s[1:]))

Here we perfom the operation on the rest of the elements in input *map is to convert the remaining input into 1,..3 format.


i'm new to python,could you explain to me how does the code process works in this code?(sorry for bad english)

for x in range(int(input())):
for this part, i know that, they'll input "12" first, resulting it to loop 12 times.

s = input("").split()
when it loops for the 1st time, they'll input "insert 0 5". then what happens afterwards? will they become ['insert','0','5']?

if hasattr(l,s[0]): #hasattr(object,name)
so, for this conditional statement, how did they identify "insert 0 5" as valid and "print" as invalid?

getattr(l,s[0]) (*map(int,s[1:]))
what does getattr(l,s[0]) do?

for this (*map(int,s[1:]), is the *args unpacking the number 0 and 5?\


Could you explain what

cmd += "("+ ",".join(args) +")"
cmd += "("+ ",".join(args) +")"
means?


It means that the sequence of the elements in args will be joined with the string ',' and have a "(" prefix and ")" suffix. Basically, if args are ['0','5'] the new string will be "(0,5)", and then all this appended to cmd by the cmd+= See https://www.tutorialspoint.com/python/string_join.htm

Slightly more concise take on this eval approach:

arg1 = input()
l = []
for _ in range(int(arg1)):
    s = input().split()
    if (s[0] != 'print'):
        eval("l.{}(".format(s[0])+','.join(s[1:])+")")
    else:
        print(l)
Also worth noting that unpacking a list with *l or a dictionary with **dict could be useful in similar problems.


Sure.

str.split() will take the string, str and use white space as a delimiter to turn the contents of str into a list of strings.

example: "so this becomes".split() = ['so','this','becomes']

The first value in each of the lists created within the for loop is a string that matches the method we wish to use. eval takes strings as input, and runs them as Python code.

example: eval("print("same")") == print("same")

The format code is taking the first element of the list, s[0], and substituting it for the "{}" contained in my eval string.

example: "{}{}{}".format("Hello"," ","World") becomes "Hello World"

','.join(list) takes each element of a list, and appends them into a string using ',' as the delimiter. the + operator here is just appending the front half of my eval statement to the back half of my eval statement.

example: ','.join(['this',' ','is',' ','nice']) becomes 'this, ,is, ,nice'

example: "l.insert(" + "1,2)" = "l.insert(1,2)"

All of these steps take advantage of methods that are built into Python's list data type. That's why we can do list.METHOD(arguments).

simpler

if __name__ == '__main__':
    N = int(raw_input())
    my_list=[]
    for x in range(N):
        args= raw_input().strip().split()
        args[1:]=map(int,args[1:])
        try:
            getattr(my_list,args[0])(*args[1:])
        except AttributeError:
            print my_list
            
            
            
            
            
 I just use eval function


n = input()
l = []
for _ in range(n):
    s = raw_input().split()
    cmd = s[0]
    args = s[1:]
    if cmd !="print":
        cmd += "("+ ",".join(args) +")"
        eval("l."+cmd)
    else:
        print l
        
        
        
        
        hey as I am new to python,can you please explain what does cmd += "("+ ",".join(args) +")" line do?
        for first command insert 0 5 cmd += "("+ ",".join(args) +")" will bring insert(0,5)
        Great!! I used

 eval('arr.{0}{1}'.format(cmd,tuple(map(int,arg))))

#instead of 

cmd += "("+ ",".join(args) +")"
    eval("l."+cmd)
            #and  It works
            
            
            I also used eval but yours is so much cleaner! Thanks!

L = []
for _ in range(0, int(raw_input())):
    user_input = raw_input().split(' ')
    command = user_input.pop(0)
    if len(user_input) > 0:
        if 'insert' == command:
            eval("L.{0}({1}, {2})".format(command, user_input[0], user_input[1]))
        else:
            eval("L.{0}({1})".format(command, user_input[0]))
    elif command == 'print':
        print L
    else:
        eval("L.{0}()".format(command))




