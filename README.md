# Ansistyles

Functions that surround a string with ansistyle codes so it prints in style.

In case you need colors, like `red`, have a look at [ansicolors](https://github.com/ngot/ansistyles).

## Usage

```js
var styles = require('ansistyles');

console.log(styles.bright('hello world'));    // prints hello world in 'bright' white
console.log(styles.underline('hello world')); // prints hello world underlined
console.log(styles.inverse('hello world'));   // prints hello world black on white
```

## Combining with ansicolors

```js
var styles = require('ansistyles')
  , colors = require('ansicolors');

  console.log(
    // prints hello world underlined in blue on a green background
    colors.bgGreen(colors.blue(styles.underline('hello world'))) 
  );
```

## Tests

Look at the [tests](https://github.com/ngot/ansistyles/blob/master/test/ansistyles.js) to see more examples and/or run them via: 

    js test/ansistyles.js

## More Styles

As you can see from [here](https://github.com/ngot/ansistyles/blob/master/ansistyles.js#L4-L15), more styles are available,
but didn't have any effect on the terminals that I tested on Mac Lion and Ubuntu Linux.

I included them for completeness, but didn't show them in the examples because they seem to have no effect.

### reset

A style reset function is also included, please note however that this is not nestable.

Therefore the below only underlines `hell` only, but not `world`.

```js
console.log(styles.underline('hell' + styles.reset('o') + ' world'));
```

It is essentially the same as:

```js
console.log(styles.underline('hell') + styles.reset('') + 'o world');
```
