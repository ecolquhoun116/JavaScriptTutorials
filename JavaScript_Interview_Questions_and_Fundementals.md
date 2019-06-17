Java Script Interview Questions and Fundamentals

//ECMA Script Documentation



Q1 How many types of ways to integrate JS code inside your web page?

​	1) Script Tags (Explore Types of script tags, type : Babel, Module, etc.,)

​	2) Script with src attribute

​	3) Node Program (without web pages)

Q2 Console Methods 

and Display Console Messages with Font Sizes and Colors

> console.time();
>
> var obj = {	
>
> ​	fname : "Eric",
>
> ​	lname : "Colquhoun",
>
> ​	age : 21,
>
> ​	country : "USA"
>
> }
>
> if(obj){
>
> ​	//could try if(obj.age>30)
>
> ​	console.table(obj); //pretty print object
>
> ​	console.timeEnd(); //calculate time
>
> }
>
> else{
>
> ​	console.error("Object is missing")
>
> }

Q3 Disabling right Click on WebPage

> document.addEventListener("contextmenu", function(e){        
>
> e.preventDefault();   
>
>  }, false);

Q4 The "use strict" explanation

​	1)Cannot use undeclared variables

​	2)Cannot Delete 

​	3)Use undeclared variables, read w3 

​			https://www.w3schools.com/js/js_strict.asp

​			https://www.w3schools.com/js/js_object_properties.asp

Q5 Delete keyword in JS

​	Can delete objects, but not elements of object as delete cannot delete allocated memory

Q6 JS Literals (What are Types of literals in JS)

> // Literal : is to represent anything fixed value
>
> // 1) Numeric literals 1,2,2.14
>
> // 2) String Literals "some text"
>
> // 3) Array Literals
>
> // 4) Object literals
>
> // 5) Boolean Literals
>
> // 6) Function Literals
>
> 1;
>
> 'some text';
>
> [];
>
> {};
>
> true; //(or) false
>
> function(){}

Q7How do we Check type of array literals

> var kk = [1,2,3,4];
>
> consle.log(typeof(kk.length)); //if there is a property of length, then it is an array and will return number

​						What is REPL - **read–eval–print loop** 

Q8 []+{}  returns '[object Object]' and leads to understand a phenomenon known as Type Coercions

Q9What is Definition VS Declaration? You don't need to worry about Data types

​	-declaration - telling the data type of variable (we do this for good practice and readability)

​	-Definition - let, var, const (telling compiler, this is a variable definition)

> let number; //Definition
>
> var num = 2; //definition + assigning
>
> const

Q10) Passing values by reference

> let x = {
>
> ​	p : 1
>
> ​	q: 2
>
> }; 
>
> console.log(x.p,x.q); //1,2
>
> let y = x;
>
> console.log(y.p,y,q); //1,2
>
> //We are pointing to obj x when referencing y aka NOT COPYING only REFERENCING

>  let a = {
>      p:1
>  };
>
>  let b=a; //Not copying
>  let c=b; //This is only referencing
>  let d=c;
>  let e=d;
>  let f=e;
>  let g=f;
>  g.p=3;
>  console.log(a.p);

10) Scope Quirks

Quirk 1 :

​	Let and const inside a function vs global variable

​		-let doesn't allow you to redefine a variable in a local scope to outer scope

​		-use let to protect scope

​		-hoisting

> // //A variable defined using let or const keywords inside a function cannot coexist
> // with global variable of the same name.
> //– let and const inside function vs. global variable
> let a = 'global a';
> let b = "global b";
> function x(){
>     console.log("x() : global b = "+ b); 
>     console.log("x() : global a = "+ a);  // Reference Error
>     let a = 1; // doesn't hoist
> }
> x();
>
> //The let keyword doesn’t hoist definitions, and we have a global variable a, so
> // logically, inside function x() variable a should be taken from global scope, before
> // it is defined later with let a = 1 but that’s not what happens.
> // If variable a already exists inside a function (and it’s defined using let or const
> // keywords) then using a, prior its definition within the function will produce Reference Error, even if //global variable a exists!

​	Quirk 2:

> //var latches onto window/this object, let and const do not
> //Following Code should be tried in Google Chrome Browser Console
> // In global scope this reference points to instance of window object / global context.
> //console.log(this === window); //window
>
> // When variables are defined using var keyword they become attached to window
> // object, but variables defined using let (and const) are not.
>
> var c = "c";    //latches onto window (this in global scope)
> let d = "d";    // exists seperately from 'this'
> console.log(c); 
> console.log(this.c);
> console.log(window.c);
>
> console.log(d);
> console.log(this.d);
> console.log(window.d);

11) Segments

Statements VS Expressions

​	-Statements are undefined

​			ex. ;

​			Also, empty objects are  statement. ex. {}; //returns undefined

​		Statements - assigning memory and no return value

​	-Expression - directly gives value

​			ex. 1;

Primitive Types)

> // JavaScript has 7 primitive types: null, undefined, number, bigint, string,
> // boolean and symbol. Primitives helps us work with simple values such as strings,
> // numbers and booleans. Let’s take a look at some of their possible values:
>
> typeof(null); //Returns object
> typeof(undefined); //undefined
>
> typeof(Number); //function
>
> typeof(-1); //number
> typeof(5); //number
> typeof(Infinity); //number
> typeof(NaN); //number
>
> let number = new Number(7);
> typeof(number); //object
> typeof(number.valueOf()); //number
>
> const limit = Number.MAX_SAFE_INTEGER;
> limit+1;
> limit+2;
> //try with var instead of const
>
>
> typeof 10;
> typeof 10n; 
>
> typeof "text";
> typeof 'newstring';
>
> let string = new String("FooBoo");
> typeof string;
> typeof(string.valueOf());
>
>
> //template Literals
> for(let alerts=0; alerts<4;alerts++){
>     let one = (alerts == 1);
>     let is = one ? "is" : "are";
>     let s = one == 1 ? "" : "s";
>     let message = `There ${is} ${alerts} alert${s}.`;
>     console.log(message);
> }
>
> //Symbols
> // The Symbol primitive provides a way to define a completely unique key.
> // Symbol doesn’t have a constructor and cannot be initialized using new keyword:
>
> let sym = new Symbol('sym'); //TypeError because Symbol has no constuctor
>
> let sym =  Symbol('sym'); //create a new symbol with a unique ID
>
> // The ID, however, is not the used-defined string "sym", it is created internally.
> // This is demonstrated in the following example.
> // At first it might be surprising that the following statement evaluates to false:
>
> Symbol("sym") === Symbol("sym"); //false
>
> // Whenever you call Symbol(’sym’) a unique symbol is created. The comparison
> // is made between two logically distinct IDs and therefore evaluates to false.
>
>
> // Symbols is a primitive type used to define private object properties. This is not the same
> // as regular (public) object properties. However, both public and private properties
> // created with symbols can live on the same object:
>
> let sym = Symbol("unique");
> let bol = Symbol("distrinct");
> let one = Symbol("only-one");
> let obj = {
>     property: "regular property",
> [sym]:1,
> [bol]:2
> };
>
> typeof 1000n; //bigint
>
> type of 1000; //number







