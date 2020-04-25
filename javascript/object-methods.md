# JavaScript Object Methods

---

## .entries()

- Returns arrays of the object's key value pairs.

```
const obj = { 'foo': 'bar', 'baz': 42 };
console.log(Object.entries(obj));   // console: [['foo', 'bar', ['bar', 42]]
```

## .keys()

- Returns an array of the object keys.

```
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.keys(obj));   // console: ['0', '1', '2']
```

## .values()

- Returns an array of the object values.

```
var obj = { 'foo': 'bar', 'baz': 42 };
console.log(Object.values(obj));   // console: ['bar', 42]
```
