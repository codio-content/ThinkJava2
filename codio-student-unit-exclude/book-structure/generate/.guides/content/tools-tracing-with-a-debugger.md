A great way to visualize the flow of execution, including how parameters and arguments work, is to use a **debugger**. Most debuggers make it possible to do the following:




* Set a **breakpoint**, a line where you want the program to pause.
* Step through the code one line at a time and watch what it does.
* Check the values of variables and see when and how they change.



For example, open any program in DrJava and move the cursor to the first line of `main`. Press **Ctrl+B** to toggle a breakpoint on the current line; it should now be highlighted in red. Press **Ctrl+Shift+D** to turn on “Debug Mode”; a new pane should appear at the bottom of the window. These commands are also available from the **Debugger** menu, in case you forget the shortcut keys.


When you run the program, execution pauses at the first breakpoint. The debugging pane displays the **call stack**, with the current method on top of the stack, as shown in Figure 18.5. You might be surprised to see how many methods were called before the `main` method!

![Figure 18.5 The DrJava debugger. Execution is currently paused on the first line of `printTwice`. There is a breakpoint on the first line of `main`.](figs/debugger.png)

**Figure 18.5 The DrJava debugger. Execution is currently paused on the first line of `printTwice`. There is a breakpoint on the first line of `main`.**



To the right are several buttons that allow you to step through the code at your own pace. You can also click **Automatic Trace** to watch DrJava run your code one line at a time.

Using a debugger is like having the computer proofread your code out loud. When the program is paused, you can examine (or even change) the value of any variable by using the Interactions pane.

Tracing allows you to follow the flow of execution and see how data passes from one method to another. You might expect the code do one thing, but then the debugger shows it doing something else. At that moment, you gain insight about what may be wrong with the code.

You can edit your code while debugging it, but we don't recommend it. If you add or delete multiple lines of code while the program is paused, the results can be confusing.

See [http://drjava.org/docs/user/ch09.html](http://drjava.org/docs/user/ch09.html) for more information about using the debugger feature of DrJava.