# JavaScript Array Methods

---

## .every()

- If ALL of the elements evalute to true with the specified condition then it returns true.
- It's corollary is **.some()** which returns true if at least one element evaluates to true.

```
function allBiggerThan10(element, index, array) {
   return element > 10;
}

[12, 55, 18, 11, 40].some(allBiggerThan10);  // true
[12, 15, 8, 11, 40].some(allBiggerThan10);  // false
```

## .filter()

- Iterates through the array and looks for a true or false value.
  - If the value is true then the array element is kept.
- Returns a new array. The original array is left untouched.

```
const words = ["spray", "limit", "elite", "exuberant", "destruction", "present", "happy"];

let longWords = words.filter(word => word.length > 6);
```

## .forEach()

- A way to loop through things instead of using a for loop.

```
const items = ["item1", "item2", "item3"];
const copy = [];

items.forEach(function(item) {
   copy.push(item);
});
```

## .map()

- Doing something to every single element in an array.
- Returns a new array. The original array is left untouched.

```
var numbers = [1, 4, 9];
var roots = numbers.map(Math.sqrt);
// roots is now [1, 2, 3]
// numbers is sit [1, 4, 9]
```

## .reduce()

- You are building a brand new object, array or something.
- You can set an initial value as in the example below where the initial accumulator value is set to 0.
- The original array is left untouched.

```
[0, 1, 2, 3, 4, ].reduce(function(accumulator, currentValue, currentIndex, array) {
  return accumulator + currentValue;
}, 0);
```

## .some()

- If at least one of the elements evalute to true with the specified condition then it returns true.
- It's corollary is **.every()** which returns true if every element evaluates to true.

```
function isBiggerThan10(element, index, array) {
   return element > 10;
}

[2, 5, 8, 1, 4].some(isBiggerThan10);  // false
[12, 5, 8, 1, 4].some(isBiggerThan10);  // true
```
