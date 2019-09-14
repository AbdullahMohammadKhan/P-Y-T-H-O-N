### 1

x, y, z, n = int(input()), int(input()), int(input()), int(input())

Looks good, but to avoid those repetitive input calls ( means the 'int(input())' terms) you could do something like:

## 2

x, y, z, n = (int(input()) for _ in range(4))
why you use range(4)?
This expression is used for reducing the repetitive statements in reading the inputs from console.
range(x,y) will create a range of elements from x to y-1 if only one parameter is passed x is assumed to be 0 so range(y) will create elements in range from 0 till y-1

so here range(4) will create a range which includes 0,1,2,3 hence the loop will iterate 4 times as there are 4 elements

is there any reason for using '_' as the dummy variable? What's wrong with using letter, for example 'i'?
_ is used to signify that even though something is being returned, we don't plan to use that variable any where.
It just like a while loop (Ex: while(a<5)) . If we need to store in the seperte varible you can use like this x,y,z,a = (int(input()) for n in range(4). It will be stored seperatly
## 3
in py2 can be w/o int()

x,y,z,n = [input() for i in range(4)]

## 4
x, y, z, n = (int(raw_input())+1 for _ in range(4))
**raw_input() was renamed to input() in python 3
