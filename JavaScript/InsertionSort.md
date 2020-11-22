# Insertion Sort

## Instruction

## Solution
````javascript
// Best: O(n) time | O(1) space
// Average: 0(n^2) time | O(1) space
// Worst: O(n^2) time | O(1) space

function insertionSort(array) {
	// Please write your code here.
	for (let i = 1; i < array.length; i++) {
		let j = i;
		while (j > 0 && array[j] < array[j - 1]) {
			swap(j, j - 1, array);
			j -= 1;
		}
	}
	return array;
}

function swap(i, j, array) {
	const temp = array[j];
	array[j] = array[i];
	array[i] = temp;
}

// Please do not modify this code snippet.
exports.insertionSort = insertionSort;
````
