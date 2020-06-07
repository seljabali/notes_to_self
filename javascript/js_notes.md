Variables
=======
const foo = 2;
let bar = 23;


Strings
======
const bar = 3
const foo = `${bar} = 

3`

Functions
========
function add(num,1 num2) {
    const result = num1 + num2;
}


Objects
=======
const entry  {
    operation: 'ADD',
    operand1: 1,
    operand2: 40
}


HTML
======
<script src="assets/scripts/foo.js" async></script>
Doesn't parse until the JS file has been entirely downloaded. 
Executes asap without order if there are subsequent scripts.
Good for independent scripts

<script src="assets/scripts/foo.js" defer></script>
Doesn't parse until HTML has been entirely parsed
Garauntees order

Inlined scripts
Executed immediately. 
Generally not a good practice.
If external are referenced, the source trumps the inlined.


Debug
======
Open using incognito mode to avoid extensions running


Click Listeners
===========
addBtn.addEventListener('click', foo());


Links
=====
- JavaScript Basics: https://developer.mozilla.org/en-US/docs/Web/JavaScript

- Variables: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables

- Operators: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Math

- Functions: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions

- Arrays: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays

- Objects: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics

- ECMAScript : https://www.ecma-international.org/publications/standards/Ecma-262.htm
