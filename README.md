# Javascript-day4
## Objects
a. Let's say in the Amazon project, we have a basketball product. This product has a name of 'basketball', a price of 2095 cents. Create an object to represent this product and display it in the console.
```
<script>
      const product={
        name: 'Basket Ball',
        price: 2096
      }
      console.log(product);
    </script>
```
b. Continuing from 8a, let's say we want to increase the price by 500 cents. Use dot notation to increase the price, and display the updated object in the console.
```
const product={
        name: 'Basket Ball',
        price: 2096
      }
      console.log(product.price+500);
```
c. Using bracket notation, add a property 'delivery-time' to the object with the value '3 days'. Display the updated object in the console.
```
 product['deliveryTime']='3 days';
  console.log(product);
```
d. Create a function 'comparePrice(product1, product2)', which takes 2 products (with 'name' and 'price' properties) and returns the product that is less expensive. Create 2 products and try out the function.
```
function comparePrice(product1, product2){
  if(product1.price<product2.price)
  return product1;
  else
  return product2;
}
const product1={
  name: 'oil',
  price: 200
};
const product2={
  name: 'rice',
  price: 400
};
console.log(comparePrice(product1,product2));
```
e. Create a function 'isSame Product (productl, product2)', which returns true if 2 products have the same values inside ('name' and 'price'). If not, return false. Create 2 products and try out the function. (Hint: objects are references so you can't compare them directly).
```
function isSameproduct(product1,product2){
    if(product1.name===product2.name)
    return true;
  else
  return false;
  }
```
f. Using Google or an A.l. tool, search how to convert a string to all lowercase with JavaScript ('Good Morning' => 'good morning')
```
let lowString='HELLO WORLD!';
  console.log(lowString.toLowerCase());
```
g. Search how to repeat a string many times ('test' 2 times => 'testtest')
```
console.log(lowString.repeat(2));
```
h. We'll add localStorage to the calculator project. First, make a copy of
the project from exercise 7j (see the solution for 7j if needed).
• Whenever we update the calculation, save it using .setItem()
• When the page first loads, get the calculation using.getItem()
Use a default value of " if a calculation doesn't exist in local storage
```
button onclick="
  calculations=eval(calculations);
  console.log(calculations)
  localStorage.setItem('calculations',calculations)">=
  
</button>
</p>
<button onclick="
  calculations=' ';
  localStorage.setItem('calculations',calculations);
">clear</button>

<script>
  let calculations=localStorage.getItem('calculations')||'';
  function calculate(value)
  {
    calculations+=value;
    console.log(calculations);
  }
  function saveCalculation(){
    localStorage.setItem('calculations',calculations);
  }
</script>
```
i. We'll improve the coin flip game from exercise 6j to be like the rock
paper scissors game.
• Copy the code from exercise 6j (see the solution for 6j if needed).
• Create 2 buttons to play the game
heads
tails
When clicking 'heads' play the game with guess = 'heads'.
• When clicking 'tails' play the game with guess = 'tails'.
• Create a function 'playGame(guess)' to reuse the code.
```
<button onclick="
      playGame('Heads')">
      Heads
    </button>
    <button onclick="
    playGame('Tails')">
      tails
    </button>
    <script>
      function playGame(guess)
      {
        const randomNumber=Math.random();
        console.log(randomNumber);
        const result=randomNumber<0.5 ? 'Heads' : 'Tails';
        console.log(guess===result ? 'You win!' : 'You Lose!');
      }
    </script>
```
j. Create a score object { wins: 0, losses: 0 }, update the score each time after playing, and display the score in the console.
```
let score={
  wins: 0,
  lose: 0
};
if(guess===result)
  score.wins++;
  else
  score.lose++;
console.log(score);
  }
```
k. Use localStorage to save and load the score (hint: you'll need to use JSON.stringify() to convert the score object to a string).
```
const score=JSON.parse(localStorage.getItem('score'))||{
  wins: 0,
  lose: 0
};
localStorage.setItem('score',JSON.stringify(score));
```
## Document Object Model (DOM)
Lesson 9 Exercises - Document Object Model (DOM)

a. Create a <button>9a</button>. Use document.querySelector('button') to get the button from the page, and then display it in the console.
```
<button>9a</button>

<script>
console.log(document.querySelector('button'));
</script>
```
b. Continuing from 9a, create another button <button>9b</button> below. Using JavaScript, change the text in the second button to '9b done!' (hint: add a class and use .querySelector).
```
<button class="js-button">9b</button>

<script>
console.log(document.querySelector('button'));

document.querySelector('.js-button')
  .innerHTML = '9b done!';
</script>
```
c. Create 2 buttons 'heads' and 'tails', and a paragraph (<p></p>) underneath. When clicking the 'heads' button, display 'You chose: heads' in the paragraph. When the 'tails' button, display 'You chose: tails'.
```
<button onclick="
document.querySelector('.js-choice')
  .innerHTML = 'You chose: heads';
">heads</button>

<button onclick="
document.querySelector('.js-choice')
  .innerHTML = 'You chose: tails';
">tails</button>

<p class="js-choice"></p>
```
d. Create a text box (<input>) and a submit button. When clicking 'Submit', display 'Your name is: ${text}' on the page (${text} = the text inside the text box) (hint: use .value to get the text inside an <input>).
Simo
Submit
```
<input placeholder="Name" class="js-name-input">

    <button onclick="
      const inputElement = document.querySelector('.js-name-input');
      document.querySelector('.js-message')
        .innerHTML = `Your name is: ${inputElement.value}`;
    ">Submit</button>

    <p class="js-message"></p>
```
e. Modify exercise 9d so that when you press 'Enter' in the <input>, it will also display the same message on the page (hint: use onkeydown and the event object).
```
<input placeholder="Name" class="js-name-input"
      onkeydown="
        if (event.key === 'Enter') {
          const inputElement = document.querySelector('.js-name-input');
          document.querySelector('.js-message')
            .innerHTML = `Your name is: ${inputElement.value}`;
        }
      ">

    <button onclick="
      const inputElement = document.querySelector('.js-name-input');
      document.querySelector('.js-message')
        .innerHTML = `Your name is: ${inputElement.value}`;
    ">Submit</button>

    <p class="js-message"></p>
```
f. Continuing from 9e, create a function to reuse the code (if you already did this, skip this exercise).
```
<input placeholder="Name" class="js-name-input"
      onkeydown="
        if (event.key === 'Enter') {
          displayMessage();
        }
      ">

    <button onclick="
      displayMessage();
    ">Submit</button>

    <p class="js-message"></p>

    <script>
      function displayMessage() {
        const inputElement = document.querySelector('.js-name-input');
        document.querySelector('.js-message')
          .innerHTML = `Your name is: ${inputElement.value}`;
      }
    </script>
```
g. Create a file 9g.html and copy the code from 09-dom-projects.html into this file. In the Amazon Shipping Calculator, enter a cost of 7.99 and click 'Calculate'. What issue do you see? Find a fix for this issue.
7.99
Calculate
$17.990000000000002
```
function calculateTotal() {
        const inputElement = document.querySelector('.js-cost-input');
        let cost = Number(inputElement.value) * 100;

        if (cost < 4000) {
          cost = cost + 1000;
        }
        document.querySelector('.js-total-cost')
          .innerHTML = `$${cost / 100}`;
```
h. Let's create the project on the right: Whenever we type in the text box, update the text on the page. To do this, we'll learn another event called <input onkeyup="...">.
Type something
49K
This runs code after we press a key and release it (key comes up).
```
<input placeholder="Type something" class="js-input"
      onkeyup="
        const inputElement = document.querySelector('.js-input');
        document.querySelector('.js-message')
          .innerHTML = inputElement.value;
      ">

    <p class="js-message"></p>
```

i. We'll improve the Cart Quantity project.
Make a copy of exercise 71 (see the solution for 71 if needed).
Create a paragraph (<p></p>) to display the quantity.
• Whenever we update the quantity, display it on the page instead of in the console. Also, display the quantity when page first loads.
Show Quantity
Add to Cart
+2
+3
+4
+5
Remove from cart
-2
-3
Cart quantity: 6
```
<p class="js-cart-quantity"></p>

    <script>
      let cartQuantity = 0;
      displayCartQuantity();

      function updateCartQuantity(change) {
        if (cartQuantity + change > 10) {
          alert('The cart is full');
          return;
        }

        if (cartQuantity + change < 0) {
          alert('Not enough items in the cart');
          return;
        }

        cartQuantity += change;
        displayCartQuantity();
      }

      function displayCartQuantity() {
        document.querySelector('.js-cart-quantity')
          .innerHTML = `Cart quantity: ${cartQuantity}`;
      }
    </script>
```
j. We'll improve the calculator project.
• Make a copy of exercise 8h.
• Whenever we update the calculation, display it on the page instead of in the console.
12+
When the page first loads, if a calculation exists in localStorage, display it on the page.
```
<p class="js-calculation"></p>
let calculation = localStorage.getItem('calculation') || '';
displayCalculation();
function updateCalculation(value) {
  calculation += value;
  displayCalculation();
  localStorage.setItem('calculation', calculation);
}
function displayCalculation() {
  document.querySelector('.js-calculation')
    .innerHTML = calculation;
```
