# Solutions

## 1: Phone book
```
# python3
times = int(input())
di = dict()
for _ in range(times):
    inp = input().split()
    if inp[0] == 'add':
        di[inp[1]] = inp[2]
    elif inp[0] == 'find':
        if inp[1] in di and not di[inp[1]] == -1:
            print (di[inp[1]])
        else:
            print ('not found')
    else:
        if inp[1] in di:
            di[inp[1]] = -1
```

## 2: Hashing with chains
```
```

## 3: Find pattern in text
```
```

## 4: Substring equality
```
```

## 5: Longest common substring
```
```

## 6: Pattern matching with mismatches
```
```
