---
title: Algorithm's Efficiency
subtitle: Big O “In Simple English”
layout: post_detail
date-created: 2021-08-01
date-edited: 
img: dreams.png
thumbnail: 2021-08-01-algorithm-efficiency-thumbnail.jpg
alt: image-alt
category: [Post, Study]
description: A quick guide to Big O notation
comments: true
---

# Complexity | Runtime Analysis | Big O Notation

## Algorithm’s Time Complexity

Let’s start with a short popular fun story:
I’m originally from the D.R.Congo, in Central Africa and we have a very low internet speed. For illustration, opening a Gmail might take about 2 to 3 min of loading time (sometimes the whole process might just failed and time out).
In 2009, a company in South Africa had a similar issue: “really slow internet speed”. The company had two offices located about 50 miles away from each other and they decided to set up a fun test to see **if it would be faster to transfer data over their very much slow internet or via carrier pigeon.**

![Pigeon vs Internet](/img/{{ page.url }}/pigeon-vs-internet.png){: .img-responsive}

From a programming concept, Big O notation is used as a sort of measurement unit that helps programmers evaluate or estimate the efficiency of a written bloc of code, a script or an algorithm: “What the amount of time it’s going to take to run? What is the complexity depending on the variation of data to be processed by that piece of code”.  

It’s hard to determine the exact runtime of a script or an algorithm. Which is also dependent on other factors such as the speed of the processor and other specifications of the computer in which that script or algorithm is running. So instead of evaluating the runtime directly, big O notation is used to evaluate how quickly the runtime grows relative to the input data to be processed by that algorithm.  

## Time and Space Complexity
When you write code, any piece of code, in any programming language; you deal with two types of complexities:
### Time complexity
The time complexity of an algorithm determines the number of steps taken by the algorithm, measured with respect to n (input data to be processed), the size of the input.
### Space complexity
The space complexity of an algorithm determines the amount of space required by the algorithm to execute, measured with respect to n \(input data to be processed\).

---

### Constant | O(1)
* Notice that in the scenario above, the pigeon would take the same amount of time to carry 5KB, 10MB or 2TB of data stored in the USB drive. The pigeon will always take the same amount of time to move any amount of data from office A to office B, It just has to fly 50 miles — considering certain assumptions and simplifications of course.  

So in Big O Notation, the time the pigeon takes to move data from office A to office B is referred to as constant time: O(1). Meaning the time is constant with respect to the size of the input.  

Here is an example of a piece of JavaScript code that has a runtime of O(1):  
```JavaScript
// get the lenght of an array list

var fruits = ["Banana", "Orange", "Apple", "Mango"];
var numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14];

function getListLenght(list) {
    var _lenght = list.length;
    return _lenght;
}

console.log('The number of item in list is: ', getListLenght(fruits));      // 4
console.log('The number of item in list is: ', getListLenght(numbers));     // 14

// **********************************************************************************
// - In this case the run time of getListLenght is costant: O(1)
// - It'll take the same time to run no matter the number of item in the array list
// **********************************************************************************
```

### Linear | O(n)
* Whereas, transferring data over the internet would take longer and longer as the amount of data to be transferred increase.  

So in Big O Notation, the time the internet takes to transferred data from office A to Office B will grow linearly and in direct proportion to the size of the input data set and represented as O(n). with n being the amount of data to be transmitted.  

In computer programming, Big O favors the worst-case performance scenario; meaning, for example, a case where we are looking for a matching number in an array of number which could be found during any iteration of the for loop and the function would return early. Big O notation will always assume the upper limit where the algorithm will perform the maximum number of iterations to find the matching number (if the number was the last element stored in the array).  

Here is an example of a piece of JavaScript code that has a runtime of O(n):

```Javascript
// return true if an item exists in list
// and false if it doesn't
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14];

function checkItemInList(item, list) {
    return list.includes(item);
}

console.log('Is Mango in Fruit List:', checkItemInList('Mango', fruits));      // true
console.log('Is Avocado in Fruit List:', checkItemInList('Avocado', fruits));  // false

console.log('Is 14 in numbers list:', checkItemInList(14, numbers));           // true
console.log('Is 15 in numbers list:', checkItemInList(15, numbers));           // false

// **********************************************************************************
// - In the case the run time of checkItemInList is O(n)
// - n being the number of item in the array list
// - Big O Notaion favor the worse case scenaior: the item we are looking for 
// - is the last item in the list array
// **********************************************************************************
```

### Quadratic | O( n²)
Quadratic or O(N²) represents an algorithm whose performance is directly proportional to the square of the size of the input data set.  

A nested iteration over the data set ( such as nest for loop) is a common example of a script or algorithm that involve quadratic runtime. Thus, deeper nested iterations will result in O(N³), O(N⁴), etc.  

