# useCounter

### Description

Use this hook when you need a **counter**. It uses "useState" react hook for the counter state.

You can get the current value, increment, decrement or reset it to the initial value which you also can define.

### Return object of the hook:

The hook returns an object { } of functions:

|   Return  |   Type   |             Description             |
|:---------:|:--------:|:-----------------------------------:|
|   state   |  number  |            Counter value            |
| increment | function |   Increments the counter by factor  |
| decrement | function |   Decrements the counter by factor  |
|   reset   | function | Resets the counter to initial state |

### Parameters of the hook:

|   Parameter  |  Type  | Default |      Description      |
|:------------:|:------:|:-------:|:---------------------:|
| initialState | number |    10   | Counter initial value |
|   incFactor  | number |    1    |    Increment factor   |
|   decFactor  | number |    1    |    Decrement factor   |


### Examples

Example of simple usage. In this case no initialValue is passed so by default is 10, destructure the state and the functions you need:

```javascript
const { state, increment } = useCounter();

console.log(state); // 10
increment();
console.log(state); // 11
```
---
Example usage of all functions. For increment or decrement you can also specify the factor:

```javascript
const { state, increment, decrement, reset } = useCounter(38);

console.log(state); // 38

increment(12);
console.log(state); // 50

decrement(10);
console.log(state); // 40

reset();
console.log(state); // 38
```