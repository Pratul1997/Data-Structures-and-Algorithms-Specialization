# Solutions

## 1: Checking Consistency of CS Curriculum
```
# python3
(no_vertex, no_edges) = [int(i) for i in input().split()]
graph = []

for _ in range(no_vertex + 1):
    graph.append([])

for _ in range(no_edges):
    (a, b) = [int(i) for i in input().split()]
    graph[a].append(b)

removed = [True] * (no_vertex + 1)

def ccircle(host, fixedx):
    for x in range(len(graph[host])):
        nxt = graph[host][x]
        if nxt in fixedx:
            return True
        if removed[nxt] == True:
            cond = ccircle(nxt, fixedx + [nxt])
            if cond == True:
                return True
    removed[host] = False
    
flag = False
while sum(removed) > 1:
    for x in range(1, len(removed)):
        if removed[x] == True:
            out = ccircle(x, [x])
            if out == True:
                flag = True
                break
    if flag == True:
        break

if flag == True:
    print (1)
else:
    print (0)
```

## 2: Determining an Order of Courses
```
# python3
(no_vertex, no_edges) = [int(i) for i in input().split()]
graph = []

for _ in range(no_vertex + 1):
    graph.append([])

for _ in range(no_edges):
    (a, b) = [int(i) for i in input().split()]
    graph[a].append(b)

removed = [True] * (no_vertex + 1)

pk = []

def ccircle(host, fixedx):
    for x in range(len(graph[host])):
        nxt = graph[host][x]
        if removed[nxt] == True:
            cond = ccircle(nxt, fixedx + [nxt])
    removed[host] = False
    pk.append(host)

while sum(removed) > 1:
    for x in range(1, len(removed)):
        if removed[x] == True:
            out = ccircle(x, [x])
            
for x in range(len(pk)):
    print(pk[len(pk)-1-x], end=' ')
```

## 3: Checking Whether Any Intersection in a City is Reachable from Any Other
```
```
