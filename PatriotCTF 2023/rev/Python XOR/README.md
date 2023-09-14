# Python XOR
### Description
### The flag has been encrypted, yet again. Find a way to iterate through the alphabet variable to decrypt the flag.

### Flag format: Flag{}

### Author: CACI

<br> We are given a file `XOR.py`<br>

```py
from string import punctuation

alphabet = list(punctuation)
data = "bHEC_T]PLKJ{MW{AdW]Y"
def main():
#   For loop goes here
    key = ('')
    decrypted = ''.join([chr(ord(x) ^ ord(key)) for x in data])
    print(decrypted)
main()
```

<br> Brute force XOR at `key = 24` and you get the flag.<br>
<br> Flag: Flag{python_is_e@sy}
