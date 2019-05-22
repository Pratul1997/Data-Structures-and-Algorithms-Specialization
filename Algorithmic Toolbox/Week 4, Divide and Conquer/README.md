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
```
# python3
n = int(input())
srt = [int(i) for i in input().split()]
count = 0

def MergeSort(arr):
    if len(arr) == 1:
        return arr
    mid = len(arr) // 2
    L = MergeSort(arr[:mid])
    R = MergeSort(arr[mid:])
    O = Merge(L, R)
    return O

def Merge(L, R):
    i = 0
    j = 0
    out = []
    global count
    while i < len(L) and j < len(R):
        if L[i] <= R[j]:
            out.append(L[i])
            i += 1
        else:
            out.append(R[j])
            count += len(L) - i
            j += 1
    if i == len(L):
        while j < len(R):
            out.append(R[j])
            j += 1
    else:
        while i < len(L):
            out.append(L[i])
            i += 1
    return out

MergeSort(srt) 
print(count)
```


## 5: Organizing a Lottery



## 6: Closest Points
