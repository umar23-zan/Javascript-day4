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
