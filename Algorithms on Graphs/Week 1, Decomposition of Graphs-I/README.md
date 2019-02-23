# Solutions

## 1: Finding an Exit from a Maze
```
# python3
def dfs(num):
    check[num] = True
    for x in range(len(graph[num])):
        if check[graph[num][x]] == False:
            dfs(graph[num][x])

(no_vertex, no_edges) = [int(i) for i in input().split()]
graph = []
for toaddvertex in range(no_vertex + 1):
    graph.append([])

for _ in range(no_edges):
    (a, b) = [int(i) for i in input().split()]
    graph[a].append(b)
    graph[b].append(a)
(fm, to) = [int(i) for i in input().split()]

check = [False]
check += [False] * no_vertex

dfs(fm)
if(check[to]):
    print(1)
else:
    print(0)
```

## 2: Adding Exits to a Maze
```
# python3
def dfs(num):
    check[num] = True
    for x in range(len(graph[num])):
        if check[graph[num][x]] == False:
            dfs(graph[num][x])

(no_vertex, no_edges) = [int(i) for i in input().split()]
graph = []
for toaddvertex in range(no_vertex + 1):
    graph.append([])

for _ in range(no_edges):
    (a, b) = [int(i) for i in input().split()]
    graph[a].append(b)
    graph[b].append(a)

check = [False]
check += [False] * no_vertex
count = 0
for y in range(1, len(check)):
    if check[y] == 0:
        count += 1
        dfs(y)
                
print(count)
```
