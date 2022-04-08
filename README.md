# corecode
# Fullstack developer Bootcamp


## Here are my solutions

## 1. Week 1
### Week challenges (Tuesday) 💻
#### Ensure question

Instructions: Given a string, write a function that returns the string with a question mark ("?") appends to the end, unless the original string ends with a question mark, in which case, returns the original string.

Example 1

    "Yes" --> "Yes?" 
    "No?" --> "No?" 

Link to codewars: https://www.codewars.com/kata/5866fc43395d9138a7000006

##### Solution

```
function ensureQuestion(s) {
  return s.substr(-1) !== "?" ? (s + "?") : s;
}
```

#### Reversed words

Instructions: Complete the solution so that it reverses all of the words within the string passed in.

Example 1

    "The greatest victory is that which requires no battle" --> "battle no requires which that is victory greatest The"
    
Link to codewars: https://www.codewars.com/kata/51c8991dee245d7ddf00000e
    
##### Solution
```
function reverseWords(str){
  let auxArr = [];
  let inicio = 0;
  for(i = 0; i < str.length; i++) {
    if (str[i] == " "){
      auxArr.unshift(str.substr(inicio, i - inicio));
      auxArr.unshift(" ");
      inicio = i + 1;
    }
    if (i === (str.length - 1)) {
      auxArr.unshift(str.substr(inicio, i + 1 - inicio));
      inicio = i + 1;
    }
  }
  
  str = "";
  
  for (i = 0; i < auxArr.length; i++) {
    str = str + auxArr[i];
  }
  return str;
}
```

### Week challenge (Wednesday)  💻

#### Find the smallest integer in the array

Instructions: Given an array of integers your solution should find the smallest integer. You can assume, for the purpose of this kata, that the supplied array will not be empty.

Example 1

    Given [34, 15, 88, 2] your solution will return 2
    Given [34, -345, -1, 100] your solution will return -345

Link to codewars: https://www.codewars.com/kata/55a2d7ebe362935a210000b2

##### Solution
```
class SmallestIntegerFinder {
  findSmallestInt(args) {
    return Math.min.apply( Math, args );
  }
}
```

### Week challenges (Thursday) 💻
#### Odd or even

Instructions: Given a list of integers, determine whether the sum of its elements is odd or even.

Give your answer as a string matching "odd" or "even".

If the input array is empty consider it as: [0] (array with a zero).

Example 1

    Input: [0]
    Output: "even"

    Input: [0, 1, 4]
    Output: "odd"

    Input: [0, -1, -5]
    Output: "even"
    
    
Link to codewars: https://www.codewars.com/kata/5949481f86420f59480000e7
    
##### Solution
```
function oddOrEven(array) {
  let suma = 0;
  array.forEach((item) => {
     suma += item;
  })
  return (suma%2===0) ? "even":"odd";
}
```
