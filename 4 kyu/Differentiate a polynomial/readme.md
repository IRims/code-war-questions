# Differentiate a polynomial
Create a function that differentiates a polynomial for a given value of `x`.

Your function will receive 2 arguments: a polynomial as a string, and a point to evaluate the equation as an integer.

Assumptions:
- There will be a coefficient near each `x`, unless the coefficient equals `1` or `-1`.
- There will be an exponent near each `x`, unless the exponent equals `0` or `1`.
- All exponents will be greater or equal to zero

Examples:
```
differenatiate("12x+2", 3)      ==>   returns 12
differenatiate("x^2+3x+2", 3)   ==>   returns 9
```

## Solution:
### Python:
```
import re

def differentiate(poly, x):
    terms , result = re.findall(r'([+-]?\d*)(x\^?\d*)', poly) , 0
    for term in terms:
        coeff, x_part = term
        if coeff == '' or coeff == '+':
            coeff = 1
        elif coeff == '-':
            coeff = -1
        else:
            coeff = int(coeff)
        if x_part == 'x':
            exponent = 1
        elif x_part == 'x^0':
            exponent = 0
        else:
            exponent = int(x_part.split('^')[1])
        if exponent > 0: result += coeff * exponent * (x ** (exponent - 1))
    return result

```