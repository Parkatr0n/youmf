
VirtualScript
=============

VirtualScript is my take on Bash. It's the easy language, one anyone can use but that is also robust enough to write most scripts using.

Comments
---------
Comments are indicated with a `#` marker.
```
# my test comment

set x=1 # another comment. good work!
```

Variables
---------
Variables are set using the `set` command, and referenced using a `$` sign.
```
# Set value of x to 1
set x=1

# Reference a variable
echo $x
```

Conditional Checking
--------------------
The only conditionals are `if` and `while`. More may appear in the future.
```
# IF
if 1 == 1
then
  echo "1 is 1."
end
```

```
# WHILE
set x=0
while $x < 10
then
  echo $x
end
```

Arguments
---------
Arguments are information passed to the program through the commandline.
Arguments are referenced using a `%` sign and a number.
There is no maximum to the number of arguments you can reference.
If you reference and argument that was never provided, it will return an empty string.

For the example code below, I ran the command `test Hello
```
# echo out to the user what they put in
