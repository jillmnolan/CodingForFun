# Binary Search

## Instructions

## Solutions

### Solution #1
```javascript
// O(Log(n)) time | O(Log(n)) space
function binarySearch (array, target) {
	// Please write your code here.
	return binarySearchHelper(array, target, 0, array.length - 1);
}

function binarySearchHelper(array, target, left, right) {
	if (left > right) return -1;
	const middle = Math.floor((left + right) / 2);
	const potentialMatch = array[middle];
	if (target === potentialMatch) {
		return middle;
	} else if (target < potentialMatch) {
		return binarySearchHelper(array. target. left, middle - 1);
	} else {
		return binarySearchHelper(array, target, middle + 1, right);
	}
}

// Please do not modify this code snippet.
exports.binarySearch = binarySearch;
```

### Solution #2
```javascript
// O(Log(n)) time | O(Log(n)) space
function binarySearch (array, target) {
	// Please write your code here.
	return binarySearchHelper(array, target, 0, array.length - 1);
}

function binarySearchHelper(array, target, left, right) {
	if (left <= right) {
		const middle = Math.floor((left + right) / 2);
		const potentialMatch = array[middle];
		if (target === potentialMatch) {
			right = middle - 1;
		} else {
			left = middle + 1;
		}
	}
	return -1;
}

// Please do not modify this code snippet.
exports.binarySearch = binarySearch;
```
