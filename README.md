# The if Statement

## Learning Goals

- Use the `if` statement

## The `if` statement in Java

All the code examples we have used so far have been "unconditional", meaning
that when we've instructed the computer to do something, it's been in the form
of "always do this thing". Even when we've provided multiple statements, they've
been in the form of "always do this first thing, then always do this second
thing".

It's not hard to imagine that we might want conditional behavior sometimes. For
example, I could have different greetings for people of different ages in my
"Hello, World" program:

```java
int birthYear = 2000;
int currentYear = 2020;
int age = currentYear - birthYear;
if (age > 18) {
    System.out.println("Look at you, all grown up");
}
if (age < 18) {
    System.out.println("Hi kiddo!");
}
```

You now understand what happens up to line 3 - we end up with a variable of name
`age`, which has a value of `20` stored in it. Let's break down the statement on
line 4:

```java
if (age > 18) {
```

The `if` statement allows us to specify a "condition". In Java, an `if`
statement is immediately followed by an open parenthesis `(`, what we call a
"condition clause" and a close parenthesis `)`. The condition clause is any
expression that can evaluate to either "true" or "false".

In this case, either the `age` is greater than 18 or it's not. If it's greater
than 18, then the program will execute the content of the `if` block. If the age
is not greater than 18, then the program will not execute the content of the
`if` block.

Like a Java class, an `if` statement can contain multiple statements inside it.
Therefore, an `if` statement can be followed by an open curly brace `{` if it is
meant to indicate the conditional execution of more than one statement. As
always, the open curly brace `{` must then be matched with a close curly brace
`}`:

```java
if (age > 18) {
    // as many conditional statements here
    // as I need for my program
}
```

Note that if you only have one conditional statement, you can omit the matching
curly braces:

```java
if (age > 18)
    System.out.println("Look at you, all grown up");
```

I do not recommend this notation, as it makes it very easy to accidentally
expand or reduce the scope of an `if` statement.

An `if` statement can be followed by, but does not have to, an `else` statement.
When an `else` follows an `if`, its content will be executed whenever the
conditional clause of the `if` is not true:

```java
if (true) {
    System.out.println("display this message when true");
} else {
    System.out.println("display this message when false");
}
```

Since `if` statements can contain multiple statements inside their `if` block,
they can also contain other `if` statements:

```java
if (age < 18) {
    System.out.println("Hello kiddos");
    if (age < 10) {
        System.out.println("Impressively young to be learning this!");
        System.out.println("Good to see you here!");
    } else {
        System.out.println("Good to see you here!");
    }
}
```

In the example above, we want to further customize the greeting message for
users younger than 18, so we check if they're also younger than 10, and display
a special message if that's the case. If not, we simply welcome them without a
special message.
