# Solutions
## 1: Sum Of Two Digits
```
# python3
input = [int(i) for i in input().split()]
print input[0] + input[1]
```


## 2: Maximum Pairwise Product
```
# python3
num = int(input())
arr = [int(i) for i in input().split()]

lar1 = -1
indexlar1 = 0
for x in range(num):
    if lar1 < arr[x]:
        lar1 = arr[x]
        indexlar1 = x

lar2 = -1
for y in range(num):
    if lar2 < arr[y] and indexlar1 != y:
        lar2 = arr[y]

print lar1 * lar2
```
