# Part 3 - Javascript (Step 2 - Functional)

Once we have the pseudocode written down in the form of Events that trigger Action Steps, we can start writing these events and steps down in JavaScript using functions.

A function is just a way to store a sequence of steps. A function can also be 'called' to trigger that sequence of steps.

The basic syntax for a function is,

```
function hello() {
  console.log("Hello");
}

hello();
```

In the above example, the function 'hello' has one step 'console.log("Hello");'. This console.log itself is another function and it is one of the in-built functions provided by a web browser. When we call the function using 'hello();', it prints a message to our browser console.

Each step in the program is called a statement.

The above 'console.log("Hello")' and 'hello();' statements are 'function call statements'. Function call statements trigger the execution of a function.

Functions can also take arguments as input, and use the argument in their statements. For example,

```
function hello(text) {
  console.log(text);
}

hello("World");
```

The above code will print "World" in the browser console.

Arguments can be any of the types supported by JavaScript. The most common primitive types in JavaScript are,

- Boolean (true or false)
```
console.log(true);
```
- Number (0, 0.1, 1000, -10.5, etc.)
```
console.log(-10.5);
```
- String ("Hello", 'world')
```
console.log("Hello" + 'world');
```
- Undefined (undefined -> default value for an uninitialized variable or object property)
```
console.log(undefined);
```
- Null (null -> initialized but empty variable)
```
console.log(null);
```

The non-primitive types are,
- Objects
```
console.log({
  "age": 20,
  "name": "Dev",
  "school": {
    "name": "Kendriya Vidyalaya",
    "location": "Bengaluru",
  }
);
```
- Arrays
```
console.log([1, 2, 3, "hello", true, undefined, {"age": 20}, null]);
```

Functions can even take other functions as arguments. For example,

```
function print(f, x) {
  console.log(f(x));
}

function add_one(a) {
  return a + 1;
}

print(add_one, 100);
```

You can write a comment in your code and that line will be ignored like this,

```
console.log("Hello");
// This is a comment and will be ignored
```

You can declare a variable to hold any data type in one of the following ways,
- let (when the variable will be reassigned)
```
let x = 100;
x = 50;
console.log(x);
```
- const (when the variable will never be re-assigned)
```
const X = 100;
console.log(X);
```

Variables can be global (shared across all functions in the file) or local (only accessible within that function's scope). For example,

```
let x = 100;
function update() {
  let y = 50;
  x = y;
}

console.log(x);
update();
console.log(x);
```

## Workshop steps

1. Write each event from the pseudocode as a high-level function with each action step as a separate function call
2. Write a function stub (empty function) for each action event with a little comment explaining what needs to be done in the stub
3. Identify the data that needs to flow into each function and pass it as arguments
4. Create global variables for any data that needs to be shared across functions

For example, "When a question loads" event can become:

```
let correct_answer = ""; // global variable to store the current correct answer

function on_question_load(question, answer_options, answer) {
    update_question_text(question);
    update_answer_buttons_text(answer_options);
    store_correct_answer(answer);
    fetch_clue_image_gif(answer);
}

function update_question_text(question) {
    // TBD update the text of the question
}

function update_answer_buttons_text(answer_options) {
    // TBD update the text of the 4 answer buttons
}

function store_correct_answer(answer) {
    // TBD update correct_answer with answer
}

function fetch_clue_image_gif(answer) {
    // TBD fetch clue image gif from Tenor API (after replacing the QUERY) then call on_clue_image_gif_load(gif_url)
}
```

## Next steps

There can be many different ways to design the high-level functions in a programming language. I have taken an approach which works for me as I can reason well about it. Yours may be different. There is no right or wrong answer as long as the app eventually works and we can explain it to someone else easily.

In the next part of the workshop, we will implement all of the function stubs and get our game to work. Switch to the branch **workshop/part3-javascript-step3-implementation** to continue.
