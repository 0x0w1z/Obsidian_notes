
Array => Ordered collections of values 
Array => arrays are reference type

```
This is how array are made

let favoriteAnime = ["grand blue dreaming", "naruto", "Your name"]

```

```
Way to modify the array 

let userNames = ["Kirito", "Asuna", "Hinata", "Pikachu"]

userNames[0] = "Not Kirito"

// ["Not kirito", "Asuna", "Hinata", "Pikachu"]

What happens is the indices of the kirito is = 0 so if we wanna change the userName from kirito to not kirito we selects the indices of that value in the array and change.

The way to add other values in the array, suppose the new user has been signed up in the website so we have to add the user into the data so this is how it's done.

userName[userName.length] = "Miyamura";
So, what it does is it add the Miyamura into the end of the array.
```


# Array Methods

Methods in arrays

1. Push() : add to the end
2. Pop() : remove from end 
3. shift() : remove from start
4. unshift() : remove from end

## Push() Method

```
let newUserNames = [
"Sarams Rauniyar",
"0x0w1z",
"KiritoSir",
]
newUserNames.push("0w1z")
console.log(newUserNames)
// ["Sarams Rauniyar","0x0w1z","kirito","0w1z"]
// so what Push function does is it adds the value which is given in the     function to the array

```

## Pop

```
let topSongs = ["Never gonna give up", "Shape of you ", "Last one standing"];

topSongs.pop();

console.log(topSongs);
// [ 'Never gonna give up', 'Shape of you ' ]
// What pop does it it removes the ending value of the array
```


## Unshift ()

```
let dishesToDo = ["Big Plate", "Noodles Bowl", "Coffee Glass"];

dishesToDo.unshift("Fork");

console.log(dishesToDo);
// [ 'Fork', 'Big Plate', 'Noodles Bowl', 'Coffee Glass' ]
// What happen here is the "Fork" got added in beginning where as push add to the end 
```

## Shift()

```
let clothesToClean = ["Pant", "Shirt", "Coat"];

clothesToClean.shift();

console.log(clothesToClean)

// [ 'Shirt', 'Coat' ]
// Same as the Pop() function shift removes the value but what it does is it removes the value which is in beginning
```


## Concat ()

```
let alphabets = ["a", "b", "c"];

let remaingAlphbets = ["d", "e"];

let completeAlphebets = alphabets.concat(remaingAlphbets);

console.log(completeAlphebets);

// [ 'a', 'b', 'c', 'd', 'e' ]
// what concat does is it concat the 2 or more than 2 arrays, well what does not happens is that it doesnot mutate nor the array but it concat the arrays and store it into new variable 
```

## Includes 

```
let ingredients = ["fish", "Shrimp", "rice", "meat"];

let searchFish = ingredients.includes("fish");

console.log(searchFish); // True : there is "Fish" in the array

let searchChicken = ingredients.includes("chicken");

console.log(searchChicken); // False : no "chicken" in array
// what includes does is it gives the boolean values as the output if there is the value is in the array matches the value which is being searched by the includes.
```

### Program using includes
```
let Menu = ["cabbage", "cauliflower", "peas"];

if (Menu.includes("cabbage")) { // true

console.log("I will take this menu because im vegan");

}

if (Menu.includes("fish")) { // false

console.log("I will not take this menu because im vegan");

}
// I will take this menu because im vegan 
// if i add the fish in the array it will give the another ouput
```

## Reverse ()

```
let arrReverse = ["a", "b", "c"];

arrReverse.reverse();

console.log(arrReverse);

// As the name says what is does is the reverse the array 
// [ 'c', 'b', 'a' ]
```


## Join()

```
let elements = [
"Fire",
"Water",
"Earth",
]

let  joinedElements = elements.join("")
console.log(joinedElements)

// FireWaterEarth
// what is does is it joins the value which is inside of the array and makes is one. If we add something between the string like join("-") it will add those between the value and joins them into one. so, after doing that the output would be like this. // Fire-Water-Earth
// After using the join method what it does is it concatinate the value into one so for example there is an array which looks like this [100, "hello", true] what the output comes is the javascript concatinates the value of the array into one so, the output would be "100hellotrue" everything becomes the string because of the concatination of the javascript.
```


## Slice()

```
let animals = ["whale", "salmon", "bear", "lion"];

let waterType = animals.slice(0, 2);

console.log(waterType);

let groundType = animals.slice(2, 4);

console.log(groundType);

let whaleSalmonBear = animals.slice(0, 3);

console.log(whaleSalmonBear);

// what is does it extract the value from the array and store it into the new array.
// ['whale','salmon','bear']
```


## Const In Array

```
// Using Const in array is the way to make the array constant and not being able to change because when we make the array using the let keyword what it let us do it to change the array value.

// Let array and ouput

let drinkStorage = ["Coke"];

drinkStorage = ["Fanta"];

console.log(drinkStorage);

// ["Fanta"] // because the array is getting changed from the coke into the fanta beacuse of the let keyword.


// array using const and output

const foodStorage = ["Milk"];

foodStorage.push("Egg");

foodStorage = ["Egg", "Milk"]

console.log(foodStorage);
// error because the const doesn't let us change the array like in the let keyword because of the reference type although, we can add or remove the element inside the array like using pop() or push() but we  cannot do array = ["some value"] it will give us the error.
```


## Nested Array 
```
const typeOfPokemons = [

["Onix", "Geodude"],

["charmander", "charizard"],

];

console.log(typeOfPokemons[0][1]);

// geodude
// what happens here the way to access the geodude in the nested array is nested the array index typeOfPokemon[0][1] what it means the 0 is the first array which have onix and the geodude and the 1 means in there 0 index array log the array of which index is 1 which will give the output of geodude
// to access the nested array we need to chain the index of the values
```

