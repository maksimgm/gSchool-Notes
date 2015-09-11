Javascript(Day1)
===

Ecmascript(JS) released a new version in June 2015.

JS is important because it is the language of the web.

Watch JS video [history of js](https://www.youtube.com/watch?v=t7_5-XYrkqg)

Important to  comment code, especially when collaborating with others.

\n -- go to new line
\ include in string i.e.

"this is a quote \""

output:
"this is a quote ""

####Data Types

1. Numbers

	* integers & floats
	* "The sum of 3 + 4 is " + 3 + 4;

	* output: The sum of 3 + 4 is 34

	* solution:
		"The sum of 3 + 4 is " + (3 + 4);
		
	* % module, used for finding remainder
	
	* ||, &&, !
2. Strings

	* any string that has characters in it will evaluate to true. i.e.

	* false ==	"false"
	* output --> flase
	
3. Booleans
	* True and False
	* They are good for comparisons	
4. Objects
5. Arrays
6. Undefined (null is an object)

	* represents a value that has not been defined

* Variables let you store values.

=======

#### Conditionals & Control Flow

functions---

var feedback = function(name, feedback){

  return `You're doing ${feeback}, ${name}!`;
}


Javascript(Day2)
===

######exercise 1

1. numbers, strings, booleans, undefined/null, 

2. true

3.
```
  var isOdd = function(a){
	  if(a % 2 === 0){
    	return false;
	  } else{
    	return true;	
	  	}	
	  };
		
	  isOdd(3);
```	
	
###### Switch statements:

```
	switch (/* our expression */ ) {
   		case /*value 1*/:
	       // some code
    	   break;
	   case /*another value*/:
    	   // some code
	       break;
	   default:
    	   // the default code, just like the else block
       	break;
	}
```

###### While loop

Another way of constructiing a loop. 

	while(/*Boolean expression*/){
		//Code
	}
example:

```
var timesForPhrase = 10;
var phrase = prompt("What do you want to say " + timesForPhrase + " times?");

var i = 0;
while (i < timesForPhrase)  {
   console.log(phrase);
   i++;
}
```	

###### Do-While loop

A do-while loop will run at least once, even if the condition is not met.

```
// log some squares

var i = 1;
while (i < 10) {
  console.log(i*i);
  i++;
}

// log some squares, another way

var i = 1;
do {
  console.log(i*i);
  i++;
} while(i < 10);

```

###### Arrays

```
var arr = [5,4,3,2,1];
arr[0]; // Returns 5
arr[4]; // Returns 1
arr.length // The length of the array.  Returns 5 in this case

var arrOfArrs = [ [1,2,3], [4,5,6], [7,8,9] ];
arrOfArrs[0][0];  // Returns 1
arrOfArrs[0];     // Returns an array, [1,2,3];
arrOfArrs[2][0];  // Returns 7

```

Most important protery for an array is the `length` method.

A few methods available for adding and removing data in an array:

```
var arr = ['a', 'b', 'c'];
arr.push('d');  // array is now ['a', 'b', 'c', 'd']
arr.pop();      // Array is now back to ['a', 'b', 'c']

arr.shift();    // Array is now ['b', 'c']
arr.unshift('z');   // Array is now ['z', 'b', 'c'];
arr.unshift('q');   // Array is now ['q', 'z', 'b', 'c'];
```
Push and unshift retrun the length of the array.
Pop and shift retrun what you removed.

`.join` - converts array into  string.

`.concat` - joins arrays together.

`.split` - converts a string into an array.

`.indexOf` - returns the position of the occurance of a specified value in a string or an array.

`splice` - Changes the content of an array by removing existing elements and/or adding new elements. i.e.

```
var arr = [1,2,3,4,5];

arr.splice(2,1);

**output** = [1,2,4,5];
```

unsplice-- `arr.splice (2,0,2,3,4)`

.splice('index','how many spaces', 'what to add');
output:

```
[1,2,2,3,4,4,5]
```

###### Objects

Building blocks of JS. You can make very complex structures out of objects. They are very similar to arrays, except that the accessor does not have to be a number. Here is a simple example:

```
var myObj = {}; // Creates an empty object literal
var myObj2 = { name : "Matt", position: "Associate Instructor", dog: "Whiskey"};
myObj2['dog'];  // returns the string "Whiskey"
myObj2.dog;   // Also returns the string "Whiskey"

var persion = { name : "Matt", interests: ["baseball", "coding", "hiking"] };
person.interests[1];   // What does this return?
```

for loop (initialization, condition, increment/decrement)

* initialization determines where to start the for loop
* determines whether to run the loop if the condition is true
* decides how much to increment or decrement


Post fix or pre fix operators: ( i++ v. ++i ):

```
// Postfix 
var x = 3;
y = x++; // y = 3, x = 4

// Prefix
var a = 2;
b = ++a; // a = 3, b = 3
```

Return exits you out of a function, even if something comes after the return.

Debugging Javascript(Day 3)
===
There are many ways of debugging code, the simpliest one is to  place your block of code into the console, using `console.log`, which is part of chrome dev tools. However, this is not as effective when you are working with large blocks of code. 

A pure function is a function that does not change anything outside of that function.

###### Breakpoint

What is done to a certain line of code to stop it in order to narrow down a problem. This allows us to prevent the rest of the code from running after the breakpoint.

Where you click,  is where your code will stop, this is a breakpoint


###### Hoisting 

What does the `var` keyword do?

Variable declarations are processed before any code is executed, therefore declaring a variable anywhere in the code is equivalent to declaring it at the top. This means that a variable can appear to be used before it is declared. This behavior is called 'hoisting', as it appears that the variable declaration is moved to the top of the function or global code.

For this reason, it is recommended to always declare a variable at the top of your scope. This technique makes it clear which variables are function scoped local and which are resolved on the scope chain.





	var x=0;
	function start(){
		var x=y=1; 
	<!--x is declared locally.y is not!-->
	}

	start(x,y); 
	<!--0,1-->
	<!--x is the global variable, as 			expected-->
	<!--y is local-->  



**Expression**

```
var myFunc=function(){
 return "Hello from a function expression"
}
```

**Declaration**

```
foo();

function foo(){
 return "Hi!"
}
```

###### Set Interval & Set Timeout

```
function sayHi(){
	return "Hello... later!"
}

setTimeout(sayHi, 1000)
```

Higher order function- a function that takes in another function as a parameter.

Asynchronous programing- programs are not executed in the order which they are written in. This is the opposite of synchronise code.

```
function goFirst(){
console.log ("Im first");
}

setTimeout(function(){console.log("im next")},0)

function goThird(){
console.log ("Im third");
}

goFirst();
goThird();

```


Stack


![The Stack](https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcRd8vnnxLXGD40oNqKPs7OYf0EuhHsFHKj0lnFN2rw_sfxPUdfPkQ)
	
heap- is a group of objects. Place where memory is kept

stack- specific to functions. LIFO(last one in first one out)

queue- FIFO method. The stack must be empty for things to get moved to the stack.

The DOM (document object model)
===

DOM- The interface between HTML, CSS, and JS. It provides a structural representation of the document, enabling the developer to modify its content and visual representation.

method- a function that is attached to an object. i.e. `getElementById`

```
document.getElementsByTagname('div')[0]
	
	This will return the first tag in the html document.
	
document.getElementsByTagName('h1')[0].innerHTML = "Maksim"

	This will change the first
```


###### How to prevent JS from loanding script tag before html:

1. Place script tag at the end of the `body`.
2.

```
window.onload = function  () {
  
};

This will wait for the DOM to load before loading the script tag. The script must be nested inside of the `window.onload`
```
Methods are functions that are attached to objects.

Add event listener is a method that is attached to something in the DOM.

Add event listener is used as a high order function which is used 



```
var img = document.getElementById('hplogo')

img.addEventListener('click',function(){
  console.log("Foo");
})

```

this- refers to its parent object


Javascript Review
===

Any kind of value that equals a string is a true value.

falsey vlaue- false, 0, ""(empty string), undefined, NaN

truthy value-

Once a condition has been met, it does not bother to continue reading the code.

primatives- string, number, booleans, NaN.

objects- array

arrays are a type of object

	* collections of data structures

splice returns an array, of the numbers that were taken out.

Assesment
===

eventListener

```
window.addEventListener('click',function(){
	console.log("hello!");
})

Event Listeners allow have to be called on something. The following is not okay:

addEventListener('click',function(){
	console.log("hello!");
})

```


Week 3
===

create element-- multiple times.
append element
append child

create element

	var newText = document.createElement('h1')

add text
	
	newText.innerText = "Hello World";

target parent
	
	document.getElemetByTagName('h1')

append to parent
	
	document.querySelector('h1').appendChild(newText)



```
var newH1 = document.create Element("h1")

This creates an element in JS.
In order to add it to the html, you must append it to the child.

var sweet = document.getElementByTagName

sweet.appendChild(newH1)
```

#### TDD

###### Test driven flow

```
Write the test
Watch it fail
Write some code
Watch it pass
Refactor your code
Repeat!
```

TDD means writing a test before you write the test. NOT THE OTHER WAY AROUND. THis can elad to problems. You can write tests that have nothing to do with the code. Test should not be done blindly. It is important to do testing correctly; this is called BDD(Behavioral Driven Development).

**Unit Test**- Low level tests to check functionality of classes, methods, or functions. So far we have been running unit tests on small examples using Jasmine or RSpec. Unit tests run fast! This is our primary focus today!

**Acceptance/Feature tests**-High level tests conducted to make sure all requirements are met. In Rails we will use the testing tools RSpec and Capybara to run acceptance tests. Acceptance tests run slow!

**Integration / functional / service-level testing**-Testing between unit and acceptance tests. In most cases this will involve testing RESTful APIs. Don't worry about this one too much right now!

Unit test support the accepted test.

##### Jasmine

One of the things that can make jasmine a little confusing is that you can either run it in the browser, or from the command line using node. Since we have been doing javascript in the browser so far, we will start there.

First we need to install the jasmine gem.
```
$ npm install -g jasmine
```
And make sure that it works, create a directory called jasmine-testing-fun, then type:

```
$ jasmine init
```
This will generate the following in our jasmine-testing-fun directory:

spec/support/jasmine/jasmine.json
This file just tells Jasmine where to find the tests we are writing and any helper files.

#### Modules

Encapsulate code, modulization. This way you can change one thing in the code and only effect what you changed. 

```
module.export 

This is specific to the terminal, (node).
This cannot be used in the browser.
function each(arr,callback){
  for(var i=0; i < arr.length; i++){
    callback(arr[i]);
  } 
}

```

```
Module.exports={}

&

require = {..application name}

```
###### 2 kinds of modules

common js model

```
var $ = require('jquery');
exports.myExample = function () {};
```
amd modules- i.e. require js.

```
define(['jquery'] , function ($) {
    return function () {};
});
```

#### Iterations

Methods that are built into JS. All of these methods can only be used on arrays.

Methods are functions that are attached to objects.

```
// FUNCTION TIME!
function each(arr,callback){
  for(var i=0; i < arr.length; i++){
    callback(arr[i]);
  } 
}


// METHOD TIME!
var arr;
arr.each = function(arr,callback){
  for(var i=0; i < arr.length; i++){
    callback(arr[i]);
  } 
};
```
#### 4 main iterations
All of these are higher order functions.
######forEach
Iterate through an array, but you don't care about what it returns. Most of these functions only take in one parameter. The callback function takes in 3 parameters, but the higher order function only takes in one.
**forEach will always return undefined**
forEach does not care about the return word.

```
[1,2,3].forEach(function(element, index, array){
	console.log(element);
})
```

```
var arr = [1,2,3,4,5];

arr.forEach(function(element,index,array){
  console.log(element * 2)
});
```

```
var arr = [[1,2],[3,4],[5,6]]

arr.forEach(function(el){
  el.forEach(function(innerEl,innerIndex){
	console.log(innerIndex);
  })
})
```

```
multi([1,2,3],2)

function multi(arr,num){
  arr.forEach(function(element,index,array){
   console.log(element * num);
  })  
}
```
######map
```
multi([1,2,3],2)

function multi(arr,num){
  arr.map(function(element,index,array){
   return element * num;
  })  
}
```

```
var firstArr = [1,2,3]

function multi(arr,num){  
  return firstArr.map(function(element,index, array){
	return element * num
  });
}
```

```
var arr = [1,2,3,4,5]

arr.map(function(element,index,array){
  return element * 5
})

```

```
multi([1,2,3,4,5],5)

function multi(arr,num){
  return  arr.map(function(element,index,array){
    return element * num;
  })  
}
```
######filter

Returns the result of the truthy conditions.
Anytime there is an expression that evaluates to false, it will not return.
Filter will always return an array to you.

```
var newArr = [-3,-2,1,0,1,2,3].filter(function(elem){
  return elem > 0
});

```


######reduce

Reduce serves the purpose of reduce some data. First two parameters are, start and end.


```
var arr = [1,2,3,4,5]

numArr.reduce(funciton(start,el){
  return + el
},0)
start refers to the begining value
```

```
var arr = [1,2,3,4,5]

var newArr = arr.map(function(elem){
   return elem * 5;
})


newArr.reduce(function(start,el){
  return start + el
})
75
```

#### Data structures, algorithms, CS essentials

lower level languages - C, C++
higher level languages - JS, Ruby

Measuring the preformance of an algorithm

algorithm- A way to do something.

Computers are not good at searching and sorting. Most of the algorithms we create will be be on sorting and searching.

##### Algorithm Complexity: Big O

######Asymptotic Notation

[http://bigocheatsheet.com/](Cheat sheet)

Often in software engineering, we need to choose between algorithms and data structures which are suited to different tasks. We need to analyze our own tasks, and the data we will be using, and make informed decisions about what tools to use. Sometimes one tool is better in every way than another, but more often we have to sacrifice memory use for computation speed, or sacrifice speed of deletions to increase speed of insertions, and so on.

So what does it mean for an algorithm to be efficient? We can't measure in terms of seconds, because hardware and software are different across all machines. One program may run slower than another because of different software or because one machine is older than other - it's like comparing apples and oranges.

So how do we compare 2 algorithms regardless of hardware and software? We measure the asymptotic complexity of a program and a notation called big O. You can see the mathematical definition here.

What this basically means is that big O measures how fast a program's runtime grows asymptotically - as the size of the inputs increase towards infinity, how does the runtime of your program grow?

Imagine counting the letters of a string and going one by one - This algorithm would run at a linear time, for each letter n you count n times, this is also known as O(n). The time to traverse a string is proportional to the number of characters.

Say O(n) is not fast enough? What if you already stored the length and then tried to find it again? You could run 1 calculation to find the length. This program would run equally fast on a 2 character string or a 1000 character string. Accessing a variable is an asymptotically constant time operation or O(1). The runtime does not change as the size of the inputs grow.


![http://www.daveperrett.com/images/articles/2010-12-07-comp-sci-101-big-o-notation/Time_Complexity.png](A visualization of big O)

#### Data Structures
Time complexity is how much time it takes based on the number of elements. Space complexity refers to how much memory does it take for hte algorithm to work. How much space does it take(how efficent is it?)?

A data structure is a way to store and organize data in a computer, so that it can be used efficiently. The key word here is "efficiently". At the end of the day, we are only interested in data structures that are efficient (we will discuss how we measure efficiency later).

With the definition out of the way, let's think about a data structure we have used since the beginning of our coding journey. How about an Array? An array is a very simple data structure, but what does it do well? What does it not do well? Start here [http://stackoverflow.com/questions/8423493/what-is-the-performance-of-objects-arrays-in-javascript-specifically-for-googl.](data structure info)

#### OOP

Objects consists of key value pairs. 1st, key; 2nd, value; 3rd, method.

###### Constructors

Classes are created using constructors. We can use a constructor function to create multiple objects that share the same properties. The constructor of an object is a reference to the function which made the object. 

```
function Movie(name,releaseYear){
    this.name = name;
    this.releaseYear = releaseYear;
}

var movie5= new Movie("To Kill a MockingBird", 1962);

movie5;
```
Without using the new key word, it will return undefined.

Whatever comes after key will determine the name of the key.

```
var movie = new Movie("giberish", 2000)

1. new object is created
2. movie.constructor is set to Movie
3. Points movie to the Movie prototype
4. Calls the constructor function with this = movie

```

**Avoid return statements**

###### Pitfalls

1. When using the constructor, don't try to call a constructor without the new keyword. What happens if you do?

2. Always make sure the keyword this is on the left hand side: this.foo = foo. Otherwise, the values you set won't be associated with your new object!

3. return statements in a constructor does not do anything (See this Stackoverflow exchange).

###### Prototypes
```
function Movie(name,releaseYear){
    this.name = name;
    this.releaseYear = releaseYear;
}

Movie.prototype.wachedAgain = function(){
	this.watchCount++
}
```

Prototype is useful for inheritence. Declare methods using prototypes.

###### Why is it useful to write code in terms of objects when programming?

**Encapsulation**- The practice of packing data and functionality into an object. The data and functionality have a clearly defined set of interactions.

**Abstraction**-The set of interactions that is available to an object. Creating an abstraction allows the programmer to think about objects at a higher level, instead of dealing with the details of how the object works.


```

function Animal() {
    this.awake = false;
}

Animal.prototype.feed = function() { return "NOM NOM NOM"; };
Animal.prototype.speak = function() { return "growl"; };


function Pig() {
    Animal.call(this);
}

Pig.prototype = Object.create(Animal.prototype);

Pig.prototype.constructor = Pig;


Pig.prototype.speak  = function() {
    return "oink";
};

var p = new Pig();
p.speak();

```
**call**- transfers a method form one object to another. Can only be called on functions!!!



`instanceof` tests whether an object has in its prototype chain the prototype property of a constructor.

Week 4
===
	$('a').text("happy monday");
	
jQuery packages up things which you want to do in the DOM.

	$('a:eq(1)').text("happy monday");
	
Grab individual selectors ^^^

Parsing query strings

```

function parseQueryString(url) {
  var queryPairs = url.split("?")[1].split("&");
  return queryPairs.reduce(function(start,el){
    start[el.split("=")[0]] = el.split("=")[1];
    return start;
  },{});
}

```

#### How the Web Works

**Application**

**Transmission/Transfer**-HTTP(hyper text mark up language)

**Internet**- IP address

**L**-The network. The physical hardware(not so concerning as a web developer)

The above encompesses the internet. 

protocol- the way the internet communicates.

The DNS translates from IP addesses to a website.

TCP- governs the way data is transfered once it is found.

HTTP- hyper text transfer protocol. This goverens communication between client and server.

**All data must be stringified!!!!**

Client server communication is on the Application level
**client and server communication...**

client(browser)- the client renders html, css, and JS

server- serves content or files. Also...databases. They are physical machines which stroe information

**Request respond cycle**- HTTP governs this cycle. The client makes a request... the request goes to some server. **Servers give back responses, and clients make requests.** 

Along with requests and responses, there are headers. Headers are metadata. Headers contain additional pieces of info that can be used.

**AJAX**- Enables us to get data from a server without refreshing the page. Originally, created by microsoft. XHR(XMLHttpRequest) makes requests to servers. All ajax functions are higher order.

XHR- technology used to make AJAX requests

^^**A**synchronious **J**avascript **A**nd **X**ML


**JSON**- Javascript object notation. Stringafied object. A text based format used to communicate between clients and servers. IT HAS TO BE TEXT!!! By far the defacto.

**API**-Application programming interface. An interface for computers to communicate to one another.

Companies will build APIs. They give people access to their methods.

```
Always need a url and a callback funciton.

$.ajax({})

```

i.e

```

$.get("https://api.github.com/users/maksimgm", function(response){
  console.log(response);
})

```

#### Local Storage

The web is stateless meaning, there is no built in way to maintain state(remember things). The tool that we will use to remember things is `localStorage`, which is a browser based way of storing information.

	*console.dir
	console.table
	console.warn
	console.error
	

Local Storage- The data stored must be a string. Set things using...

	localStorage.setItem
	setItem
	(key,value)
	
	Get the method using:
	localStorage.setItem("key")
	
	Remove a given item:
	localStorage.removeItem("key")
		
KEYS AND VALUES MUST BE STRINGIFIED.
	
Using local Storage v. set a variable...the console will forget the variable that was set. However local storage will remember it. It will only rememeber it at that domain name.

	localStorage.clear()
	Will wipe all the local storage in that domain name.

JSON method- stringify

	var arr = JSON.stringify([1,2,3,4,5])
	
	return-- "[1,2,3,4,5]"
	
	localStorage.setItem('arr',arr)
	
	JSON.parse(localStorage.getItem("arr"))
	
	
#### Design Presentation

3-Step Learning Process

1. Set the stage
	
	* What you are going to learn and why it is important.
	
2. Play

	* Have fun when you are playing.

3. Reflect

##### Objectives

* Describe and folow the 5 rules of free-writing.
* Reinforce  topics you've learned through 4 wrtiting games:
	* 	100 bad idead
	* 	3 dimentional writing
	* 	leading questions
	* 	paper conversations
* Discuss the power fo writing as a eprsonal learnign tool.
* Discuss the benefits of your writing publicly

###### Rules of Freewriting

1. write for yourself
2. write fast and continuously
3. work against a time limit
4. write the way you think
5. go with the thought

###### 100 bad ideas

quantity breeds quality

accidental genius- Mark Levy

the 5 elelemnts of effective thinking

a mind for numbers

**The generation effect**

Illusion of competency--the idea that you understand a problem that has already been solved.

####### 3-dimensional writing

Machine learning has revolutionized how we as human beings interact with computers and software. It has changed our lives, as a layman you may say that your smartphone is the best thing in the world, because it rememebrs your searchhistyory, where you have been(shoped, bought food, or gone out). Although this is convinient, it will inevitablly become problematic. High level programers are starting to write insanly mind blowing algorithms whihc can teach a car how to drive. This car detects human movement, obsticales, and pretty much everything else. Only, 11 have crashed thus far, and all of them have been the other drivers fault. As I said before, this is amazing, but we should be scared shitless. WHY you may ask, because machine a reaching a pount where they are learning from their mistakes to improve whatever it is they are doing. This inevitablly leads them to do better than certain humans. This will result in people losing jobs.


future me

what sets you apart fromother developers?

I think that going to a 6 month immersion course as well as starting a blog posts, has allowed me to immerse myself into code for a longer period of time which inevitabbly led to me growing in my skill set.

#### Review

###### OOP(object oriented programing)

Helps you orginize your code. Use objects to structure your code. It relies on classes, which are blueprints. Classes should be very obstract and vague.

Classes allow you to avoid repetition. Making copies of classes--instanciations. Constructer function should be capitalized.

Use the new keyword that you have named, not ones that are built in.

Flyweight pattern- One function that creates many things.

prototypes are objects. 

Inheritence- Methods and properties receieved from another constructor functions prototype.

```
function Vehicle(make,model,year){
  this.make = make;
  this.model = model;
  this.year = year;
}

Vehicle.prototype.honk = function(){
  alert("beep")
}


Car.prototype = Object.create(Vehicle.prototype);
Car.prototype.constructor = Car;

function Car(make,model,year){
  this.make = make;
  this.model = model;
  this.year = year;
}

Car.prototype.honk = function(){
  alert("beep from a car")
}

var firstCar = new Car("toyota", "corollaS", 2004)

// var firstCar = new Car("toyota", "corollaS", 2004);

firstCar.honk();

var secondCar = new Car("honda", "civic", 2007);

secondCar.honk();

```
Call only borrows given methods. Whereas, inheritence borrows the parent objects prototypes.

###### Borrowing the invocation of function
Call & Apply

These can only be used on functions.

```
1-- Call(thisArg,make,model,year)
2-- Apply(thisArg,[make,model,year])

apply is easier to work with
```

###### internet

protocols- a set of rules governing procedures. 

tcp- maintains that data gets transfered from one place to another

ip-concered with where data goes.

http- transfering of text between client and server.

xhr- xml http request. XHR is a JS object. Created to refresh webpages without clicking refresh.

Week 5
===

#### Review

data attributes- `data-attr` It is the equivolent of an ID which is used to manipulate your JS.

```
data-___= " "

```

attribute- Additional description added to a tag. This goes inside fo the html tag**May or may not change the presentation**

fast-forward merge (these are prefeered)--

recursive merge-- when merging using this strategy, a message will display in sublime. 

	git branch -a

shows remote branches

##### Upstream

the remote that you only have pull access to.

Week 6
===

##### Recursion

A function that calls iteself. Another option is a loop. Need to make a lot of function calls. When you deal with recursion, you need a counter to stop the calling of the function, aka base case.

**base case**- a condition set to leave a recursive function.

In a traditional for loop, you know where it ends. 

Recursion is very elegant.

A function pushed to the stack is a frame. Push and pop refers to the end of something.

```

function factorialRecursive(n){
    if(n === 0){
        return 1;
    }
    return(n * factorialRecursive(n-1))
}

```


memoize-store the result of an expensive function.

##### HTTP

It is the network used to deliver cirtually all files and other data(collectively called resources) on the World Wide Web.

	http://www.domain.com:1234/path/to/resource?a=b&x=y
	
	protocol= http
	host= www.domain.com
	port= 1234
	resource path= path/to/resource
	query= ?a=b&x=y

###### VERBS

1. GET- fetch an existing resource. The URL contains all the nessecary information the server needs to locate and return the resource

2. POST- create a new resource. POST request usually carry a payload that specifies the data.

3. PUT- update an existing resource. The payload may contain the updated data for the resource.

4. DELETE- delete an existing resource

###### Status Codes

1xx: informational messages

2xx: successful

 200- okay

3xx: redirection
 301-moved permenantly: the resource is now located  	at a new URL.

4xx: client error

5xx: server error

WHY DO WE CARE?

We use frameworks like ExpressJS and Rails to tell our server how to handle client requests.

Understanding HTTP is crucial for having a clean, simple and RESTful interface between two ends.
##### Express

It is a javascript framework.

New version of node...It supports ECMA script 6.

```
(a,b)=> a+b

Same as:

function(a,b){
  return a+b;
}
```

##### Middleware

Code that we want to execute between the request and response cycle.

A function with access to the request object, the response object, adn the next middleware in the application's request-response cycle, commonly denoted by a variable named next.

This is not a concept unique to Express. An example of middleware:

	app.use(express.static(_dirname + "/public"));

##### Get

Get something from the server.

##### Post

Used to post information to the server. NO query string when submitted.
Need to install body-parser whenever you want to use a post request.

