# Solution

## 1: Binary Search
```
# python3
nums = [int(i) for i in input().split()][1:]
check = [int(k) for k in input().split()][1:]

for x in range(len(check)):
    target=check[x]
    start = 0
    end = len(nums)
    forendloop = 0
    flag=False
    while end - start > 0:
        mid = (start + end) // 2
        if nums[mid] == target:
            print(mid, end=' ')
            flag=True
            break
        elif nums[mid] < target:
            start = mid
        elif nums[mid] > target:
            end = mid
        if end - start == 1:
            forendloop += 1
            if forendloop == 2:
                break
    if(flag==False):
        print(-1, end=' ')
```



## 2: Majority Element
```
# python3
n=int(input())
arr=[int(i) for i in input().split()]
if n == 1:
    print (1)
else:
    if n % 2 == 1:
        mid = (n - 1) // 2
    else:
        mid = n // 2

    di = dict()
    flag = False
    for x in range(n):
        if arr[x] in di:
            di[arr[x]] += 1
        else:
            di[arr[x]] = 1
        if di[arr[x]] > mid:
            print (1)
            flag = True
            break
    if not flag:
        print (0)
```

## 3: Improving Quicksort


## 4: Number of Inversions


## 5: Organizing a Lottery



## 6: Closest Points
