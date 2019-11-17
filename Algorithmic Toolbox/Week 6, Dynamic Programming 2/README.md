# Solutions

## 1: Maximum Amount of Gold
```
```

## 2: Partitioning Souvenirs
```
# python3
n = int(input())
arr = [int(i) for i in input().split()]
tot_sm = sum(arr)

def check(index, tot):
    if index == len(arr):
        if tot[0] == tot[1] and tot[0] == tot[2]:
            return True
        else:
            return False
    else:
        ans = False
        for x in range(3):
            tot[x] += arr[index]
            if not tot[x] > tot_sm // 3:
                ans = ans or check(index + 1, tot)
            tot[x] -= arr[index]
        return ans


val = check(0, [0, 0, 0])
if(val):
    print(1)
else:
    print(0)
```

# 3: Maximum Value of an Arithmetic Expression
```
```
