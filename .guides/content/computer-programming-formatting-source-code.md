In Java source code, some spaces are required. For example, you need at least one space between words, so this program is not legal:

```code
publicclassGoodbye{

    publicstaticvoidmain(String[] args) {
        System.out.print("Goodbye, ");
        System.out.println("cruel world");
    }
}
```

But most other spaces are optional. For example, this program *is* legal:



The newlines are optional, too. So we could just write this:



It still works, but the program is getting harder and harder to read. Newlines and spaces are important for visually organizing your program, making it easier to understand the program and find errors when they occur.

Many editors will automatically format source code with consistent indenting and line breaks. For example, in DrJava (see Appendix 18.1) you can indent your code by selecting all text (**Ctrl+A**) and pressing the **Tab** key.






Organizations that do a lot of software development usually have strict guidelines on how to format source code. For example, Google publishes its Java coding standards for use in open source projects: [https://google.github.io/styleguide/javaguide.html](https://google.github.io/styleguide/javaguide.html).

You probably won't understand these guidelines now, because they refer to language features you haven't yet seen. But you might want to refer to them periodically as you read this book.