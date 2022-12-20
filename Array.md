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

Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.

Note: input will never be an empty string
x='45385593107843568'

# Ans:

mine
function fakeBin(x){
var y=[]
for(var i in x){
if(parseInt(x[i])<5){y.push('0');}

if (parseInt(x[i])>=5){y.push('1');}

}

return y.join('');

}

# Ans:

function fakeBin(x) {
return x.split('').map(n => n < 5 ? 0 : 1).join('');
}

# Ans:

function fakeBin(x) {
return x.replace(/\d/g, d => d < 5 ? 0 : 1);
}

---

DESCRIPTION:
Write a function that takes an array of numbers and returns the sum of the numbers. The numbers can be negative or non-integer. If the array does not contain any numbers then you should return 0.

Examples
Input: [1, 5.2, 4, 0, -1]
Output: 9.2

Input: []
Output: 0

Input: [-2.398]
Output: -2.398

Assumptions
You can assume that you are only given numbers.
You cannot assume the size of the array.
You can assume that you do get an array and if the array is empty, return 0.
What We're Testing
We're testing basic loops and math operations. This is for beginners who are just learning loops and math operations.
Advanced users may find this extremely easy and can easily write this in one line.

# Ans:

mine
// Sum Numbers
function sum (numbers) {
if(numbers==null)return 0
if(numbers.length==1)return numbers[0]
return numbers.reduce((a,b)=>a+b,0);
};

# Ans:

const sum = n => n.reduce((a,b) => a+b, 0);

# Ans:

function sum(numbers) {
return numbers.reduce((a, b) => a + b, 0);
}

---

DESCRIPTION:
Given a non-empty array of integers, return the result of multiplying the values together in order. Example:

[1, 2, 3, 4] => 1 _ 2 _ 3 \* 4 = 24

# Ans:

mine
function grow(x){
return x.reduce((a,b)=>a\*b,1);
}

# Ans:

const grow = (nums) => nums.reduce((product, num) => product \* num, 1);

# Ans:

x=[1, 2, 3]
function grow(x){
var temp=1
for(let i in x)
{
temp\*=x[i]
}
return temp;
}
grow(x);

---

DESCRIPTION:
Create a function with two arguments that will return an array of the first n multiples of x.

Assume both the given number and the number of times to count will be positive numbers greater than 0.

Return the results as an array or list ( depending on language ).

Examples
countBy(1,10) === [1,2,3,4,5,6,7,8,9,10]
countBy(2,5) === [2,4,6,8,10]

# Ans:

function countBy(x, n) {
var z = [];

for(var i=1;i<=n;i++){
z.push(x \* i);
}
return z;
}

# Ans:

function countBy(x, n) {
var z = [];
for (i = 1; i <= n; i++) {
z.push(x \* i);
}
return z;
}

---

DESCRIPTION:
I'm new to coding and now I want to get the sum of two arrays... Actually the sum of all their elements. I'll appreciate for your help.

P.S. Each array includes only integer numbers. Output is a number too.

# Ans:

function arrayPlusArray(arr1, arr2) {
return arr1.reduce((a,b)=>a+b,0) + arr2.reduce((a,b)=>a+b,0); //something went wrong
}

# Ans:

function arrayPlusArray(arr1, arr2) {
return arr1.concat(arr2).reduce((acc, cur) => acc + cur);
}

# Ans:

function arrayPlusArray(arr1, arr2) {
let arr = [...arr1, ...arr2];
return arr.reduce((a, b) => a + b);
}

---

DESCRIPTION:
It's the academic year's end, fateful moment of your school report. The averages must be calculated. All the students come to you and entreat you to calculate their average for them. Easy ! You just need to write a script.

Return the average of the given array rounded down to its nearest integer.

The array will never be empty.

# Ans:

function getAverage(marks){
return parseInt((marks.reduce((a,b)=>a+b,0))/marks.length, 10)
}

# Ans:

function getAverage(marks){
return Math.floor(marks.reduce((sum, x) => sum + x) / marks.length);
}

# Ans:

