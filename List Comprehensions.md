Let's learn about list comprehensions! You are given three integers  and  representing the dimensions of a cuboid along with an integer . You have to print a list of all possible coordinates given by  on a 3D grid where the sum of  is not equal to . Here, 

Input Format

Four integers  and  each on four separate lines, respectively.

Constraints

Print the list in lexicographic increasing order.

Sample Input 0

1
1
1
2
Sample Output 0

[[0, 0, 0], [0, 0, 1], [0, 1, 0], [1, 0, 0], [1, 1, 1]]
Explanation 0

Concept

You have already used lists in previous hacks. List comprehensions are an elegant way to build a list without having to use different for loops to append values one by one. This example might help.

Example: You are given two integers x and y . You need to find out the ordered pairs ( i , j ) , such that ( i + j ) is not equal to n and print them in lexicographic order.( 0 <= i <= x ) and ( 0 <= j <= y) This is the code if we dont use list comprehensions in Python.

python x = int ( raw_input()) y = int ( raw_input()) n = int ( raw_input()) ar = [] p = 0 for i in range ( x + 1 ) : for j in range( y + 1): if i+j != n: ar.append([]) ar[p] = [ i , j ] p+=1 print ar
Other smaller codes may also exist, but using list comprehensions is always a good option. Code using list comprehensions:

python x = int ( raw_input()) y = int ( raw_input()) n = int ( raw_input()) print [ [ i, j] for i in range( x + 1) for j in range( y + 1) if ( ( i + j ) != n )]

আমাদেরকে লিস্টের ব্যাপারে কিছু ব্যাপার মাথায় রাখতে হবে।

লিস্ট কম্প্রিহেনশনে অবশ্যই সবার প্রথমে এবং সবার শেষে থার্ড ব্র্যাকেট দিতে হবে।

লিস্টের ভেতরে কী থাকবে সেটা বলে দেওয়ার সময় এটা মনে রাখা উচিত যে লিস্টের ভেতরের এলিমেন্টগুলো কমার মাধ্যমে একে অপরের সাথে ৃথক থাকে। সোআলাদা করে তাদের মাঝে কমা দেওয়ার চিন্তা করতে হবে না 

এবার  আসি ভেতরের এলিমেন্ট গুলো কীভাবে ডিক্লেয়ার করবো, তা নিয়ে...


ভেতরের একটি এলিমেন্ট কী হবে সেটাই জাস্ট মাথায় রাখতে হবে 
এটা যদি জাস্ট একতা ভ্যারিয়েবল হয়, তাহলে সবার প্রথমে তা-ই লিখতে হবে, তারপরে লিখতে হবে কন্ডিশন (যদি থাকে)ঃ

a=[j for i in range(3)]
output: [0,1,2]

for conditional statements:

[i for i in range(10) if i%2==0]
>> [0,2,4,6,8]


এবার আউটপুট যদি লিস্ট হয়,তাহলে সবার প্রথমে লিস্টই জেনারালাইজ করে লিখতে হবে 

[[i,j,k] for i in range(ii+1) for j in range(jj+1) for k in range(kk) if i+j+k<=s]
>>[[0, 0, 0], [0, 1, 0], [1, 0, 0], [1, 1, 0]]


Remember, এখানে লুপে কোলন দেওয়ার কোনও প্রয়োজন নাই। 




#### solutions:

## 1

```python
x, y, z, n = int(input()), int(input()), int(input()), int(input())
print ([[a,b,c] for a in range(x+1) for b in range(y+1) for c in range(z+1) if a + b + c != n ])
```
## 2
```python
x, y, z, n = (int(raw_input())+1 for _ in range(4))
print [[a,b,c] for a in range(x) for b in range(y) for c in range(z) if a+b+c!=n-1]
```
## 3
As an alternative, to avoid multiple for loops you can use product:
```python
combinations = list(product(range(x+1), range(y+1), range(z+1)))
print([list(a) for a in combinations if sum(a) != n])
```
## 4 (by creating a list )
```python
listijk = []
for i in range(x + 1):
    for j in range (y + 1):
        for k in range (z + 1):
            if i + j + k != n: #before printing the result, it will exclude the output which 'i' + 'j' + 'k' is the same as 'n'.
                listijk.append([i,j,k])
print(listijk)

```
## 5
```python
print([[i,j,k] for i in range(x+1) for j in range(y+1) for k in range(z+1) if sum([i,j,k]) != n])
```
## 6 naieve solution

```python
X = int(raw_input())
Y = int(raw_input())
Z = int(raw_input())
N = int(raw_input())

Xi = [x for x in range(X+1)]
Yi = [y for y in range(Y+1)]
Zi = [z for z in range(Z+1)]

results = []
for x in Xi:
    for y in Yi:
        for z in Zi:
            if x + y + z != N:
                results.append([x,y,z])
print results
```
## 7
```python
cuboid = []

results = [cuboid.append([x, y, z]) for x in range(X+1) for y in range(Y+1) for z in range(Z+1) if x + y + z != N]

print(cuboid)
```
## 8
```python
if __name__ == '__main__':
    x = int(input())
    y = int(input())
    z = int(input())
    n = int(input())

    from itertools import product
    print([list(p) for p in product(range(x + 1), range(y + 1), range(z + 1)) if sum(p) != n])
```
