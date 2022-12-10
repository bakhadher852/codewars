DESCRIPTION:
You get an array of numbers, return the sum of all of the positives ones.

Example [1,-4,7,12] => 1 + 7 + 12 = 20

Note: if there is nothing to sum, the sum is default to 0.

# Ans:

function positiveSum(arr) {
var total = 0;  
 for (i = 0; i < arr.length; i++) { // setup loop to go through array of given length
if (arr[i] > 0) { // if arr[i] is greater than zero
total += arr[i]; // add arr[i] to total
}
}
return total; // return total
}

# Ans:

function positiveSum(arr) {
return arr.reduce((a,b)=> a + (b > 0 ? b : 0),0);
}

# Ans:

function positiveSum(arr) {
return arr.filter(x => x > 0).reduce((a, b) => a+b, 0);
}

---

DESCRIPTION:
Given a set of numbers, return the additive inverse of each. Each positive becomes negatives, and the negatives become positives.

invert([1,2,3,4,5]) == [-1,-2,-3,-4,-5]
invert([1,-2,3,-4,5]) == [-1,2,-3,4,-5]
invert([]) == []
You can assume that all values are integers. Do not mutate the input array/list.

# Ans:

function invert(array) {
var newArr = [];
for(var i = 0; i < array.length; i++){
newArr.push(-array[i]);
}
return newArr;
}

# Ans:

const invert = array => array.map(num => -num);

# Ans:

function invert(array) {
return array.map(e=> e\*-1);
}

---

DESCRIPTION:
Can you find the needle in the haystack?

Write a function findNeedle() that takes an array full of junk but containing one "needle"

After your function finds the needle it should return a message (as a string) that says:

"found the needle at position " plus the index it found the needle, so:

Example(Input --> Output)

["hay", "junk", "hay", "hay", "moreJunk", "needle", "randomJunk"] --> "found the needle at position 5"
Note: In COBOL, it should return "found the needle at position 6"

# Ans:

function findNeedle(haystack) {
return "found the needle at position " + haystack.indexOf("needle");
}

# Ans:

const findNeedle = haystack => `found the needle at position ${haystack.indexOf('needle')}`;

# Ans:

function findNeedle(haystack) {
return `found the needle at position ${haystack.indexOf('needle')}`;
}

---

DESCRIPTION:
Given an array of integers, return a new array with each value doubled.

For example:

[1, 2, 3] --> [2, 4, 6]

# Ans:

function maps(x){
//return x.map(el => el _ 2);
let arr = [];
for(let i = 0; i < x.length; i++){
arr.push(x[i] _ 2);
}
return arr;
}

# Ans:

maps = x => x.map(e => e \* 2);

# Ans:

function maps(x){
return x.map(n => n \* 2);
}

---

DESCRIPTION:
Convert number to reversed array of digits
Given a random non-negative number, you have to return the digits of this number within an array in reverse order.

Example(Input => Output):
35231 => [1,3,2,5,3]
0 => [0]

# Ans:

function digitize(n) {
return String(n).split('').map(Number).reverse()
}

# Ans:

function digitize(n) {
return Array.from(String(n), Number).reverse();
}

# Ans:

function digitize(n){
return (n + '').split('').map(Number).reverse();
}

---

DESCRIPTION:
Consider an array/list of sheep where some sheep may be missing from their place. We need a function that counts the number of sheep present in the array (true means present).

For example,

[true, true, true, false,
true, true, true, true ,
true, false, true, false,
true, false, false, true ,
true, true, true, true ,
false, false, true, true]
The correct answer would be 17.

Hint: Don't forget to check for bad values like null/undefined

# Ans:

function countSheeps(arrayOfSheeps) {
return arrayOfSheeps.filter(Boolean).length;
}

# Ans:

function countSheeps(arrayOfSheep) {
// TODO May the force be with you
var num = 0;

for(var i = 0; i < arrayOfSheep.length; i++)
if(arrayOfSheep[i] == true)
num++;

return num;
}

# Ans:

function countSheeps(arr) {
return arr.filter(Boolean).length;
}

---

DESCRIPTION:
Complete the square sum function so that it squares each number passed into it and then sums the results together.

For example, for [1, 2, 2] it should return 9 because 1^2 + 2^2 + 2^2 = 9.

# Ans:

function squareSum(numbers){
return numbers.reduce(function(sum, n){
return (n\*n) + sum;
}, 0)
}

# Ans:

function squareSum(numbers){
return numbers.reduce((sum,num) => sum + (num \* num), 0);
}

# Ans:

function squareSum(numbers){
var sum = 0;
numbers.forEach(function(n) {
sum += n \* n
});
return sum;
}

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---

# Ans:

# Ans:

# Ans:

---
