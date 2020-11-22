Node Depths

The distance between a node in the Binary Tree and the tree's root is called the node's
depth.  Write a function that takes in a Binary Tree and returns the sum of its nodes' depths.

Each ```BinaryTree``` node has an integer ```value```, a ```left``` child node, and a ```right``` child node.  Children nodes can either be ```BinaryTree``` themselves or ```None``` / ```null```.

```javascipt
// Sample Input
tree =

// Sample Output

16
// The depth of the node with value 2 is 1.
// The depth of the node with value 3 is 1.
// The depth of the node with value 4 is 2.
// The depth of the node with value 5 is 2.
// Summing all of these depths equates to 16.
```

To solve this question, think how to compute the depth of any given node.  Once we know how to do so, we can compute all of the depths and add them up to obtain the desired output.  To compute the depth of a given node, one need information about its position in the tree.  Can you pass this information down from the node's parent?  The depth of any node in the tree is equal to the depth of its parent node plus 1.  By starting at the root node whose depth is 0,  we can pass down to every node in the tree its respective depth, and you can implement the algorithm that does this and that sum up all of the depths  either recursively or iteratively.

Please note that **Binary Tree** is represented by a list of ```nodes``` and a ```root``` node.  Every node has to have a unique string ```id``` that will be referenced by other nodes' ```left``` and ```right```pointers and by the ```root```.

### Solution #1
```javascript
// Average case: when the tree is balanced.
// O(n) time | O(h) space - where n is the number of nodes in the
// Binary Tree and h is the height of the Binary Tree.

function nodeDepths(root) {
	// Write your code here...
	let sumOfDepths = 0;
	const stack = [{node: root, depth: 0}]
	while (stack.length > 0) {
		const (node, depth) = stackpop();
		if (node === null) continue;
		sumOfDepths += depth;
		stack.push({node: node.left, depth: depth + 1});
		stack.push({node: node.right, depth: depth + 1});
	}
	return sumOfDepths;
}

// This is the class of the input binary tree.
class BinaryTree {
	constructor(value) {
		this.value = value;
		this.left = null;
		this.right = null;
	}
}

// Please do not modify this code snippet.
exports.nodeDepths = nodeDepths;
```

### Solution #2
```javascript
// Average case: when the tree is balanced.
// O(n) time | O(h) space - where n is the number of nodes in the
// Binary Tree and h is the height of the Binary Tree.

function nodeDepths(root, depth = 0) {
	// Write code here.
	if (root === null) return 0;
	return depth + nodeDepths(root.left, depth + 1) + nodeDepths(root.right, depth + 1);
}

// This is the class of the input binary tree.
class BinaryTree {
	constructor(value) {
		this.value = value;
		this.left = null;
		this.right = null;
	}
}

// Please do not modify this code snippet.
exports.nodeDepths = nodeDepths;
```
