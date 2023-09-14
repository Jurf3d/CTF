# Suboptimal
### Description
### I feel like my keygen might not be optimal, could you test it?

### Flag format: PCTF{}

### Author: @elbee#3779

<br> Opening the file in ghidra and we see the following: <br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/d46a74b9-dd37-43a3-8fe0-bfe18cfdb1d4)

The function of interest is the `complex` and `check_equals` function.

![image](https://github.com/Jurf3d/CTF/assets/139546647/b64c144a-23aa-4310-b7e7-faa7180a5b66)

![image](https://github.com/Jurf3d/CTF/assets/139546647/589fe1c6-63dd-4949-9125-58fc2d0abb56)

<br> The program is reading 23 characters and it is passing through a series of functions. The `complex` function checks whether the character's ASCII code is greater than 64 and less than 126.<br>
<br> The `check_equals` function basically check whether the input string is equals to `xk|nF{quxzwkgzgwx|quitH`<br>
<br> You can write a script or just solve it manually. <br>
<br> I run the program into a debugger, key in `abcdefghijklmnopqrstuvw` as input, and the output is `ijklmnopqrstuvwxyz{|}AB`. Hence, it's basically a shift cipher.<br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/d9ecf658-e182-4e4b-b2e1-850b010d22b6)

Flag: pctf{simproc_r_optimal}
