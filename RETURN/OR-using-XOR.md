# RETURN - OR using XOR

This snippet uses XOR to implement OR in RETURN.

XOR differs from OR only in that `1 XOR 1 = 0` (unlike OR, where `1 OR 1 = 1`). To account for this case, we will use AND, where `1 AND 1 = 1`.

```
¤~&|
```

# Demonstration
```
3 7¤~&|
```
<ol>
<li>The numbers 3 and 7 are pushed to the stack: `3 7`</li>
<li>The number 3 is duplicated to the top of the stack: `3 7 3`</li>
<li>Bitwise NOT:
<code>
00000000000000000000000000000011    Top of stack as a 32-bit integer
11111111111111111111111111111100    Bitwise NOT of top of stack as a 32-bit integer
Stack: 3 7 -4
</code></li>
<li>Bitwise AND:
<code>
11111111111111111111111111111100    First number as a 32-bit integer
00000000000000000000000000000111    Second number as a 32-bit integer
00000000000000000000000000000100    Bitwise AND of the two numbers as a 32-bit integer
Stack: 3 4
</code></li>
<li>Bitwise XOR:
<code>
00000000000000000000000000000100    First number as a 32-bit integer
00000000000000000000000000000011    Second number as a 32-bit integer
00000000000000000000000000000111    Bitwise XOR of the two numbers as a 32-bit integer
Stack: 7
</code></li>
</ol>
The result is 7.
