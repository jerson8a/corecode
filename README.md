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

## 2. Week 2

### Week challenges (Monday) 💻
#### Is palíndrome? 

Instructions: A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. This includes capital letters, punctuation, and word dividers.

Implement a function that checks if something is a palindrome. If the input is a number, convert it to string first.

Examples
isPalindrome("anna")   ==> true
isPalindrome("walter") ==> false
isPalindrome(12321)    ==> true
isPalindrome(123456)   ==> false

##### Solution
```
function isPalindrome(line) {
  return new String(line).split("").reverse().join("") == line;
}
```

### Week challenges (Thuesday) 💻
#### Well of ideas

Instructions: For every good kata idea there seem to be quite a few bad ones!

In this kata you need to check the provided array (x) for good ideas 'good' and bad ideas 'bad'. If there are one or two good ideas, return 'Publish!', if there are more than 2 return 'I smell a series!'. If there are no good ideas, as is often the case, return 'Fail!'.

Example 1

    well(['bad', 'bad', 'bad']) => 'Fail!'
    well(['good', 'bad', 'bad', 'bad', 'bad']) => 'Publish!'
    well(['good', 'bad', 'bad', 'bad', 'bad', 'good', 'bad', 'bad', 'good']) => 'I smell a series!'
  
Link to codewars: https://www.codewars.com/kata/57f222ce69e09c3630000212/train/javascript

##### Solution

````
function well(x){
  let count = 0;
  x.forEach((item) => {
    if (item == "good") {
      count++;
    }
  })
  if (count === 1) {
    return "Publish!";
  } else if (count > 2) {
    return 'I smell a series!';
  } else {
    return "Fail!";
  }
}
````

### Week challenges (Wednesday) 💻
#### React manage events

Instructions: Write a react component that will display the current value of our counter.

The counter should start at 0.
There should be a button to add 1.
There should also be a button to subtract 1.
We want to be able to see the value of the counter - so it should be rendered! And for your buttons to work they will need an onClick prop.

In your render you should return:

The counter display element with an id of 'counter', containing the counter value.
An increment button with an id of 'increment'
A decrement button with an id of 'decrement'

Link to codewars: https://www.codewars.com/kata/5a8319f257c562ede8000037

##### Solution

```
import React from 'react';

export class Counter extends React.Component {
  constructor(props) {
    // Your state
    super(props);
    this.state = {
      counter: 0
    };
  }
  
  
  // Your event handlers 
  render() {
    return (
      <div>
        <h1 id="counter">{this.state.counter}</h1>
          <button id="decrement" type="button" onClick={() => this.setState({ counter: this.state.counter - 1 })}>
            Decrement
          </button>
          <button id="increment" type="button" onClick={() => this.setState({ counter: this.state.counter + 1 })}>
            Increment
          </button>
      </div>
    )
  }
}

```

### Week challenges (Thursday) 💻
#### React santa wishlist

Instructions: Santa wants to simplify his life and offer children the possiblity to enter their wishlist via an online form.

The form should be a React component and should contain:

