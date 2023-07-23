# No statics
## Level: 1 Score 10 Category reversing
### This time there is no static value inside...but you are the best. So crack it baby!
### Link: https://github.com/SecurityValley/PublicCTFChallenges/tree/master/reversing/no_static
<br><br>
For this challenge, I actually got the flag in the unintended way. But I will provide the intended solution as well.

<br> Upon downloading the file and running it, we get the following: <br><br>
![image](https://github.com/Jurf3d/CTF/assets/139546647/da4ff237-5d30-4155-8579-cd08dc95ed55)
<br><br> I entered the passphrase **123** to test out the program and it shows **mySecret**. I got curious so I tried using it as a passphrase
and it does work. <br><br>
![image](https://github.com/Jurf3d/CTF/assets/139546647/71b7549a-8574-49b2-8bc3-ed6a232ad639) 
<br><br>

**INTENDED SOLUTION** <br>

First, I check the file using `file` command. <br><br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/2008972c-21bb-4070-87d4-ae8c249f4191) <br>

Since it has `pie executable` enabled, which means that we need to run the program first then only we can get the correct address.

I opened the file in Ghidra to look at the code. In the main function, we see that the `strcmp` is being done at line 27. <br><br>
![image](https://github.com/Jurf3d/CTF/assets/139546647/03d33d2f-db35-48ca-8b8b-8d1e89f8ece6) <br>

Next, I run the program in a debugger and set the breakpoint at `strcmp`. <br><br>
![image](https://github.com/Jurf3d/CTF/assets/139546647/b4c56e8c-8a2d-4d97-a6bb-eaebbcc21835) <br><br>
![image](https://github.com/Jurf3d/CTF/assets/139546647/f314a0f9-ac0a-41ef-82df-a845d00a9a7b)

<br> As we can see, the string `123` and being compared with `mySecret`. So we know that the passphrase is mySecret. <br><br>
Finally, typing in the password correctly and it will provide us the flag. <br><br>

Flag: SecVal{Th15_Wa5_Hard3R}