function getAverage(marks){

// calculates total number of marks
var total = 0;
for(var i = 0; i < marks.length; i++){
total += marks[i];
}

---

DESCRIPTION:
Sentence Smash
Write a function that takes an array of words and smashes them together into a sentence and returns the sentence. You can ignore any need to sanitize words or add punctuation, but you should add spaces between each word. Be careful, there shouldn't be a space at the beginning or the end of the sentence!

Example
['hello', 'world', 'this', 'is', 'great'] => 'hello world this is great'

# Ans:

mine
function smash (words) {
return words.join(' ');
};

# Ans:

function smash (words) {
"use strict";
return words.join(' ');
};

# Ans:

---

DESCRIPTION:
Write a function to split a string and convert it into an array of words.

Examples (Input ==> Output):
"Robin Singh" ==> ["Robin", "Singh"]

"I love arrays they are my favorite" ==> ["I", "love", "arrays", "they", "are", "my", "favorite"]

# Ans:

function stringToArray(string){

return string.split(' ')
}

# Ans:

const stringToArray = string => string.split(' ');

# Ans:

stringToArray=(s)=>s.split(' ')

---

DESCRIPTION:
You take your son to the forest to see the monkeys. You know that there are a certain number there (n), but your son is too young to just appreciate the full number, he has to start counting them from 1.

As a good parent, you will sit and count with him. Given the number (n), populate an array with all numbers up to and including that number, but excluding zero.

For example(Input --> Output):

10 --> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
1 --> [1]

# Ans:

mine
function monkeyCount(n) {
// your code here
var z=[]
for(var i=1 ;i<=n;i++){
z[i-1] =i;
}
return z;
}

# Ans:

function monkeyCount(n) {
return Array.from({length:n}, (\_,i)=>i+1)
}

# Ans:

function monkeyCount(n) {
for (var i = 0, arr = []; i < n; arr.push(++i));

return arr;
}

---

DESCRIPTION:
Given an array of integers as strings and numbers, return the sum of the array values as if all were numbers.

Return your answer as a number.

assert.strictEqual(sumMix([9, 3, '7', '3']), 22);
assert.strictEqual(sumMix(['5', '0', 9, 3, 2, 1, '9', 6, 7]), 42);
assert.strictEqual(sumMix(['3', 6, 6, 0, '5', 8, 5, '6', 2,'0']), 41);
})

# Ans:

function sumMix(x){
return x.reduce((a,b)=>a+Number(b),0)
}

# Ans:

function sumMix(x){
return x.map(a => +a).reduce((a, b) => a + b);
}

# Ans:

function sumMix(x){
let result = 0;
for (let n of x) {
result += parseInt(n);
}
return result;
}

---

DESCRIPTION:
Your task is to find the first element of an array that is not consecutive.

By not consecutive we mean not exactly 1 larger than the previous element of the array.

E.g. If we have an array [1,2,3,4,6,7,8] then 1 then 2 then 3 then 4 are all consecutive but 6 is not, so that's the first non-consecutive number.

If the whole array is consecutive then return null2.

The array will always have at least 2 elements1 and all elements will be numbers. The numbers will also all be unique and in ascending order. The numbers could be positive or negative and the first non-consecutive could be either too!

If you like this Kata, maybe try this one next: https://www.codewars.com/kata/represent-array-of-numbers-as-ranges

1 Can you write a solution that will return null2 for both [] and [ x ] though? (This is an empty array and one with a single number and is not tested for, but you can write your own example test. )

2
Swift, Ruby and Crystal: nil
Haskell: Nothing
Python, Rust, Scala: None
Julia: nothing
Nim: none(int) (See options)

# Ans:

mine

function firstNonConsecutive (arr) {

    var f=arr[0]

for(var i in arr){

if(arr[i]!=f)return arr[i]

f++
}
return null
}

# Ans:

function findFirstNonConsecutive(arr) {
for (let i = 1; i < arr.length; i++) {
if (arr[i] - arr[i-1] !== 1) {
return arr[i];
}
}
return null;
}

# Ans:

function firstNonConsecutive (arr) {
let result = arr.find((val, index) => val !== index + arr[0]);

    return (Number.isInteger(result)) ? result : null;

## }

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
