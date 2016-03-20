# RETURN: Base to Decimal
This snippet uses the double-then-add method of converting to decimal.
```
¦{␃0[␇1-][[A]×+]#}
```
Where `[A]` is the base to convert from.
# Demonstration
To convert `1011001` from binary to decimal:
```
1011001¦{␃0[␇1-][2×+]#}
1011001                  Push 1011001 to stack
       ¦                 Split 1011001
        {                Set the current stack to the split number
         ␃              Reverse
          0              Push 0 as accumulator
           [    ][   ]#  While loop
            ␇1-           Check if stack length > 0
                  2×+      If so, double accumulator and add next digit
                       } Go back to parent stack
```
The result will be `89`.
