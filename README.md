## **Step One: Simplifying Expressions**

Simplify the following big O expressions as much as possible:

1. O(n + 10)

   ## O(n)

2. O(100 \* n)

   ## O(n)

3. O(25)

   ## O(1)

4. O(n^2 + n^3)

   ## O(n^3)

5. O(n + n + n + n)

   ## O(n)

6. O(1000 \* log(n) + n)

   ## O(n)

7. O(1000 _ n _ log(n) + n)

   ## O(n log(n))

8. O(2^n + n^2)

   ## O(2^n)

9. O(5 + 3 + 1)

   ## O(1)

10. O(n + n^(1/2) + n^2 + n \* log(n)^10)
    ## O(n^2)

---

## Step Two: Calculating Time Complexity

Determine the time complexities for each of the following functions. If you’re not sure what these functions do, copy and paste them into the console and experiment with different inputs!

function logUpTo(n) {
for (let i = 1; i <= n; i++) {
console.log(i);
}
}

## Time Complexity: O(n)

## The loop runs from 1 to n; it executes n times.

## Each iteration performs a constant-time operation (console.log(i)).

## The loop executes O(n) times, the overall time complexity is O(n).

---

function logAtLeast10(n) {
for (let i = 1; i <= Math.max(n, 10); i++) {
console.log(i);
}
}

## Time Complexity: O(n)

## The loop runs from 1 to the maximum of (n, 10).

## If n >= 10, the loop runs n times → O(n).

## If n < 10, the loop runs 10 times → O(10) = O(1) (constant time).

## In Big O, consider the worst-case and dominant term, so the function simplifies to O(n).

---

function logAtMost10(n) {
for (let i = 1; i <= Math.min(n, 10); i++) {
console.log(i);
}
}

## Time Complexity: O(1)

## The loop runs at most 10 times, regardless of how large n is.

## If n < 10, the loop runs n times.

## If n ≥ 10, the loop runs exactly 10 times.

## Since 10 is a constant the function is O(1) (constant time).

---

function onlyElementsAtEvenIndex(array) {
let newArray = [];
for (let i = 0; i < array.length; i++) {
if (i % 2 === 0) {
newArray.push(array[i]);
}
}
return newArray;
}

## Time Complexity: O(n)

## The loop iterates through the array n times (where n is array.length).

## Each iteration performs a constant-time operation (push() is O(1)).

## Since there are O(n) iterations, the overall time complexity is O(n).

---

function subtotals(array) {
let subtotalArray = [];
for (let i = 0; i < array.length; i++) {
let subtotal = 0;
for (let j = 0; j <= i; j++) {
subtotal += array[j];
}
subtotalArray.push(subtotal);
}
return subtotalArray;
}

## Time Complexity: O(n^2)

## The outer loop runs n times (from 0 to n-1).

## The inner loop runs i+1 times for each iteration of the outer loop.

## This results in a nested sum:

## The dominant term is n^2, so the overall time complexity is O(n^2).

---

function vowelCount(str) {
let vowelCount = {};
const vowels = "aeiouAEIOU";

for (let char of str) {
if(vowels.includes(char)) {
if(char in vowelCount) {
vowelCount[char] += 1;
} else {
vowelCount[char] = 1;
}
}
}

return vowelCount;
}

## Time Complexity:O(n)

## The function iterates over each character in str, which takes O(n) time.

## vowels.includes(char) is an O(1) operation because checking a string of fixed size ("aeiouAEIOU") takes constant time.

## The dictionary updates (vowelCount[char] += 1) are O(1) operations.

## Since the function only loops through str once, the overall complexity is O(n).

---

## **Part 3 - short answer**

Answer the following questions

1. True or false: n^2 + n is O(n^2).
   ## True – because the highest-order term dominates.
2. True or false: n^2 \* n is O(n^3).
   ## True –
3. True or false: n^2 + n is O(n).
   ## False – because n^2 dominates.
4. What’s the time complexity of the .indexOf array method?
   ## O(n) – The .indexOf method searches through the array linearly in the worst case.
5. What’s the time complexity of the .includes array method?
   ## O(n) – The .includes method also performs a linear search.
6. What’s the time complexity of the .forEach array method?
   ## O(n) – The .forEach method iterates through each element once.
7. What’s the time complexity of the .sort array method?
   ## O(n log n) – The .sort method typically uses an efficient sorting algorithm like Quicksort or Merge Sort.
8. What’s the time complexity of the .unshift array method?
   ## O(n) – The .unshift method shifts all elements to the right, making it linear.
9. What’s the time complexity of the .push array method?
   ## O(1) – The .push method appends an element to the end, which is constant time.
10. What’s the time complexity of the .splice array method?
    ## O(n) – The .splice method can remove or insert elements, requiring shifting in the worst case.
11. What’s the time complexity of the .pop array method?
    ## O(1) – The .pop method removes the last element without shifting, making it constant time.
12. What’s the time complexity of the Object.keys() function?
    ## O(n) – The Object.keys() function retrieves all keys, requiring traversal of the object.

### **BONUS**

1. What’s the space complexity of the Object.keys() function?

## O(n) – Object.keys() returns an array of keys, which takes up space proportional to the number of keys.
