for(var i; i<arr.length;i++)== for(var i in arr)

for(var i in arr){
if you want to print the index
console.log(i);
if you want to print the value
console.log(arr[i]);
}

for(var i of arr){
console.log(i);will print the value
}

Array properties
-forEach()
make some process for each value
-map()
make new array from the orginal array ex: double each value
-filter(value,index,array)
it filter the same array base on some condition ex: >5
-reduce(total,value,index,array)
it give you only one value from array ex: the sum of the array
-some()
it is a boolean function it return T or F base on some condition
if only one value match the condition will return T
-every()
it is a boolean function it return T or F base on some condition
must ALL VALUES match the condition will return T
-find()
it return the value you search for if the condition True if False will return undefine
-findIndex()
same as find() but it return the index if false will return -1
//////////////////////////////////////////////////////
How to remove item from Array ?
arr=['eggs','milk','bread','grapes','tomatoes'];
splice(1,2)
1 starting position based on INDEX
2 indicates how many items we want to remove
arr.splice(arr.indexOf('grapes'),1);

---

-shift()
remove the first element in index
-pop()
remove the last element in index
//////////////////////////////////////////////////////

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

Given an array of integers.

Return an array, where the first element is the count of positives numbers and the second element is sum of negative numbers. 0 is neither positive nor negative.

If the input is an empty array or is null, return an empty array.

Example
For input [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15], you should return [10, -65].

# Ans:

function countPositivesSumNegatives(input) {
if (input == null || input.length == 0)
return [];

var positive = 0;
var negative = 0;

for (var i=0, l=input.length; i<l; ++i)
{
if (input[i] > 0)
++ positive;
else
negative += input[i];
}

return [positive, negative];
}

# Ans:

function countPositivesSumNegatives(input) {
return input && input.length ? [input.filter(p => p > 0).length, input.filter(n => n < 0).reduce((a, b) => a + b, 0)] : [];
}

# Ans:

function countPositivesSumNegatives(input) {
if (!Array.isArray(input) || !input.length) return [];
return input.reduce((arr, n) => {
if (n > 0) arr[0]++;
if (n < 0) arr[1] += n;
return arr;
}, [0, 0]);
}

---

You will be given an array a and a value x. All you need to do is check whether the provided array contains the value.

Array can contain numbers or strings. X can be either.

Return true if the array contains the value, false if not.

# Ans:

const check = (a,x) => a.includes(x);

# Ans:

function check(a,x){
return a.includes(x);
};

# Ans:

mine
retrun a.some((e)=>e==x)

---

Write a function which calculates the average of the numbers in a given list.

Note: Empty arrays should return 0.

# Ans:

mine
function findAverage(array) {
if(array==null||array.length==0)
return 0;
let sum=array.reduce((a,b)=>a+b);
return sum/array.length;
}

# Ans:

var find_average = (array) => {  
 return array.length === 0 ? 0 : array.reduce((acc, ind)=> acc + ind, 0)/array.length
}

# Ans:

function find_average(array) {
if (array.length === 0) {
return 0;
}
var result = 0;
for (i=0; i<array.length; i++) {
result +=array[i];
}
return result/array.length;
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