```JavaScript
// read an array of array
function readArrayOfArray() {
    // This is an array of arrays.
    // It is a little easier to read like this:
    var arrayNumberFruit = [
        [1, 'Orange'],
        [2, 'Banana'],
        [3, 'Apple'],
        [4, 'Mango']
    ];

    arrayNumberFruit.forEach(function (items) {

        // will display [1, 'Orange'], [2, 'Banana'],...
        console.log('Items in the array are: ', items); 

        items.forEach(function (number) {

            // will display 1, Orange, 2, Banana, 3 ......
            console.log('Numbers in the array are: ', number); //
            
        });     
    });
}

// **********************************************************************************
// - In this case the run time of readArrayOfArray is quadratic: O( n²)
// - the method goes as O(N*N) or O(N²), because every time you increase the number 
// - of items in the array of array, the computation effort or time will increase as 
// - the square of the number of points.
// **********************************************************************************
```

### Exponential | O(2^n)
An algorithm is said to have an exponential time or O(2^n) if its runtime doubles with each addition to the input data set. The growth curve of an O(2^n) function is exponential — starting off very shallow, then rising meteorically. A recursive calculation of Fibonacci numbers is one example of an O(2^n) function is:

```JavaScript
// recursive calculation of Fibonacci numbers

function fibonacci(number) {
    if (number <= 1) return number;
    return fibonacci(number - 2) + fibonacci(number - 1);
}

console.log(fibonacci(5));
console.log(fibonacci(6));
console.log(fibonacci(7));

// **********************************************************************************
// - In this case the run time of readArrayOfArray is quadratic: O(2^N)
// **********************************************************************************
```

### Logarithmic| O(log n)
Logarithmic time complexity is a bit trickier to get at first. So I’m going to use a common example to explain it: Binary search concept.  

Binary search is a technique used to search sorted data sets. It works by selecting the middle element of the data set and compares it against a target value. If the values match it will return success. If the searched value is higher than the value of the probe element it will take the upper half of the data set and perform the same operation against it.  

Otherwise, if the searched value is lower than the value of the probe element it will perform the operation against the lower half. this set of actions will continue to halve the data set with each iteration until the searched value has been found or until it can no longer split the data set:

```JavaScript
// Binary Search(Iterative Approach)

var binarySearch = function (array, number) {
    var start = 0;
    var end = array.length - 1;

    // Iterate while start not meets end 
    while (start <= end) {

        // Find the mid index 
        var mid = Math.floor((start + end) / 2);

        // If element is present at mid, return True 
        if (array[mid] === number) return true;

        // Else look in left or right half accordingly 
        else if (array[mid] < number)
            start = mid + 1;
        else
            end = mid - 1;
    }

    return false;
};

function findNumber(array, number) {
    if (binarySearch(array, number, 0, array.length-1)) {
        return('Number 5 exist in the array');
    } else {
        return('Number 5 not found!');
        
    }
}

var numberArray = [1, 3, 4, 2, 5, 7, 6, 8, 9];
var searched_number = 5;

// will display Number 5 exist in the array
console.log(findNumber(numberArray, searched_number));

// **********************************************************************************
// - In this case the run time of this script is: O(logn)
// - this is a script that implement binary search through iterative approach. 
// - we use a while loop, which runs until it hits the base condition 
// - i.e start becomes greater than end.
// - best case scenario is when the element we are looking for is stored in the 
// - middle of the array.(which means the script will only run one time)
// - Worst case scenario is when the element we are looking for is stored either 
// - at the end or begining of the array
// **********************************************************************************
```

![Big-O Cheat Sheet](/img/{{ page.url }}/big-o-cheat-sheet.jpeg){: .img-responsive}

Here are some typical orders of growth:
* O(1) — constant time
* O(log n) — logarithmic
* O(n) — linear time
* O(n²) — quadratic
* O(2^n) — exponential
* O(n!) — factorial

if you are entry-level programmer, try to make a habit of thinking about the time and space complexity as you “design algorithm and write code.” It’ll allow you to optimize your code and solve potential future performance issues right away.

![Comparison of Sort Algorithms](/img/{{page.url}}/sort-efficiency.png){: .img-responsive}


> ##### “writing code is good, writing code that works is better, writing optimized working code is best.”

it’s quite evident that a script that takes 2 min to run is better than one that takes 5 min to run. Writing code that works, easy to understand, and meets its functionalities requirement is good, any programmer can do that. Writing code that is optimized (time and space-efficient) with the right balance of readability, runtime and maintainability are what the word “engineer” represent in the title “Software Engineering.”

---

### Source
[Algorithm’s Efficiency | Big O “In Simple English”](https://blog.bitsrc.io/algorithms-efficiency-big-o-in-simple-english-adbaedbcdfcf){:target="_blank"}