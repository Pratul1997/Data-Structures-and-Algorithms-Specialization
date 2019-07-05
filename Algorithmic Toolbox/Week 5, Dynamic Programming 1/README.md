# Solutions
## 1: Money Change Again
```
# python3
n = int(input())
arr = [0]
for x in range(1, n + 1):
    if x >= 4:
        arr.append(min(arr[x - 1] + 1, arr[x - 3] + 1, arr[x - 4] + 1))
    elif x >= 3:
        arr.append(min(arr[x - 1] + 1, arr[x - 3] + 1))
    else:
        arr.append(arr[x - 1] + 1)

print(arr[-1])
```

## 2: Primitive Calculator
```
# python3
n = int(input())
arr = [0]
index = [0]
for x in range(1, n + 1):
    if x % 3 == 0 and x % 2 == 0:
        arr.append(min(arr[x // 3] + 1, arr[x // 2] + 1, arr[x - 1]
                   + 1))
    elif x % 3 == 0:
        arr.append(min(arr[x // 3] + 1, arr[x - 1] + 1))
    elif x % 2 == 0:
        arr.append(min(arr[x // 2] + 1, arr[x - 1] + 1))
    else:
        arr.append(arr[x - 1] + 1)

    if arr[-1] == arr[x // 3] + 1:
        index.append(x // 3)
    elif arr[-1] == arr[x // 2] + 1:
        index.append(x // 2)
    else:
        index.append(x - 1)
print(arr[-1]-1)

out = ''
id = len(index) - 1
while not id == 0:
    out = str(id) + ' ' + out
    id = index[id]
print(out)
```

## 3: Edit Distance


## 4: Longest Common Subsequence of Two Sequences



## 5: Longest Common Subsequence of Three Sequences
