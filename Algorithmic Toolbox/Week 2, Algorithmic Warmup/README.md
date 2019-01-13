# Solution
## 1: Fibonacci Number
```
# python3
num = int(input())
a0 = 0
a1 = 1
a2 = 0
if num >= 2:
    for x in range(num - 1):
        a2 = a1 + a0
        a0 = a1
        a1 = a2
    print (a2)
else:
    print (num)
```
## 2: Last Digit Of Fibonacci Number
```
# python3
num = int(input())
a0 = 0
a1 = 1
a2 = 0
if num >= 2:
    for x in range(num - 1):
        a2 = a1 + a0
        a2 = a2 % 10
        a0 = a1
        a1 = a2
    print (a2)
else:
    print (num)
```
## 3: Greatest Common Divisor
```
# python3
num1 , num2 = [int(i) for i in input().split()]
if num2 > num1:
    (num1, num2) = (num2, num1)
while num2 != 0:
    (num1, num2) = (num2, num1 % num2)
print (num1)
```
## 4: Least Common Multiple
```
# python3
num1 , num2 = [int(i) for i in input().split()]
product = num1 * num2
if num2 > num1:
    (num1, num2) = (num2, num1)
while num2 != 0:
    (num1, num2) = (num2, num1 % num2)
print (int(product // num1))
```
## 5: Fibonacci Number Again
```
# python3
(n, m) = [int(i) for i in input().split()]
a0 = 0
a1 = 1
a2 = 0
if n > 0 and m > 0:
    count = 0
    while True:
        a2 = a1 + a0
        a0 = a1
        a1 = a2
        count = count + 1
        if a0 % m == 0 and a2 % m == 1:
            break
    n = n % count
    a0 = 0
    a1 = 1
    last = 0
    if n >= 2:
        for x in range(n - 1):
            last = a1 + a0
            a0 = a1
            a1 = last
    elif n == 1:
        last = 1
    elif n == 0:
        last = 0
    print (last % m)
```
## 6: Last Digit Of The Sum Of Fibonacci Numbers
```
# python3
n = int(input())
a0 = 0
a1 = 1
a2 = 0
n += 2
m = 10
if n > 0:
    count = 0
    while True:
        a2 = a1 + a0
        a0 = a1
        a1 = a2
        count = count + 1
        if a0 % m == 0 and a2 % m == 1:
            break
    n = n % count
    a0 = 0
    a1 = 1
    last = 0
    if n >= 2:
        for x in range(n - 1):
            last = a1 + a0
            a0 = a1
            a1 = last
    elif n == 1:
        last = 1
    elif n == 0:
        last = 0
    if last % m == 0:
        print (9)
    else:
        print (last % m - 1)
```
## 7: Last Digit Of The Sum Of Fibonacci Numbers Again
```
# python3
def lastsum(n):
    a0 = 0
    a1 = 1
    a2 = 0
    n += 2
    m = 10
    if n > 0:
        count = 0
        while True:
            a2 = a1 + a0
            a0 = a1
            a1 = a2
            count = count + 1
            if a0 % m == 0 and a2 % m == 1:
                break
        n = n % count
        a0 = 0
        a1 = 1
        last = 0
        if n >= 2:
            for x in range(n - 1):
                last = a1 + a0
                a0 = a1
                a1 = last
        elif n == 1:
            last = 1
        elif n == 0:
            last = 0

        if last % m == 0:
            return 9
        else:
            return last % m - 1


(num1, num2) = [int(i) for i in input().split()]
last_num2 = lastsum(num2)
last_num1 = lastsum(num1 - 1)
if last_num2 >= last_num1:
    print (last_num2 - last_num1)
else:
    print (last_num2 + 10 - last_num1)
```
## 8: Last Digit Of The Sum Of Squares Of Fibonacci Numbers
