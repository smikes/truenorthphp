# ECMAScript 6: What's in it for me?

I'm here today to talk about a language that's almost as old
as the web itself is.  

## ECMAScript 4

### The "Harmony" Effort

## New features in ES6 flat-out stolen from PHP

### Generators/yield

### String Interpolation

## New features that make Javascript hard to read

### Arrow functions

```
() => 1
```

or 

```
x = (a, b) => a+b
x(1, 3)
```

This is just a shorthand for

```
function (...) { return ...; }

```

When an arrow function is being parsed, only the **first** statement after the arrow goes inside the function body.  So here's a fun one:

```
x = (a, b) => a *= 2; a+b;

--> ReferenceError: a is not defined
```

Now you might think that you can fix this with a block, and you kind of can:
```
x = (a, b) => {a *= 2; a+b;}

now no ReferenceError

x(1, 3)
--> undefined
```

What happened?  By including the block `{` and `}`, we disabled the "automatic return".  So the function we probably wanted was 


```
x = (a, b) => {a *= 2; reference a+b;}

x(1, 3)
--> 5
```

Finally!
