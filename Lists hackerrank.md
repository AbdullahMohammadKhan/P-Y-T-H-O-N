



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
        print(result)if __name__ == '__main__':
    
```python


