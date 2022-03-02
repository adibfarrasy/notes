## What are JavaScript generators?

Signature:

1. there's a \* after function, i.e. function\*
2. the function has yields, a special return keyword

Generators have properties `value` and `done`. When the function is called with the next method, it will return the first yield value, then when next is applied again it will return the next yield value, all the way until there's no more yield and the property `done` will be `true`.

### Example

function\* simpleGenerator() {
yield 1
yield 2
yield 3
}

const generateObject = simpleGenerator()
console.log(generatorObject.next()) // {value: 1, done: false}
console.log(generatorObject.next()) // {value: 2, done: false}
console.log(generatorObject.next()) // {value: 3, done: false}
console.log(generatorObject.next()) // {value: undefined, done: true}

### Useful example

function\* generateId(){
let id = 1

    while(true) {
        yield id
        id++
    }

}
