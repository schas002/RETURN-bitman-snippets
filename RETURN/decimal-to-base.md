# RETURN - Decimal to Base
This snippet uses divmod to convert from decimal to any arbitrary base.
```
{[[A]÷$][]#␃}§
```
Where `[A]` is the base to convert to.

# Demonstration
To convert `5` to binary (base 2):
```
5{[2÷$][]#␃}§
5             push 5 to stack
 {            set current stack to 5
  [   ][]#    while loop
   2÷$          divmod by 2 and check if top of stack > 0
                this leaves the mods on stack
          ␃  reverse stack
           }  go back to parent stack
            § join top stack into number
```
The result will be `101`.
