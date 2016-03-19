# RETURN - OR using AND and NOT

This snippet demonstrates the [De Morgan's laws](http://en.wikipedia.org/wiki/De Morgan's laws) in RETURN.

> The negation of a disjunction is the conjunction of the negations.

or, in other words,

> "***not (A or B)***" is the same as "***(not A) and (not B)***".

```
[A]~[B]~&~
```

`[A]` means "item A enters stack", `[B]` means "item B enters stack". Replace these with the values you need to use.

## Demonstration

```
3~5~&~.
```

1. After `3`, the number 3 enters the stack.
2. After `~`, the 3 is negated to -4.
3. After `5`, the number 5 enters the stack.
4. After `~`, the 5 is negated to -6.
5. After `&`, the -4 and -6 are replaced with the bitwise AND of the two numbers, which is -8.
6. After `~`, the -8 is negated to 7.

After the final `.`, we get the output:

```
7
```
