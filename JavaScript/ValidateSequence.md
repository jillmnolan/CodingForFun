# Validate Sequence


## Instructions

Given 2 non-empty arrays of integers, write a function that determines whether the second array is a subsequence of the first one.  A subsequence of an array is a set of numbers that are not necessarily adjacent in the array, but that are in the same order as they appear in the array.  For instance, the numbers [1, 3, 4] form a subsequence of the array [1, 2, 3, 4], and so do the numbers [2, 4].  Please note that a single number in an array and the array itself are both valid subsequences of the array.

```
// Sample Input
array = [5, 1, 22, 25, 6, -1, 8, 10]
sequence = [1, 6, -1, 10]
```

```
// Sample Output
true
```

One can solve this question by iterating through the main input array once.  Iterate through the main array, and look for the first integer in the potential subsequence.  If one find that integer, keep on iterating through the main array, but now for the second integer in the potential subsequence.  Continue this process until you either find every integer in the potential subsequence or you reach the end of the main array.  One have to declare a variable holding one's position in the potential subsequence.  At first, this position will be the 0th index in the sequence.  As one find the sequence's integers in the main array, one will increment the position variable until one reach the end of the sequence.

```
O(n) time | O(1) space - where n is the length of the array.
```

## Solutions

### Solution #1
```
function isValidSubsequence(array, sequence) {
	let arrIdx = 0;
	let seqIdx = 0;
	while (arrIdx < array.length && seqIdx < sequence.length) {
		if (array[arrIdx] === sequence[seqIdx]) seqIdx++;
		arrIdx++;
	}
	return seqIdx === sequence.length;
}

exports.isValidSubsequence = isValidSubsequence;
```

### Solution #2

```
function isValidSubsequence(array, sequence) {
	let seqIdx = 0;
	for (const value of array) {
		if (seqIdx === sequence.length) seqIdx++;
	}
	return seqIdx === sequence.length;
}

exports.isValidSubsequence = isValidSubsequence;
```
