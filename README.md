# The if Statement

## Learning Goals

- Learn about conditionals
- Learn how to use the `if` statement

## The `if` statement in Java

In Java, code will run sequentially unless specified otherwise. We have seen
in the Execution Path lesson how code can jump around when methods are called.
But even then, all our code so far would still be considered "unconditional".
This means that the code is written in a sequential manner without any logic
applied. Wouldn't it be great if we could say "If this is true... do this thing
first"? Well turns out, we can! Statements and logic like that are called
**conditionals** where we interrupt the flow of the program with some logic.

Let's go back to our `Student` class. Say we want to send a message to a student
if they got a certain grade on a recent test:

```java
public class Student {
    private String firstName;
    private String lastName;
    private String major;

    /**
     * Take in a student numeric grade and provide feedback
     * on how they did on a test
     * @param grade : int - numeric grade the student received
     *                on the test
     */
    public void calculateGrade(int grade) {
        if (grade >= 70) {
            System.out.println("Congrats! You passed!");
        }
    }
}
```

Let's break down the statement on the first line in the calculateGrade()
method:

```java
if (grade >= 70) {
```

The `if` statement allows us to specify a "condition". In Java, an `if`
statement is immediately followed by an open parenthesis `(`, what we call a
"conditional clause" and a close parenthesis `)`. The **conditional clause** is
any expression that can evaluate to either "true" or "false".

In this case, either the `grade` is greater than or equal to 70, or it's not.
If it's greater than or equal to 70, then the program will execute the
content of the `if` block. If the grade less than 70, then the program will not
execute the content of the `if` block.

Like a Java class, an `if` statement can contain multiple statements inside it.
Therefore, an `if` statement can be followed by an open curly brace `{` if it is
meant to indicate the conditional execution of more than one statement. As
always, the open curly brace `{` must then be matched with a close curly brace
`}`:

```java
if (grade >= 70) {
    // as many conditional statements here
    // as I need for my program
}
```

Note that if we only have one conditional statement, we can omit the matching
curly braces:

```java
if (grade >= 70)
    System.out.println("Congrats! You passed!");
```

This notation is not recommended, as it makes it very easy to accidentally
expand or reduce the scope of an `if` statement.

An `if` statement can be followed by an `else` statement. When an `else`
follows an `if`, its content will be executed whenever the conditional clause
of the `if` statement is not true. It should be noted that an `else` statement
is not required to follow an `if` statement.

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
if (grade >= 70) {
    System.out.println("Congrats! You passed!");
    if (grade >= 90) {
        System.out.println("Wow! You got an A!");
        System.out.println("Great job!");
    } else {
        System.out.println("Great job!");
    }
}
```

In the example above, we want to further customize the greeting message for
students that pass their test. We want to give an extra congratulations to
those students who receive a score of 90 and up; so we check to see if their
grade is greater than or equal to a 90 and display a message if that is the
case. If not, we simply tell them they did a great job on the test.

Can we modify the code in the previous example to remove the duplicated line of
code between the case where the student's grade is greater than or equal to 90
and the case where the student's grade is less than 90 but greater than or
equal to 70?

```java
if (grade >= 70) {
    System.out.println("Congrats! You passed!");
    if (grade >= 90) {
        System.out.println("Wow! You got an A!");
    }
    System.out.println("Great job!");
}
```
