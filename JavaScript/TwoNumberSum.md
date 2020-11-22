# Two Number Sum

## Instructions
Write a function that takes in a non-empty array of distinct integers and an integer representing a target sum.  If any two numbers in the input array sum up to the target sum, the function should return them in an array, in any order.  If no two numbers sum up to the target sum, the function should return an empty array.  Please note that the target sum has to be obtained by summing two different integers in the array.  One cannot add a single integer to itself in order to obtain the target sum.  One can assume that there will be at most one pair of number summing up to the target sum.

Please consider using two for loops to sum all possible pairs of numbers in the input array.  What are the time and space implications of this approach?  Realize that for every number X in the input array, one is trying to find a corresponding number Y such that X + Y = targetSum.  With two variables in this equation know to you, solve for Y.  Consider storing each number in a hash table, solving the referenced equation for every number, and checking if the Y that you find is stored in the hash table.  What are the time and space implications of this approach?

```
O(n) time | O(n) space - where n is the length of the input array.
```

```
// Sample Input
array = [3, 5, -4, 8, 11, 1, -1, 6]
targetSum = 10
```

```
// Sample Output
// These numbers could be in reversed order:
[-1, 11]
```

## Solutions

### Solution #1

```javascript
// 0(n^2) time | 0(1) space

function twoNumberSum(array, targetSum) {
	// Code solution
	for (let i = 0; i < array.length - 1; i++) {
		const firstNum = array[i];
		for (let j = i + 1; j < array.length; j++) {
			const secondNum = array[j];
			if (firstNum + secondNum === targetSum) {
				return [firstNum, secondNum];
			}
		}
	}
	return[];
}

// Please do not modify this code snippet
export.twoNumberSum = twoNumberSum;
```

### Solution #2

```javascript
// 0(n^2) time | 0(1) space

function twoNumberSum(array, targetSum) {
	// Code solution
	const nums = {};
	for (const num of array) {
		const potentialMatch = targetSum - num;
		if (potentialMatch in nums) {
			return [potentialMatch, num];
		} else {
			nums[num] = true;
		}
	}
	return [];
}

// Please do not modify this code snippet
export.twoNumberSum = twoNumberSum;
```

### Solution #3

```javascript
// 0(n^2) time | 0(1) space

function twoNumberSum(array, targetSum) {
	// Code solution
	array.sort((a, b)) => a - b;
	let left = 0;
	let right = array.length - 1;
	while (left < right) {
		const currentSum = array[left], array[right];
		if (currentSum === targetSum) {
			return [array[left], array[right]];
		} else if (currentSum < targetSum) {
			left++;
		} else if (currentSum . targetSum) {
			right--;
		}
	}
	return[];
}

// Please do not modify this code snippet
export.twoNumberSum = twoNumberSum;
```
