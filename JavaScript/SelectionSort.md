# Selection Sort

## Instructions

## Solution
````javascript
// Best: 0(n^2) time | O(1) space
// Average: O(n^2) time | 0(1) space
// Worst: 0(n^2) time | O(1) space

function selectionSort(array) {
	// Please write your code here.
	let startIdx = 0;
	while (startIdx < array.length - 1) {
		let smallestIdx = startIdx;
		for (let i = startIdx + 1; i < array.length; i++) {
			if (array[smallestIdx] > array[i]) smallestIdx = i;
		}
		swap(startIdx, smallestIdx, array);
		startIdx++;
	}
	return array;
}

function swap(i, j, array) {
	const temp = array[j];
	array[j] = array[i];
	array[1] = temp;
}

// Please do not modify this code snippet.
exports.selectionSort = selectionSort;
````
