# JS_1st_week_tasks

Declare a variable named page and constant named limit. Initialize the variable with the value 1 and the constant with the value 10.


Answer = 
let page = 1;
const limit = 10;

-------------------------------------------------

Can you change the value of a constant after initializing it?

Answer = No, because const can not be changed

-------------------------------------------------

In the following code, in which of the numbered places (// 1, // 2, // 3, // 4, // 5, // 6, // 7 and // 8) is the variable user defined and usable?

// 1
 
const testUser = () => {
    // 2
 
    let user = 'Jake';
 
    // 3
 
    if (user === 'Steve') {
        // 4
    }
 
    // 5
 
    for (let i = 0; i < 10; i++) {
        // 6
    }
 
    // 7
}
 
// 8


Answer = 3-4-5-6-7

-------------------------------------------------

In the code from the previous exercise, in which of the numbered places is the variable i defined and usable?

Answer = 6

-------------------------------------------------

What is the result of this operation:

Answer = 30

-------------------------------------------------

What is the result of this operation:
10 + '20'

Answer = 1020

-------------------------------------------------

You have a number in a variable:
const number = 13;
Use the ternary operator and the modulo operator to produce a string 'odd' if the number is odd or the string 'even' if it is even. It should be done in a single statement (single line of code) that begins like this:
const verdict =      ; // your code should go before the semicolon
Log the result into the console with console.log(verdict);
Then change the first line to say const number = 12; and try again.

Answer = 

const number = 13;
const verdict = number % 2 === 0 ? "even" : "odd" ;

-------------------------------------------------

Declare a function logMyAge (no arguments). It is supposed to log your age into the console (just hard-code your age into the code, don't calculate it).
Then call the function.

function logMyAge ( ) {
	console.log(24)
}

call ======== logMyAge (24)

-------------------------------------------------

Declare a function greet which would accept one argument named who. It is supposed to log the sentence 'Hello, XXX!' to the console, where XXX is the value of the argument who.
Then call the function like this: greet('world'). It should log 'Hello, world!' into the console.

Answer = 

function greet (who) {
	console.log(`Hello, ${who}!`)	
}

greet (who)

-------------------------------------------------

Put this into the body of your HTML document:
<div id="red-box" class="box box--red">
    The <strong>red</strong> box
</div>
<div class="box box--green">
    The <strong>green</strong> box
</div>
Write JavaScript to find the "red box" <div> element in the document using .getElementById. Once found, put it in a constant and log it into the console.

Answer =  

const element1 = document.querySelector('#red-box').innerHTML;
console.log(element1)

-------------------------------------------------

Using the HTML code from the exercise above, write JavaScript to find the "green box" <div> element in the document using .querySelector. Once found, put it in a constant and log it into the console.

Answer =  

let element2 = document.querySelector('.box--green').innerHTML;
console.log(element2)

-------------------------------------------------

Define a function getBoxByColor which would accept one argument color. It will find the box with the correct color using .querySelector and return it.
Then use it like this:
const box = getBoxByColor('green');
console.log(box);

Answer =

function getBoxByColor (color) {
	return document.querySelector('.box--' + color);
}
const box = getBoxByColor('green');
console.log(box);

-------------------------------------------------

Put this into the body of your HTML document:
<ul class="cars">
    <li>Skoda</li>
    <li>VW</li>
    <li>Ford</li>
    <li>Hyundai</li>
    <li>Jaguar</li>
</ul>
Write JavaScript to select all the <li> elements that are in the <ul class="cars"> element. Log the result (a NodeList) into the console.

Answer = 

let thisListOfCars = document.querySelectorAll('.cars, ul>li')
console.log(thisListOfCars)

-------------------------------------------------

Using the HTML from the previous exercise, define a new empty array in a variable called brands.
Loop through the <li> elements, extract their contents with .innerText and add every brand name as a new element of the array brands.
Then log the value of the array brands into the console.

Answer = 
[]

let brands = []
let data = document.querySelectorAll('li')

for (let i = 0; i < data.length; i++) {
	brands.push(data[i].innerText)
}

console.log(brands)


//let selectAllFunction = document.querySelectorAll('li').innerText;
//let brands = document.getElementById('brands').innerText;
//console.log(selectAllFunction)

-------------------------------------------------

Modify the code from the previous exercise so that the looping ends when the array brandsalready has 3 elements. Use .length and break; to do that.

Answer = 

let brands = []
let data = document.querySelectorAll('li')

for (let i = 0; i < data.length; i++) {
	brands.push(data[i].innerText)
	if (i === 2) {
		break;
	}
}
}

console.log(brands)

------------------------------------------------

Modify the code from the previous exercise so that when during the looping you encounter the brand Ford, it will be skipped and not added to the array. Use continue; to do that.

Answer = 

let brands = []
let data = document.querySelectorAll('li')

for (let i = 0; i < data.length; i++) {
	if (data[i].innerText == 'Ford') {
		continue;
	}
	brands.push(data[i].innerText)
}
console.log(brands)  

------------------------------------------------

Take the following code and put it into your code:

const cart = {
    total: {
        amount: 91.6,
        currency: 'CZK'
    },
    items: [
        {
            name: 'Apples',
            amount: '2kg',
            price: 62.6
        },
        {
            name: 'Cinnamon',
            amount: 1,
            price: 29
        }
    ]
}
Try to name the data types of the following:

typeof cart
'object'
typeof cart.total
'object'
typeof cart.total.amount
'number'
typeof cart.items
'object'
typeof cart.items[0]
'object'
typeof cart.items[0].name
'string'
typeof cart.items[0].amount
'string'
typeof cart.items[1].amount
'number'
------------------------------------------------

Stringify the cart constant from the previous exercise into a JSON string and log it into the console.

Answer = 

cart
const obj = {cart}
let str = JSON.stringify(obj)
console.log(str)

* I finally got this =
{"cart":{"total":{"amount":91.6,"currency":"CZK"},"items":[{"name":"Apples","amount":"2kg","price":62.6},{"name":"Cinnamon","amount":1,"price":29}]}}

------------------------------------------------

Parse the JSON string that was the result of the previous exercise into a new constant named shopping_cart and log the constant into the console.

Answer = 

const shopping_cart = JSON.parse(str);
console.log(shopping_cart);

------------------------------------------------

Declare a variable named cheapest and initialize it with the value null.

Then use .forEach to loop through the array shopping_cart.items. Your goal is to find the cheapest of the products in the cart and put it into the variable cheapest.

In the end, log the value of cheapest into the console. It should show this object:

{
    name: 'Cinnamon',
    amount: 1,
    price: 29
}

Answer = 

let cheapest = null;
cheapest = shopping_cart.cart.items[0].price;
let cheapest_ind = 0;

shopping_cart.cart.items.forEach((element, i) => {
	if (element.price < cheapest) {
		cheapest = element.price
		cheapest_ind = i
	}
})
console.log(shopping_cart.cart.items[cheapest_ind])

-------------------------------------------------

In your HTML code, create a new button like this:

<button class="remove-cheapest">Remove cheapest product</button>
Write JavaScript code so that when the button is clicked, the cheapest of the products in the shopping_cart constant is found and removed from shopping_cart.items.

Also after clicking of the button, log the value of shopping_cart into the console. You should see the object of "Cinnamon" disappear.

Answer = 

<button class="remove-cheapest" onclick="cartcleaner()">Remove cheapest product</button>


function cartcleaner () {
	let cheapest = null;
	cheapest = shopping_cart.cart.items[0].price;
	let cheapest_ind = 0;
	shopping_cart.cart.items.forEach((element, i) => {
		if (element.price < cheapest) {
			cheapest = element.price
			cheapest_ind = i
		}
	})
	shopping_cart.cart.items.splice(cheapest_ind, 1)
}


-------------------------------------------------

In the HTML of your page, add this element:

<ul class="items"></ul>
Declare a function displayItems which will accept one argument - an object similar to the one that we have in constants cart and shopping_cart.

The function is supposed to create HTML <li> elements within the <ul class="items"> element, one for each of the items in the cart.

Then call the function, passing the shopping_cart to it as argument like this: displayItems(shopping_cart).

The resulting HTML might look like this.

<ul class="items">
    <li class="items__item">Apples (2kg)</li>
    <li class="items__item">Cinnamon (1)</li>
</ul>

Answer =



-------------------------------------------------

If you did not do it already, change the code from the previous exercise to use .appendChild instead of .innerHTML to add the list items.

Answer =



-------------------------------------------------

First make sure to remove all contents of the <ul class="items"> element at tbe beginning of the displayItems function.

Then add a call to the function displayItems also when the <button class="remove-cheapest"> button is clicked (at the end of that process).

Clicking the button should now see items disappearing from the list.

Answer =



-------------------------------------------------

To your HTML code add this:

<input class="item-name-input" type="text" name="name" value="" placeholder="Item name">
<input class="item-amount-input" type="text" name="amount" value="" placeholder="Item amount">
<input class="item-price-input" type="number" name="price" value="" placeholder="Item price">
<button class="add-item">Add to cart</button>
Write JavaScript code so that when the button "Add to cart" is clicked, a new item object will be added to the shopping_cart.items containing the relevant information from the input fields.

At the end of that process, make sure to call displayItems again.

Clicking the "Add to cart" button should now keep adding items into the list.

Answer =



-------------------------------------------------

In the previous process, write a condition, so that if any of the input fields are empty (contain a falsy value), the item will NOT be added to the items.

Answer =



-------------------------------------------------

In the previous process, make it so that when the item is successfully added to the items, the input fields are cleared (their value attributes reset to "")

Answer =
