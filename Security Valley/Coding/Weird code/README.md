# Weird code
## Level: 2 Score 15 Category coding
### I've found a weird piece of code in the internet. That looks strange....but there is a flag inside. I belive that! Help me, plz.
### Link: https://github.com/SecurityValley/PublicCTFChallenges/tree/master/coding/weird_code

<br><br>
Upon clicking the link, we are given this code in **code.txt**:

```
##################################################
 15           0 LOAD_GLOBAL              0 (print)
              2 LOAD_CONST               1 ('loading application')
              4 CALL_FUNCTION            1
              6 POP_TOP

 17           8 LOAD_GLOBAL              1 (magic)
             10 LOAD_CONST               2 ('8934')
             12 LOAD_GLOBAL              2 (get_flag)
             14 CALL_FUNCTION            0
             16 CALL_FUNCTION            2
             18 STORE_FAST               0 (d)

 19          20 LOAD_GLOBAL              0 (print)
             22 LOAD_FAST                0 (d)
             24 CALL_FUNCTION            1
             26 POP_TOP
             28 LOAD_CONST               0 (None)
             30 RETURN_VALUE
None
##################################################
  4           0 LOAD_CONST               1 ('k\\PbYUHDAM[[VJlVAMVk[VWQE')
              2 RETURN_VALUE
None
##################################################
  7           0 LOAD_CONST               1 (b'')
              2 STORE_FAST               2 (out)

  9           4 LOAD_GLOBAL              0 (range)
              6 LOAD_GLOBAL              1 (len)
              8 LOAD_FAST                1 (f)
             10 CALL_FUNCTION            1
             12 CALL_FUNCTION            1
             14 GET_ITER
        >>   16 FOR_ITER                46 (to 64)
             18 STORE_FAST               3 (i)

 10          20 LOAD_FAST                2 (out)
             22 LOAD_GLOBAL              2 (bytes)
             24 LOAD_GLOBAL              3 (ord)
             26 LOAD_FAST                1 (f)
             28 LOAD_FAST                3 (i)
             30 BINARY_SUBSCR
             32 CALL_FUNCTION            1
             34 LOAD_GLOBAL              3 (ord)
             36 LOAD_FAST                0 (k)
             38 LOAD_FAST                3 (i)
             40 LOAD_GLOBAL              1 (len)
             42 LOAD_FAST                0 (k)
             44 CALL_FUNCTION            1
             46 BINARY_MODULO
             48 BINARY_SUBSCR
             50 CALL_FUNCTION            1
             52 BINARY_XOR
             54 BUILD_LIST               1
             56 CALL_FUNCTION            1
             58 INPLACE_ADD
             60 STORE_FAST               2 (out)
             62 JUMP_ABSOLUTE           16

 12     >>   64 LOAD_FAST                2 (out)
             66 RETURN_VALUE
None
```

I actually spent a lot of time doing this challenge and I thought of giving up. But in the end, I looked for writeup that is written by [this guy](https://github.com/ricardo-uqueio/ctf_writeups/tree/main/sec_valley/coding/weird_code_COMPLETED#readme) so that I can have some guidance. Eventually, I created this python script:

```py
def main():
    d = magic('8934', get_flag())
    print(d)

def magic(k, f):
    out = b''
    for i in range(len(f)):
        out += bytes([ord(f[i]) ^ ord(k[i % len(k)])])
    return out

def get_flag():
    return 'k\\PbYUHDAM[[VJlVAMVk[VWQE'

if __name__ == '__main__':
    main()
```

<br>Upon running the script, we get the flag.<br>
Flag: SecVal{pythons_byte_code} <br><br>
Overall, I learnt a lot from playing this challenge.

# UPDATE
Found another writeup https://www.youtube.com/watch?v=79GfTc2tjWQ
