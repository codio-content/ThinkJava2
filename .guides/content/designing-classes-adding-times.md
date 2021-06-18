Suppose you are going to a movie that starts at 18:50 (that is, 6:50 PM), and the running time is 2 hours, 16 minutes. What time does the movie end? We'll use `Time` objects to figure it out:

```code
Time startTime = new Time(18, 50, 0.0);
Time runningTime = new Time(2, 16, 0.0);
```


Here are two ways we could “add” the `Time` objects:



* Write a static method that takes two `Time` objects as parameters.
* Write an instance method that gets invoked on one object and takes the other as a parameter.



To demonstrate the difference, we'll do both. Here is the static method:


```code
public static Time add(Time t1, Time t2) {
    Time sum = new Time();
    sum.hour = t1.hour + t2.hour;
    sum.minute = t1.minute + t2.minute;
    sum.second = t1.second + t2.second;
    return sum;
}
```

And here's how we would invoke it:

```code
Time endTime = Time.add(startTime, runningTime);
```

Here's what it looks like as an instance method:


```code
public Time add(Time t2) {
    Time sum = new Time();
    sum.hour = this.hour + t2.hour;
    sum.minute = this.minute + t2.minute;
    sum.second = this.second + t2.second;
    return sum;
}
```

And here's how we would invoke it:

```code
Time endTime = startTime.add(runningTime);
```

Notice the differences:



* The static method has the keyword `static`; the instance method does not.
* The static method has two parameters, `t1` and `t2`. The instance method has one explicit parameter, `t2`, and the implicit parameter, `this`.
* We invoked the static method with the `Time` class; we invoked the instance method with the `startTime` object.




That's all there is to it. Static methods and instance methods do the same thing, and you can convert from one to the other with just a few changes.


However, there's a problem with both of these methods; they are not correct. The result from either method is `20:66`, which is not a valid time.

If `second` exceeds 59, we have to carry into the minutes column, and if `minute` exceeds 59, we have to carry into `hour`.

Here is a better version of the instance method, `add`:

```code
public Time add(Time t2) {
    Time sum = new Time();
    sum.hour = this.hour + t2.hour;
    sum.minute = this.minute + t2.minute;
    sum.second = this.second + t2.second;

    if (sum.second >= 60.0) {
        sum.second -= 60.0;
        sum.minute += 1;
    }
    if (sum.minute >= 60) {
        sum.minute -= 60;
        sum.hour += 1;
    }
    if (sum.hour >= 24) {
        sum.hour -= 24;
    }
    return sum;
}
```

If `hour` exceeds 23, we subtract 24 hours, but there's no `days` attribute to carry into.