# Solutions

## 1: Money Change
```
# python3
m = int(input())
count = 0
count += int(m // 10)
m = m % 10
count += int(m // 5) + m % 5
print (count)
```

## 2: Maximum Value of the Loot
```
# python3
(n, W) = [int(i) for i in input().split()]
vlbywt = []
wt = []
for x in range(n):
    (v, w) = [int(i) for i in input().split()]
    vlbywt.append(v / w)
    wt.append(w)
totalcost = 0
for x in range(n):
    mval = -1
    mvalindex = -1
    for y in range(n):
        if vlbywt[y] > mval:
            mval = vlbywt[y]
            mvalindex = y
    takeval = min(W, wt[mvalindex])
    totalcost += takeval * vlbywt[mvalindex]
    vlbywt[mvalindex] = -1
    W -= takeval
    if W == 0:
        break
print(totalcost)
```

## 3: Maximum Aadvertisement Revenue
```
# python3
n = int(input())
ad = [int(i) for i in input().split()]
cost = [int(i) for i in input().split()]
ad.sort()
cost.sort()
maxprofit = 0
for x in range(n):
    maxprofit += ad[x] * cost[x]
print(maxprofit)
```

## 4: Collecting Signatures


## 5: Maximum Number of Prizes
```
# python3
number = int(input())
arr = []
i = 1
while True:
    if number - i >= 0:
        number -= i
        arr.append(i)
        i += 1
    else:
        arr[len(arr) - 1] += number
        break
print(len(arr))
for x in range(len(arr)):
    print(arr[x], end=' ')
```

## 6: Maximum Salary
```
# python3
n = int(input())
arr = input().split()
out = ''

def IsGreaterOrEqual(digit, max_digit):
    return int(digit + max_digit) >= int(max_digit + digit)

for x in range(len(arr)):
    mval = arr[0]
    index = -1
    for y in range(len(arr)):
        if IsGreaterOrEqual(arr[y], mval):
            mval = arr[y]
            index = y
    arr[index] = '0'
    out += mval
print(int(out))
```
