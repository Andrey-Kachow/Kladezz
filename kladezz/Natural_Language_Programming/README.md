# Natural Language Programming

The idea is to make a programming language that is as close as possible to the natural language.

## Design Choices

1) I think that would be cool to make the language not whitespace sensitive so that a programmer could align code as they want
2) Keywords or phrases shall be UPPERCASE. It will leave freedom for the user to notice them in natural language sentences.
3) In addition to the 2, upper case will create a feeling of yelling at the machine what to do, which I think is funny.

### 1. Whitespace sensitivity.

Consider the following Python code.

```

for _ in range(5):
    if 1 + 1 == 2:
        print("Hello")

```

Is a valid Python code. But the following is not:

```

for _
    in
    range(5):

  if 1 + 1 == 2: 
    print("Hello")

```

Making the language whitespace sensitive. As well as indentation sensitive.


On the other hand, consider the following snippet of a draft Natural Language Code:

```

FOR EVERY item IN A range between 0 and 5 DO THE FOLLOWING TASK:
    DEPENDING ON THE CASE,
    IF 1 + 1 = 2 THEN DO THE FOLLOWING:
        output "Hello" to standard output.
    OTHERWISE
        PROCEED.
    COMPLETE THE CASE AND THEN PROCEED.
COMPLETE THE TASK AND THEN PROCEED.
    

```
Every loop or conditional construct has a beginning and ending, like '{' and '}' in the C programming language.
Wrapper code may be restricted to ensure consistent interpretation.


The code does not look attractive for the experienced programmer.
However, the code can be reformatted as a natural language pretty much.


FOR EVERY item IN A range between 0 and 5 DO THE FOLLOWING TASK:
DEPENDING ON THE CASE,
IF 1 + 1 = 2 THEN DO THE FOLLOWING:
output "Hello" to standard output.
OTHERWISE
PROCEED.
COMPLETE THE CASE AND THEN PROCEED.
COMPLETE THE TASK AND THEN PROCEED.


Notice that the capitalized KEYWORDS are grouped together forming a KEYFRASE.
Also, function syntax is such that the function name is broken down into several words and allows arguments to be between.
It might be challenging to parse and therefore the concept must be proved.
It is hoped to be possible because that would imply being cool.


