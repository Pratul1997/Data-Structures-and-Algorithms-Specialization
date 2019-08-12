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
```
# python3
def maxcommonsequence(X , Y): 
    arr = [[None]*(len(Y)+1) for i in range(len(X)+1)] 

    for i in range(len(X)+1): 
        for j in range(len(Y)+1): 
            if i == 0 or j == 0 : 
                arr[i][j] = 0
            elif X[i-1] == Y[j-1]: 
                arr[i][j] = arr[i-1][j-1]+1
            else: 
                arr[i][j] = max(arr[i-1][j] , arr[i][j-1]) 
  
    return arr[-1][-1]


nx = int(input())
X = [int(i) for i in input().split()]
ny = int(input())
Y = [int(i) for i in input().split()]

print (maxcommonsequence(X, Y))
```


## 5: Longest Common Subsequence of Three Sequences
```
# python3
def maxcommonsequence(X, Y, Z): 
	lenX=len(X)
	lenY=len(Y)
	lenZ=len(Z)
	L = [[[0 for i in range(lenZ+1)] for j in range(lenY+1)] for k in range(lenX+1)] 

	for i in range(lenX+1): 
		for j in range(lenY+1): 
			for k in range(lenZ+1): 
				if (i == 0 or j == 0 or k == 0): 
					L[i][j][k] = 0
					
				elif (X[i-1] == Y[j-1] and  X[i-1] == Z[k-1]): 
					L[i][j][k] = L[i-1][j-1][k-1] + 1

				else: 
					L[i][j][k] = max(max(L[i-1][j][k], L[i][j-1][k]), L[i][j][k-1]) 

	return L[-1][-1][-1] 

nx=int(input())
X=[int(i) for i in input().split()]
ny=int(input())
Y=[int(i) for i in input().split()]
nz=int(input())
Z=[int(i) for i in input().split()]

print(maxcommonsequence(X, Y, Z))
```
