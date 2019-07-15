# Solutions
## 1: Construct a Trie from a Collection of Patterns
* Solved Using Dictionary
```
# python3
def build_trie(patterns):
    tree = dict()
    tree[0] = {}
    nodeNumber = 1
    for pattern in patterns:
        currentNode = 0
        for c in pattern:
            if c not in tree[currentNode]:
                tree[currentNode][c] = nodeNumber
                tree[nodeNumber] = {}
                nodeNumber += 1
            currentNode = tree[currentNode][c]
    return tree

n=int(input())
patterns=[]
for x in range(n):
    ip=input()
    patterns.append(ip)
tree = build_trie(patterns)
for node in tree:
    for c in tree[node]:
        print("{}->{}:{}".format(node, tree[node][c], c))
```
* Solved using Node
```
# python3
class Node:
    def __init__(self, val, edge, children):
        self.val = val
        self.edge= edge
        self.children = children
    

def p_nt(root):
    if(len(root.children)>0):
        for x in range(len(root.children)):
            print('{}->{}:{}'.format(root.val,root.children[x].val,root.children[x].edge))
            p_nt(root.children[x])
            
def formation(root, allstring):
    count=1
    for st in allstring:
        travel=root
        for st_t in range(len(st)):
            flag=False
            for nd in range(len(travel.children)):
                if(travel.children[nd].edge==st[st_t]):
                    travel=root.children[nd]
                    flag=True
                    break
            if(flag==False):
                temp=Node(count,st[st_t],[])
                count+=1
                travel.children.append(temp)
                travel=temp
            
        
    p_nt(root)
    
n=int(input())
astr=[]
for x in range(n):
    ip=input()
    astr.append(ip)

root=Node(0,0,[])
formation(root,astr)
```

## 2: Implement TrieMatching
```
# python3
class Node:
    def __init__(self):
        self.next = {}
        self.isLeaf = False

def solve(text, n, patterns):
    root = Node()
    for pattern in patterns:
        currentNode = root
        for x in range(len(pattern)):
            if pattern[x] not in currentNode.next:
                currentNode.next[pattern[x]] = Node()
            if x == len(pattern) - 1:
                currentNode.next[pattern[x]].isLeaf = True
            else:
                currentNode = currentNode.next[pattern[x]]

    return check(root)

def check(root):
    result = []
    for i in range(len(text)):
        index = i
        currentNode = root
        while index < len(text):
            c = text[index]
            if c not in currentNode.next:
                break
            currentNode = currentNode.next[c]
            if currentNode.isLeaf:
                result.append(i)
                break
            index += 1

    return result

text = input().strip()
n = int(input())
patterns = []
for i in range(n):
    patterns += [input().strip()]

ans = solve(text, n, patterns)
print (' '.join(map(str, ans)))
```

## 3: Extend TrieMatching 
```
Same as Implement TrieMatching
```

## 4: Construct the Suffix Tree of a String 

## 5: Find the Shortest Non-Shared Substring of Two Strings 
