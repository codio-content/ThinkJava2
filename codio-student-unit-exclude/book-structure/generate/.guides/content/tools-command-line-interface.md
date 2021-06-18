One of the most powerful and useful skills you can learn is how to use the **command-line interface**, also called the “terminal”. The command line is a direct interface to the operating system. It allows you to run programs, manage files and directories, and monitor system resources. Many advanced tools, both for software development and general-purpose computing, are available only at the command line.


Many good tutorials are available online for learning the command line for your operating system; just search the web for “command line tutorial”. On Unix systems like Linux and macOS, you can get started with just four commands: change the working directory (`cd`), list directory contents (`ls`), compile Java programs (`javac`), and run Java programs (`java`).

Figure 18.3 shows an example in which the *Hello.java* source file is stored in the *Desktop* directory. After changing to that location and listing the files, we use the `javac` command to compile *Hello.java*. Running `ls` again, we see that the compiler generated a new file, *Hello.class*, which contains the byte code. We run the program by using the `java` command, which displays the output on the following line.

![Figure 18.3 Compiling and running *Hello.java* from the command line.](figs/terminal.png)

**Figure 18.3 Compiling and running *Hello.java* from the command line.**

Note that the `javac` command requires a *filename* (or multiple source files separated by spaces), whereas the `java` command requires a single *class name*. If you use DrJava, it runs these commands for you behind the scenes and displays the output in the Interactions pane.

Taking time to learn this efficient and elegant way of interacting with the operating system will make you more productive. People who don't use the command line don't know what they're missing.