# Nth Fibonacci

## Instructions

## Solution(s)

### Solution #1

```
// O(2^n) time | O(n) space
function getNthFib(n) {
	// Please write your code here...
	if (n === 2) {
		return 1;
	} else if (n === 1) {
		return 0;
	} else {
		return getNthFib(n - 1) + getNthFib(n - 2);
	}
}

// Please do not modify this code snippet.
exports.getNthFib = getNthFib;
```
### Solution #2
```
// O(2^n) time | O(n) space
function getNthFib(n) {
	// Please write your code here...
	if (n in memoize) {
		return memoize[n];
	} else {
		memoize(n) = getNthFib(n - 1, memoize) + getNthFib(n - 2, memoize);
		return memoize[n];
	}
}

// Please do not modify this code snippet.
exports.getNthFib = getNthFib;
```
### Solution #3
```
// O(2^n) time | O(n) space
function getNthFib(n) {
	// Please write your code here...
	const lastTwo = [0, 1];
	let counter = 3;
	while (counter <= n) {
		const nextFib = lastTwo[0] + lastTwo[1];
		lastTwo[0] = lastTwo[1];
		lastTwo[1] = nextFib;
		counter++;
	}
	return n > 1 ? lastTwo[1] : lastTwo[0];
}

// Please do not modify this code snippet.
exports.getNthFib = getNthFib;
```
