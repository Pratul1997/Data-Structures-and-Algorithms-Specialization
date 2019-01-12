# Solutions

## 1: Money Change
```
m = int(input())
count = 0
count += int(m // 10)
m = m % 10
count += int(m // 5) + m % 5
print (count)
```
