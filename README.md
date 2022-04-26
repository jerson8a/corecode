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

