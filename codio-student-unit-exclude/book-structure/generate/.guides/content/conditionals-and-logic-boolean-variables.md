To store a `true` or `false` value, you need a `boolean` variable. You can declare and assign them like other variables. In this example, the first line is a variable declaration, the second is an assignment, and the third is both:

```code
boolean flag;
flag = true;
boolean testResult = false;
```


Since relational and logical operators evaluate to a `boolean` value, you can store the result of a comparison in a variable:

```code
boolean evenFlag = (x % 2 == 0);    // true if x is even
boolean positiveFlag = (x > 0);     // true if x is positive
```


The parentheses are unnecessary, but they make the code easier to understand. A variable defined in this way is called a **flag**, because it signals, or “flags”, the presence or absence of a condition.

You can use flag variables as part of a conditional statement:

```code
if (evenFlag) {
    System.out.println("n was even when I checked it");
}
```

Flags may not seem that useful at this point, but they will help simplify complex conditions later. Each part of a condition can be stored in a separate flag, and these flags can be combined with logical operators.

Notice that we didn't have to write  `if (evenFlag == true)`. Since `evenFlag` is a `boolean`, it's already a condition. To check if a flag is `false`, we simply negate the flag:

```code
if (!evenFlag) {
    System.out.println("n was odd when I checked it");
}
```

In general, you should never compare anything to `true` or `false`. Doing so makes the code more verbose and awkward to read out loud.