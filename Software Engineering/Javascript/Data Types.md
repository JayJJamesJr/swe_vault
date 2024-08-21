Everything in Javascript is either an object or a primitive

```javascript
let firstName = 'Jonas'; // Primitive
let map = {
	name: firstName
}; // Object
```


1. `Number`: Floating point numbers -> Used for decimals and integers
2. `String`: Sequence of characters -> Used for text
3. `Boolean`: Logical type that can only be true of false -> Used to take decisions
4. `Undefined`: Value taken by a variable that is not yet defined (empty value)
5. `Null`: Also means 'empty value'
6. `Symbol (ES2015)` : Value that is unique and cannot be changed (Not useful for now)
7. `BigInt (ES2020)`: Larger integers than the Number type can hold

```
Javascript has dynamic typing: We do not have to manually define the data type of the value stored in a variable. Instead, data types are determined automatically.

In Javascript the value holds the type and not the variable.
```

## Comments

There are two kinds of comments in Javascript:
- Single line comment
	- Used to write comment that fits on a single line.
- Multi line comment
	- Used to write comments spanning multiple lines.



```javascript
// This is an example of a  single line comment in JavaScript
let num = 10;

/** This is an example
of a multi line comment in JS
**/

```

