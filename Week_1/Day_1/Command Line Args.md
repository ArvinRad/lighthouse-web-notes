## Tips:
Passing Command Line Arguments in Node.js using Using [process.argv](https://stackabuse.com/command-line-arguments-in-node-js/)

The first element will always be a path, the second is the name of the JavaScript file, the third and after are arguments passed by the user.
```javascript
> node processargv.js tom jack 43
```
We can parse arguments from the process.argv array and transform it in to an easier-to-use associative array using minimist module.:
```javascript
> const args = require('minimist')(process.argv.slice(2));
```
use the alias in addition to the regular option name:
```javascript
const minimist = require('minimist');

let args = minimist(process.argv.slice(2), {
    alias: {
        h: 'help',
        v: 'version'
    }
});
```
Or if no value is passed for an option then set a default in your program to be used automatically:
```javascript
const minimist = require('minimist');

let args = minimist(process.argv.slice(2), {
    default: {
        port: 8080
    },
});
```


