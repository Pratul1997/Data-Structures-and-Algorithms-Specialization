# Solutions

## 1: Maximum Amount of Gold
```
# python3
(W, n) = [int(i) for i in input().split()]
arr = [int(i) for i in input().split()]
dp = [[0 for x in range(W + 1)] for y in range(n + 1)]

for x in range(1, n + 1):
    for y in range(1, W + 1):
        if arr[x - 1] <= y:
            dp[x][y] = max(arr[x - 1] + dp[x - 1][y - arr[x - 1]],dp[x - 1][y])
        else:
            dp[x][y] = dp[x - 1][y]
print(dp[-1][-1])
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
