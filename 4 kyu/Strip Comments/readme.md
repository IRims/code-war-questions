# Strip Comments

Complete the solution so that it strips all text that follows any of a set of comment markers passed in. Any whitespace at the end of the line should also be stripped out.

Example:

Given an input string of:
```
apples, pears # and bananas
grapes
bananas !apples
```
The output expected would be:
```
apples, pears
grapes
bananas```

The code would be called like so:
```
result = strip_comments("apples, pears # and bananas\ngrapes\nbananas !apples", ["#", "!"])
# result should == "apples, pears\ngrapes\nbananas"
```
## Solution:
### Python:
```
def strip_comments(input_string, markers):
    lines = input_string.split('\n')  
    result_lines = []
    for line in lines:
        for marker in markers:
            if marker in line:
                line = line.split(marker)[0]
        result_lines.append(line.rstrip())  
    
    return '\n'.join(result_lines)

```
