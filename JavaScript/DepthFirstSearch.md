# Depth-first Search

## Instructions

You are given a ```Node``` class that has a ```name``` and an array of optional ```children``` nodes.  When put together, nodes form an acyclic tree-like structure.  Implement the ```depthFirstSearch``` method on the ```Node``` class, which takes in an empty array, traverses the tree using the Depth-first Search approach (specifically navigating the tree from left to right), stores all of the nodes' names in the input array, and returns it.  **If you are unfamiliar with Depth-first Search approach (specifically navigating the tree from left to right), stores all of the nodes' names in the input array, and returns it.**

```javascript
// Sample input


// Sample Output
["A", "B", "E", "F", "I", "J", "C", "D", "G", "K", "H"]

```
The Depth-first Search algorithm works by traversing a graph branch.  In other words, before traversing any Node's sibling Nodes, its children nodes must be traversed.  How can you simply and effectively keep track of Nodes' sibling Nodes as you traverse them, all while  retaining the order in which you must traverse them?  Start at the root Node and try simply calling the depthFirstSearch method on all of its children Nodes. Then, call the depthFirstSearch method on all children Nodes of each child node. keepapplying this
logic until the entire graph has been traversed. Do not forget to add the current Node's name to the input array at every call of depthFirstSearch.  For the purpose of this question, a ```graph``` is represented by a list of ```nodes``` and a ```startNode` node. Every node has to have a unique string ```id``` that will be referenced by other nodes' list of ```children``` and by the ```startNode```.  The searching function will be called on the ```startNode```.  Please be advised that your graph should not have cycles.

## Solution

```javascript
// Please do not modify the Node class, with the only exception being the depthFirstSearch method.
class Node {
	constructor(name) {
		this.name = name;
		this.children = [];
	}
	addChild(name) {
		this.children.push(new Node(name));
		return this;
	}
	// O(v + e) time | O(v) space, where v is the number of vertices of the input graph,
  	// and e is the number of edges of the input graph.
	depthFirstSearch(array) {
		// Write your code here...
		array.push(this.name);
		for (const child of this.children) {
			child.depthFirstSearch(array);
		}
		return array;
	}
}

// Please do not modify this line
exports.Node = Node;
```
