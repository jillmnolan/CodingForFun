# Product Sum

# Instructions

# Solution
```javascript
// Use the Array.isArray function to check whether an item is a list or an integer.
// O(n) time | O(d) space, whereby n is the total number of elements in the array, which
// includes subelements, and d is the greatest depth of "special" arrays in the array.

function productSum(array, multiplier = 1) {
	// Please write your code here.
	let sum = 0;
	for (const element of array) {
		if (Array.isArray(element)) {
			sum += productSum(element, multiplier + 1);
		} else {
			sum += element;
		}
	}
	return sum * multiplier;
}

// Please do not modify this code snippet.
exports.productSum = productSum;
```
