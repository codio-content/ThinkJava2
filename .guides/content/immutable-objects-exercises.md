The code for this chapter is in the *ch09* directory of *ThinkJavaCode2*. See page in section Using the Code Examples for instructions on how to download the repository. Before you start the exercises, we recommend that you compile and run the examples.


**Exercise 9.1:**
The point of this exercise is to explore Java types and fill in some of the details that aren't covered in the chapter.




1. Create a new program named *Test.java* and write a `main` method that contains expressions that combine various types using the `+` operator. For example, what happens when you “add” a `String` and a `char`? Does it perform character addition or string concatenation? What is the type of the result?
1. Make a bigger copy of the following table and fill it in. At the intersection of each pair of types, you should indicate whether it is legal to use the `+` operator with these types, the operation that is performed (addition or concatenation), and the type of the result. <center>
||boolean|char|int|double|String|
|-|-|-|-|-|-|
|boolean||||||
|char||||||
|int||||||
|double||||||
|String||||||

</center>
1. Think about some of the choices the designers of Java made, based on this table. How many of the entries seem unavoidable, as if there was no other choice? How many seem like arbitrary choices from several equally reasonable possibilities? Which entries seem most problematic?
1. Here's a puzzler: normally, the statement `x++` is exactly equivalent to `x = x + 1`. But if `x` is a `char`, it's not exactly the same! In that case, `x++` is legal, but `x = x + 1` causes an error. Try it out. See what the error message is, and then see if you can figure out what is going on.
1. What happens when you add `""` (the empty string) to the other types; for example, `"" + 5`?




**Exercise 9.2:**
You might be sick of the `factorial` method by now, but we're going to do one more version.



1. Create a new program called *Big.java* and write an iterative version of `factorial` (using a `for` loop).
1. Display a table of the integers from 0 to 30 along with their factorials. At some point around 15, you will probably see that the answers are not correct anymore. Why not?
1. Convert `factorial` so that it performs its calculation using BigIntegers and returns a `BigInteger` as a result. You can leave the parameter alone; it will still be an integer.
1. Try displaying the table again with your modified factorial method. Is it correct up to 30? How high can you make it go?




**Exercise 9.3:**
Many encryption algorithms depend on the ability to raise large integers to a power. Here is a method that implements an efficient algorithm for integer exponentiation:

```code
public static int pow(int x, int n) {
    if (n == 0) return 1;

    // find x to the n/2 recursively
    int t = pow(x, n / 2);

    // if n is even, the result is t squared
    // if n is odd, the result is t squared times x
    if (n % 2 == 0) {
        return t * t;
    } else {
        return t * t * x;
    }
}
```

The problem with this method is that it works only if the result is small enough to be represented by an `int`. Rewrite it so that the result is a `BigInteger`. The parameters should still be integers, though.

You should use the `BigInteger` methods `add` and `multiply`. But don't use `BigInteger.pow`; that would spoil the fun.


**Exercise 9.4:**
One way to calculate $e^x$ is to use the following infinite series expansion. The $i$th term in the series is $x^i / i!$. $ e^x = 1 + x + x^2 / 2! + x^3 / 3! + x^4 / 4! + ... $


1. Write a method called `myexp` that takes `x` and `n` as parameters and estimates $e^x$ by adding the first `n` terms of this series. You can use the `factorial` method from Section 8.3 or your iterative version from the previous exercise.
1. You can make this method more efficient by observing that the numerator of each term is the same as its predecessor multiplied by `x`, and the denominator is the same as its predecessor multiplied by `i`. Use this observation to eliminate the use of `Math.pow` and `factorial`, and check that you get the same result.
1. Write a method called `check` that takes a parameter, `x`, and displays `x`, `myexp(x)`, and `Math.exp(x)`. The output should look like this: ```code
1.0     2.708333333333333     2.718281828459045
``` Use the escape sequence `'\t'` to display a tab character between each of the values.
1. Vary the number of terms in the series (the second argument that `check` sends to `myexp`) and see the effect on the accuracy of the result. Adjust this value until the estimated value agrees with the correct answer when `x` is 1.
1. Write a loop in `main` that invokes `check` with the values 0.1, 1.0, 10.0, and 100.0. How does the accuracy of the result vary as `x` varies? Compare the number of digits of agreement rather than the difference between the actual and estimated values.
1. Add a loop in `main` that checks `myexp` with the values -0.1, -1.0, -10.0, and -100.0. Comment on the accuracy.




**Exercise 9.5:**
The goal of this exercise is to practice encapsulation and generalization using some of the examples in previous chapters.



1. Starting with the code in Section 7.5, write a method called `powArray` that takes a `double` array, `a`, and returns a new array that contains the elements of `a` squared. Generalize it to take a second argument and raise the elements of `a` to the given power.
1. Starting with the code in Section 7.8, write a method called `histogram` that takes an `int` array of scores from 0 to (but not including) 100, and returns a histogram of 100 counters. Generalize it to take the number of counters as an argument.




**Exercise 9.6:**
The following code fragment traverses a string and checks whether it has the same number of opening and closing parentheses:

```code
String s = "((3 + 7) * 2)";
int count = 0;

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);
    if (c == '(') {
        count++;
    } else if (c == ')') {
        count--;
    }
}

System.out.println(count);
```



1. Encapsulate this fragment in a method that takes a string argument and returns the final value of `count`.
1. Test your method with multiple strings, including some that are balanced and some that are not.
1. Generalize the code so that it works on any string. What could you do to generalize it more?