an input field for the child's name (with id 'name')
a text area to describe the wish (id: 'wish')
a drop-down indicating the priority of the wish, from 1 to 5 - default is 1 (id: 'priority')
the keys in the state to store the corresponding values should be named the same as the element's id
an onSubmit action calling the function handleSubmit
a function called handleSubmit, which
calls send (a function that is already provided as part of the injected properties props)
passes the current state as a parameter to send
calls event.preventDefault
it should be a controlled component (i.e. using onChange to bind input to the component's state)

Link to codewars: https://www.codewars.com/kata/5a9ecd89fd5777e0790001ea

##### Solution
````
import { useState } from "react";
import "./styles.css";

export default function App(props) {
  const { send } = props;
  const [name, setName] = useState("");
  const [wish, setWish] = useState("");
  const [priority, setPriority] = useState(1);

  const handleSubmit = (e) => {
    e.preventDefault();
    send(wish);
  };
  return (
    <div className="App">
      <form onSubmit={handleSubmit}>
        <input
          type="text"
          id="name"
          value={name}
          onChange={(e) => setName(e.target.value)}
        />
        <textarea
          id="wish"
          value={wish}
          onChange={(e) => setWish(e.target.value)}
        ></textarea>
        <select
          name="priority"
          id="priority"
          value={priority}
          onChange={(e) => setPriority(e.target.value)}
        >
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
          <option value="4">4</option>
          <option value="5">5</option>
        </select>
      </form>
    </div>
  );
}
````


## 1. Week 3
### Week challenges (Monday) 💻
#### Build Search filter in React

Instructions: React code to build a simple search filter functionality to display a filtered list based on the search query entered by the user.

##### Solution

```
export default function App() {
  const [texto, setTexto] = useState("");
  const words = [
    "banana",
    "apple",
    "orange",
    "mango",
    "pinneapple",
    "watermelon"
  ];
  const [wordsF, setWordsF] = useState([]);

  useEffect(() => {
    texto.length > 0
      ? setWordsF(
          words.filter(function (el) {
            return el.toLowerCase().indexOf(texto.toLowerCase()) > -1;
          })
        )
      : setWordsF(words);
  }, [texto]);

  return (
    <div className="App">
      <label for="txtTexto">Search: </label>
      <input
        type="text"
        value={texto}
        onChange={(e) => setTexto(e.target.value)}
      />
      {wordsF.map((item, index) => {
        return <p key={index}>{item}</p>;
      })}
      {wordsF.length === 0 && <p>No hay coincidencias</p>}
    </div>
  );
}

```


### Week challenges (Thuesday) 💻
#### Fetch Random User Data

Instructions: React code to fetch from this API random users. You should display the Name, website, email and phone of a random user. Also there should be a Reset button to fetch a new user (For this you need to generate a random number from 1 to 10).

##### Solution

````
import { useEffect, useState } from "react";
import "./styles.css";

export default function App() {
  const [userData, setUserData] = useState({});

  useEffect(() => {
    getUserData();
  }, []);

  const getUserData = () => {
    let number = Math.floor(Math.random() * 10);
    fetch(`https://jsonplaceholder.typicode.com/users/${number}`)
      .then((response) => response.json())
      .then((json) => setUserData(json));
  };
  return (
    <div className="App">
      <button onClick={getUserData}>Reset</button>
      <h1>User Data</h1>
      <p>
        <strong>Name: </strong>
        {userData.name}
      </p>
      <p>
        <strong>Website: </strong>
        {userData.website}
      </p>
      <p>
        <strong>Email: </strong>
        {userData.email}
      </p>
      <p>
        <strong>Phone: </strong>
        {userData.phone}
      </p>
    </div>
  );
}
````


### Week challenges (Wednesday) 💻
#### React Router Blog

Instructions: Create a blog with React Router and get info from posts from a json file.

```
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Saludo from './Components/Saludo/Saludo';
import BlogMenu from './Pages/BlogMenu/BlogMenu';
import BlogReact from './Pages/BlogReact/BlogReact';
import BlogCoreCode from './Pages/BlogCoreCode/BlogCoreCode';
import './App.css';

function App() {
  return (
    <div className="App">
      <Router>
        <Routes>
          <Route path='/saludo' element={<Saludo />} />
          <Route path='/blog' element={<BlogMenu />} />
          <Route path='/blogreact' element={<BlogReact />} />
          <Route path='/blogcorecode' element={<BlogCoreCode />} />
        </Routes>
      </Router>
    </div>
  );
}

export default App;
```

````
import React from 'react';
import { Link } from 'react-router-dom';

const BlogMenu = () => {
  return (
    <>
        <h1>Menu</h1>
        <Link to="/blogreact">React</Link>
        <p>Published by ⚡️ Jerson on 2022-04-27 </p>
        <Link to="/blogcorecode">Core Code</Link>
        <p>Published by ⚡️ Jerson on 2022-04-27 </p>
    </>
  )
}

export default BlogMenu
````

## 4. Week 04

### Week challenges (Monday) 💻
#### Two To One

Instructions: Take 2 strings s1 and s2 including only letters from ato z. Return a new sorted string, the longest possible, containing distinct letters - each taken only once - coming from s1 or s2.

Examples:
a = "xyaabbbccccdefww"
b = "xxxxyyyyabklmopq"
longest(a, b) -> "abcdefklmopqwxy"

a = "abcdefghijklmnopqrstuvwxyz"
longest(a, a) -> "abcdefghijklmnopqrstuvwxyz"

Kata link: https://www.codewars.com/kata/5656b6906de340bd1b0000ac/train/javascript

##### Solution
````
function longest(s1, s2) {
  let auxString = s1 + s2;
  let arr = Array.from(auxString).sort();

  return result = arr.filter((item,index)=>{
    return arr.indexOf(item) === index;
  }).join("");
}
````


### Week challenges (Tuesday) 💻
#### Leap Years

Instructions: In this kata you should simply determine, whether a given year is a leap year or not. In case you don't know the rules, here they are:

years divisible by 4 are leap years
but years divisible by 100 are not leap years
but years divisible by 400 are leap years
Additional Notes:

Only valid years (positive integers) will be tested, so you don't have to validate them

Kata link: https://www.codewars.com/kata/526c7363236867513f0005ca/train/javascript

##### Solution
```
function isLeapYear(year) {
  // TODO
  if (year % 4 === 0) {
    if (year % 100 === 0) {
      if (year % 400 === 0) {
        return true;
      }
      return false;
    }
    return true;
  }
  return false;
}
```

### Week challenges (Wednesday) 💻
#### Maximum Length Difference

Instructions: You are given two arrays a1 and a2 of strings. Each string is composed with letters from a to z. Let x be any string in the first array and y be any string in the second array.

Find max(abs(length(x) − length(y)))

If a1 and/or a2 are empty return -1 in each language except in Haskell (F#) where you will return Nothing (None).

Example:
a1 = ["hoqq", "bbllkw", "oox", "ejjuyyy", "plmiis", "xxxzgpsssa", "xxwwkktt", "znnnnfqknaz", "qqquuhii", "dvvvwz"]
a2 = ["cccooommaaqqoxii", "gggqaffhhh", "tttoowwwmmww"]
mxdiflg(a1, a2) --> 13

Kata link: https://www.codewars.com/kata/5663f5305102699bad000056/train/javascript

##### Solution
````
function mxdiflg(a1, a2) {
  if (a1.length === 0 || a2.length === 0) return -1;
  a1.sort((a, b) => a.length - b.length);
  a2.sort((a, b) => a.length - b.length);
  return Math.max(
    Math.abs(a1[0].length - a2[a2.length - 1].length),
    Math.abs(a2[0].length - a1[a1.length - 1].length)
  );
}

````

### Week challenges (Thursday) 💻
#### Base64 Numeric Translator

Instructions: Our standard numbering system is (Base 10). That includes 0 through 9. Binary is (Base 2), only 1’s and 0’s. And Hexadecimal is (Base 16) (0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F). A hexadecimal “F” has a (Base 10) value of 15. (Base 64) has 64 individual characters which translate in value in (Base 10) from between 0 to 63.

####Write a method that will convert a string from (Base 64) to it's (Base 10) integer value.

The (Base 64) characters from least to greatest will be

ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/
Where 'A' is equal to 0 and '/' is equal to 63.

Just as in standard (Base 10) when you get to the highest individual integer 9 the next number adds an additional place and starts at the beginning 10; so also (Base 64) when you get to the 63rd digit '/' and the next number adds an additional place and starts at the beginning "BA".

Example:

base64_to_base10("/") # => 63
base64_to_base10("BA") # => 64
base64_to_base10("BB") # => 65
base64_to_base10("BC") # => 66
Write a method base64_to_base10 that will take a string (Base 64) number and output it's (Base 10) value as an integer.

Kata link: https://www.codewars.com/kata/5632e12703e2037fa7000061/train/javascript

````
function base64toBase10(base64) {
  const base64Dictionary = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/";
  let multiplier = 0;
  if (base64.length > 1) {
    multiplier = 1;
    let result = 0;
    for (let i = base64.length - 1; i >= 0; i--) {
      result += base64Dictionary.indexOf(base64[i]) * multiplier;
      multiplier = multiplier * 64;
    }
    return result;
  } else {
    return base64Dictionary.indexOf(base64[base64.length - 1]);
  }
  let response = multiplier;
  return response;
}
````

## 5. Week 05

### Week challenges (Monday) 💻
#### Fun With Lists

Kata link: https://www.codewars.com/kata/58259d9062cfb45e1a00006b/train/javascript

Instructions: mplement the method map, which accepts a linked list (head) and a mapping function, and returns a new linked list (head) where every element is the result of applying the given mapping method to each element of the original list.

For example: Given the list: 1 -> 2 -> 3, and the mapping function x => x * 2, map should return 2 -> 4 -> 6

The linked list is defined as follows:

function Node(data, next = null) {
  this.data = data;
  this.next = next;
}
Note: the list may be null and can hold any type of value.

##### Solution

````
function map(head, f) {
  if (head) {
    let response = null, aux = null;     
    let item = head; // Asignamos lista enlazada a nueva variable
    while (item != null) { // Recorremos hasta que encuentre el final
      if (response == null){ 
        // Asignamos el primer item a la respuesta
          response = new Node(f(item.data), null);
        // Pasamos el item al auxiliar para seguir recorriendo
          aux = response;
      } else {
        // Enlazamos el siguiente item en el auxiliar
          aux.next = new Node(f(item.data), null); 
        // Pasamos al item a la cabecera del auxiliar para seguir recorriendo
          aux = aux.next;
      }
      // Le agregamos a la cola el siguiente item
      item = item.next;
    } 
    return response;
  }
  return head;
}
````


### Week challenges (Tuesday) 💻
#### Separating Strings

Kata link: https://www.codewars.com/kata/5977ef1f945d45158d00011f/train/javascript
Instructions: Create a function that takes a string and separates it into a sequence of letters.

The array will be formatted as so:

[['J','L','L','M']
,['u','i','i','a']
,['s','v','f','n']
,['t','e','e','']]
The function should separate each word into individual letters, with the first word in the sentence having its letters in the 0th index of each 2nd dimension array, and so on.

Shorter words will have an empty string in the place once the word has already been mapped out. (See the last element in the last part of the array.)

##### Solution

````
function sepStr(str) {
  let wordsArray = str.split(" ");
  
  let response = [];
  let max = 0;
  
  wordsArray.forEach((item) => {
    if (item.length > max) {
      max = item.length;
    }
  })
  
  for (i = 0; i < max; i++) {
    let auxLetArray = [];
    wordsArray.map((item) => {
      if (item[i]) {
        auxLetArray.push(item[i]);
      } else {
        auxLetArray.push("");
      }
    })
    response.push(auxLetArray);
  }
  return response;
  
}

````
