# Find Closest Value in BST

## Instructions

Write a function that takes in a Binary Search Tree (BST) and a target integer value and returns the closest value to the target value contained in the BST.  You can assume that there will only be one closest value.  Each ```BST``` node has an integer ```value```, a ```left``` child node, and a ```right``` child node.  A node is said to be a valid ```BST``` node if and only if it satisifes the ```BST``` property.  Its ```value``` is strictly greater than the values of every node to its left; its ```value``` ia less than or equal to the values of every node to its right; and its children nodes are either valid ```BST``` nodes themeselves or ```None``` / ```null```.

``` 
// Sample Input

tree = 10

target = 12

// Sample Output

13
```

Try traversing the BST node by node, all the while keeping track of the node with the value closest to the target value.  Calculating the absolute value of the difference between a node's value and the target value should allow you to check if that node is closer than the closest one.  Make use of the BST property to determine what side of any given node has values close to the target value and is therefore worth exploring.  What are the advantages and disadvantages of solving this problem iteratively as opposed to recursively?

```
Average: O(log(n)) time | O(1) space - where n is the number of nodes in the BST
Worst: O(n) time | O(1) space - where n is the number of nodes in the BST
```

## Solutions

### Solution #1

```
function findClosestValueInBst(tree, target) {
	return findClosestValueInBstHelper(tree, target, tree.value);
}

function findClosestValueInBstHelper(tree, target, closest) {
	if (tree === null) return closest;
	if (Math.abs(target - closest) > Math.abs(target - tree.value)) {
		closest = tree.value;
	}
	if (target < tree.value) {
		return findClosestValueInBstHelper(tree.left, target, closest);
	} else if (target > tree.value) {
		return findClosestValueInBstHelper(tree.right, target, closest);
	} else {
		return closest;
	}
}

// This is the class of the input tree.
class BST {
	constructor(value) {
		this.value = value;
		this.left = null;
		this.right = null;
	}
}


// Please do not modify this line.
exports.findClosestValueInBst = findClosestValueInBst;
```

```
function findClosestValueInBst(tree, target) {
	return findClosestValueInBstHelper(tree, target, tree.value);
}

function findClosestValueInBstHelper(tree, target, closest) {
	let currentNode = tree;
	while (currentNode !== null) {
		if (Math.abs(target - closest) > Math.abs(target - currentNode.value)) {
			closest =currentNode.value;
		}
		if (target < currentNode.value) {
			currentNode = currentNode.left;
		} else if (target > currentNode.value) {
			currentNode = currentNode.right;
		} else {
			break;
		}
	}
	return closest;
}

// This is the class of the input tree.
class BST {
	constructor(value) {
		this.value = value;
		this.left = null;
		this.right = null;
	}
}


// Please do not modify this line.
exports.findClosestValueInBst = findClosestValueInBst;
```
