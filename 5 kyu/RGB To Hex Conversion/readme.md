# RGB To Hex Conversion

The rgb function is incomplete. Complete it so that passing in RGB decimal values will result in a hexadecimal representation being returned. Valid decimal values for RGB are 0 - 255. Any values that fall out of that range must be rounded to the closest valid value.

Note: Your answer should always be 6 characters long, the shorthand with 3 will not work here.

Examples (input --> output):
```
255, 255, 255 --> "FFFFFF"
255, 255, 300 --> "FFFFFF"
0, 0, 0       --> "000000"
148, 0, 211   --> "9400D3"
```

## Solution:
### Python:

```
def rgb(r, g, b):
    def to_hex (number):
        if number > 255:
            number =255
        elif number < 0:
            number = 0
        return format(number, '02X')
    return to_hex(r) + to_hex(g) + to_hex(b)
```