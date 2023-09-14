# Patchwork
### Description
### This program should just give the flag, but I set the wrong value in the code and now it refuses to jump to the correct function. Could you patch it for me?

### Flag format: PCTF{}

### Author: @necktie5740

<br> Opening the file in ghidra shows the following: <br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/de4a6b59-96f6-4c48-8077-86e52e8b2f4c)

<br> We can see the `give_flag` function, so we just need to jump to that function to get the flag. <br>
<br> Flag: PCTF{JuMp_uP_4nd_g3t_d0Wn}
