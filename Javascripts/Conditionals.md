
**double equality operator and triple equality operator** 


**== : equality**

**=== : strict equality**



==  => **checks for the equality of the value but doesn't checks for the type** 
			**converts both value into same type** 

```
let numberSeven = 7
let stringSeven = "7"

if( numberSeven == stringSeven ){
	console.log(true)
}
else {
	console.log(false)
}
// true 
why ? 
because while using the == what it does is coerces the value into the same type of the value so it became true because 7 and "7" type became the same type.
```


=== => **checks for the equality of the value and the type of the value which says                 as the name of the operator strict equality.** 

```
let numberOne = 1
let stringOne = "1"

if (numberOne === stringOne ){
	console.log(true)
}
else {
	console.log(false)
}
// false
why is that ? 
because while using the === what it does it strictly checks the type of the value and the value which means like before in the == what it did was making the type of the value to same but in this operator it doesn't changes or coerces that's why it gives the output false 
```

**ALWAYS USE THE === RATHER THAN ==  BECAUSE IT IS MUCH MORE PREFERRED**


# Switch Statement

```
const birthday = 2;

switch (birthday) {

case 1: 

console.log("not the valid date");

break;

case 2:

console.log("not the valid date");

break;

case 3:

console.log("yay happy birthday!!");

break;

default:

console.log("you are not eligible for this");

break;

}
```

This is same like the if else statement but syntax only has changed what happens here is birthday is 2 it will check the cases and the case 1 is not equal so not executed checks case 2 which is equal so it get executed, if there is none of the case matching it will execute the default log.
