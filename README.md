# Recursion Exercises

- ### Sum of all from 1 to n

Write a function that takes in a number as input and recursively finds the sum of all numbers up to and including that number.

```js
input: 6
output: 21

//21 = 6 + 5 + 4 + 3 + 2 + 1
```
```swift
func recursiveUpTo6(n:Int)->Int{
//base case
if n == 0 {return 0}
// recursive call
return n + recursiveUpTo6(n: n - 1)
}
recursiveUpTo6(n: 6)
```

- ### Multiply array

Write a function called `multArr` that takes in an array of numbers as an argument and recursively multiplies together all of the values in the array.

```js
multArr([2, 3, 5]); // returns 30
multArr([5, 5, 1, 2]); //returns 50
```
```swift

func recursiveArray(n:[Int]) ->Int{
var arrayVal = n
//var multipliedArrayVal:Int = 1
//base case
if arrayVal.count <= 0 {return 1}

//recursive call
return arrayVal.popLast()! * recursiveArray(n: arrayVal)
}
recursiveArray(n: [5, 5, 1, 2])
```
- ### Concatenate array

Write a function called `concatArr` that takes in an array of strings as an argument and recursively concatenates the strings together into a single string, with spaces between each original string.

```js
concatArr(['is', 'it', 'tomorrow']); // returns 'is it tomorrow'
concatArr(['or', 'just', 'the', 'end', 'of', 'time']); //returns 'or just the end of time'
```
```swift
func concatArr(n:[String])->String{
//Base case
var stringArray = n
if stringArray.count <= 0 {return ""}
//recursive call
return stringArray[0] + " " + concatArr(n: Array(stringArray.dropFirst()))
}

concatArr(n: ["is", "it", "tomorrow"])
```
- ### Sum evens

Write a function called `sumEvens` that takes in an array of numbers as an argument and recursively sums only the even numbers in the array.

```js
sumEvens([2, 3, 5, 6]); // returns 8
sumEvens([10, 5, 1, 2, 12]); //returns 24
```
```swift
func sumEvens(n:[Int])->Int{
//base case
if n.count <= 0 {return 0}
//recursive call
if n[0] % 2 == 0{
return n[0] + sumEvens(n: Array(n.dropFirst()))
}else{
return sumEvens(n: Array(n.dropFirst()))

}
}
sumEvens(n: [2, 3, 5, 6])


```


- ### Recursive range

Write a function called `range` which takes in two numbers (num1, num2) as arguments. The function should return an array of numbers between num1 and num2.

```js
range(2,10); // returns [2, 3, 4, 5, 6,7, 8, 9, 10]
range(17,20); // returns [17, 18, 19, 20]
```
```swift
func range(num1:Int, num2:Int)-> [Int]{
var numValArray:[Int] = []
if num1 > num2 {return []}
numValArray.append(num1)

return  numValArray + range(num1: num1 + 1, num2: num2)
}
range(num1: 10, num2: 25)
```


- ### Triple Step

A child is running up a staircase with n steps and can hop either 1 step 2 steps or 3 steps at a time. Write a function called 'tripleStep', that takes in an argument `n` that represents the number of steps in the staircase, and returns a count of how many possible ways the child can run up the stairs.

```js
tripleStep(3); //returns 4
tripleStep(4); //returns 7
tripleStep(5); //returns 13
tripleStep(10); //returns 274
```
```swift
```swift
func tripleStep(n:Int) -> Int{
//Base Case
if n == 0 { return 1 }
if n < 0 { return 0 }
// recursive call

return tripleStep(n: n-1) + tripleStep(n: n-2) + tripleStep(n: n-3)
}
tripleStep(n: 3)
```

Source: Cracking the Coding Interview

- ### Coin Combos

Given an infinite number of quarters, dimes, nickels, and pennies, write code to calculate the number of possible ways of giving exact change for `n` cents.

In other words, write a function called `coinCombos` that takes in one argument: `n`, which represents the total amount of money (in cents) that you need to make change for. Your function should return the amount of possible combinations you can make to return that exact amount of change.

For example:
```js
coinCombos(5); //returns 2
coinCombos(10); //returns 4
coinCombos(25); //returns 13
coinCombos(60); //returns 73
```


var combos: [[Int]] = []

func populateCombos(_ startingAmount: Int, coins: [Int] = []) {
print(coins)
if coins.reduce(0, { $0 + $1}) > startingAmount {
return
}
if coins.reduce(0, { $0 + $1 }) == startingAmount {
if !combos.contains(coins.sorted()) {
combos.append(coins.sorted())
}
return
}
populateCombos(startingAmount, coins: coins + [1])
populateCombos(startingAmount, coins: coins + [5])
populateCombos(startingAmount, coins: coins + [10])
populateCombos(startingAmount, coins: coins + [25])
}

populateCombos(23)
print(combos)
print(combos.count)
```
```swift
func tripleStep(n:Int) -> Int{
//Base Case
if n == 0 { return 1 }
if n < 0 { return 0 }
// recursive call

return tripleStep(n: n-1) + tripleStep(n: n-2) + tripleStep(n: n-3)
}
tripleStep(n: 3)

var combos: [[Int]] = []

func populateCombos(_ startingAmount: Int, coins: [Int] = []) {
print(coins)
if coins.reduce(0, { $0 + $1}) > startingAmount {
return
}
if coins.reduce(0, { $0 + $1 }) == startingAmount {
if !combos.contains(coins.sorted()) {
combos.append(coins.sorted())
}
return
}
populateCombos(startingAmount, coins: coins + [1])
populateCombos(startingAmount, coins: coins + [5])
populateCombos(startingAmount, coins: coins + [10])
populateCombos(startingAmount, coins: coins + [25])
}

populateCombos(23)
print(combos)
print(combos.count)


```

Source: CTCI

# Resources
- [JavaScript Recursion Exercises](http://www.w3resource.com/javascript-exercises/javascript-recursion-functions-exercises.php)
- [Swift Recursion Exercises](https://www.weheartswift.com/recursion/)
