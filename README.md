# inquiry-traverser

[![npm version](https://badge.fury.io/js/inquiry-traverser.svg)](https://badge.fury.io/js/inquiry-traverser)

A Promise based wrapper for prompting branched questions with [Inquirer.js](https://github.com/sboudrias/Inquirer.js).

## Documentation

### Installation

```
$ npm install inquiry-traverser
```

```JavaScript
var inquirer = require('inquirer');
var traverser = require('inquiry-traverser');

var traverse = traverser(inquirer);

traverse({ /* Put your branched questions object here */ })
  .then(function onResolve (value) {
    // Handle a successfull resolution ...
  })
  .catch(function onReject (reason) {
    // Handle a rejection ...
  });
```

### Examples

Check the `examples` folder, run the scripts, e.g.

```
$ node examples/basic-usage.js
```

### Differences to default Inquirer.js Behaviour

Contrary to the default behaviour of Inquirer.js, which calls the prompts' callback with an [Answer object](https://github.com/sboudrias/Inquirer.js#answers) that contains the user's response to _all prompted questions_, the function called upon resolving the Promise returned by `inquiry-traverser` receives a particular value (see the [basic usage](https://github.com/ta2edchimp/inquiry-traverser/blob/master/examples/basic-usage.js) example).

## Todos

Currently `inquiry-traverser` lacks a proper documentation and tests. At the moment, even only prompts of type `confirm` are tested.  
This will change and be more complete soon, hopefully. Until then, feel free to [file bug reports or make suggestions](https://github.com/ta2edchimp/inquiry-traverser/issues). Pull requests welcome :)
