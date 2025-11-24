# Ex. No: 15E - Build and Evaluate an Expression Tree

## AIM:
To write a Python program to build and evaluate the given Expression tree.

---

## ALGORITHM:

1. **Start the program.**
2. Create nodes for operators and operands.
3. Build the expression tree by connecting nodes in the correct hierarchical structure.
4. Define a recursive function `evaluate(root)`:
   - If the node is a number (leaf), return it.
   - Else, recursively evaluate left and right subtrees.
   - Apply the operator at the current node to the results.
5. Return the final result from the root node.
6. **End the program.**

---

## PROGRAM:

```
class Node:
    def __init__(self, val, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def isLeaf(node):
    return node.left is None and node.right is None
 
def process(op, x, y):
    if op == '+':
        return x + y
    if op == '-':
        return x - y
    if op == '*':
        return x * y
    if op == '/':
        return x / y
 
def evaluate(root):
 # Write your code here
 

    if root is None:
        return 0
  
    if isLeaf(root):
        return float(root.val)
    
    x = evaluate(root.left)
    y = evaluate(root.right)
    return (process(root.val, x, y))

root = Node('+')
root.left = Node('*')
root.right = Node(3)
root.left.left = Node(4)
root.left.right = Node(8)
print('The value of the expression tree is',evaluate(root))
```

## OUTPUT:
<img width="812" height="131" alt="image" src="https://github.com/user-attachments/assets/b878cb03-dc93-4e70-8821-b4ea4623a8cd" />


## RESULT:
Thus, a Python program to build and evaluate the given Expression tree was implemented successfully.

