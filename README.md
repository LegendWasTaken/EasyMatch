# EasyMatch

EasyMatch is a node package made with the intent of making matching strings 1000x easier than it is with regex.
**Disclaimer:***If you do not know RegEx, you should***not***use this package as a replacement...*

## Examples
```js
const EasyMatch = require(`easymatch`);
let matcher = new EasyMatch(`[`, `]`);

let testString = "";
let pattern = "";
let matchResult;

testString = "Song: Coding by Mark";
pattern = "Song: [name] by [artist]"

matchResult = matcher.match(testString, pattern);

// Match will be look like this
{
    name: 'Coding',
    artist: 'Mark'
}

testString = "The current time in London is 23:29 with 38% chance of rain";
pattern = "The current time in [city] is [hour]:[minute] with [rainchance]% chance of rain";

matchResult = matcher.match(testString, pattern);
{
    city: 'London',
    hour: '23',
    minute: '29',
    rainchance: '38'
}
// In the case it can't match

testString = "This is some random text!";
pattern = "The current time is [time]";
matchResult = matcher.match(testString, pattern);
// it'll look like this
{
    time: null
}
```