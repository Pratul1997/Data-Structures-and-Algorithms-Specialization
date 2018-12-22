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
## 4: Least Common Multiple
## 5: Fibonacci Number Again
## 6: Last Digit Of The Sum Of Fibonacci Numbers
## 7: Last Digit Of The Sum Of Fibonacci Numbers Again
## 8: Last Digit Of The Sum Of Squares Of Fibonacci Numbers
