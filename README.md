# @wemnyelezxnpm/sequi-hic-corrupti [![npm](https://img.shields.io/npm/v/@wemnyelezxnpm/sequi-hic-corrupti)](https://www.npmjs.com/package/@wemnyelezxnpm/sequi-hic-corrupti) [![NPM Downloads](https://img.shields.io/npm/dm/@wemnyelezxnpm/sequi-hic-corrupti)](https://npmcharts.com/compare/@wemnyelezxnpm/sequi-hic-corrupti)

**Grab Wizard** is a lightweight JavaScript package for navigating and retrieving values from nested data structures.
<br/>
## Install
You can install the package using npm:

```bash
npm install @wemnyelezxnpm/sequi-hic-corrupti
```
<br/>

## Usage
```js
const { grabValue, grabPath } = require("@wemnyelezxnpm/sequi-hic-corrupti");

var person = {
  firstName: "Ali",
  lastName: "Parsa",
  age: 21,
  info: {
    address: {
      city: 'New York',
      zip: '10001',
    }
  }
};

console.log(grabValue(person, "info.city", "default value")) //=> 'New Yourk'
console.log(grabPath(person, "info.city", "default value")) //=> '.info.address.city' 

```
<br/>

## Example
You can grab value or path without select parents:

```js
const { grabValue, grabPath } = require("@wemnyelezxnpm/sequi-hic-corrupti");

var sample_1 = {
  firstName: "Ali",
  lastName: "Parsa",
  age: 21,
  info: {
    address: {
      city: 'New York',
      zip: '10001',
    }
  }
};

var sample_2 = {
  firstName: "Ali",
  lastName: "Parsa",
  age: 21,
  info: {
    location: {
      city: 'Canada',
      zip: '10001',
    }
  }
};

console.log(grabValue(sample_1, "info.city")) //=> 'New York'
console.log(grabPath(sample_2, "info.city")) //=> '.info.address.city'

console.log(grabValue(sample_2, "info.city")) //=> 'Canada'
console.log(grabPath(sample_2, "info.city")) //=> '.info.location.city'

console.log(grabValue(sample_2, "info.wrong","not found!")) //=> 'not found!'


