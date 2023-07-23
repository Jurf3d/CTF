# Binary202

Upon loading it into ghidra, we can see the following: <br><br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/2e02eeaf-29af-4b21-8786-87c4848c3707)

<br><br>
Now we can see there is a lot of functions and it takes time to really know the purpose of each function. For me, I have the habit of looking at the most important 
part first `(uVar2 = FUN_00401775)`. So lets take a loot at the function of that. <br><br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/9745a165-3b2d-421b-9a1b-ff07b1ef77ad)

<br> The part that really caught my attention is the `for` loop. It seems like it iterates over each character
in the string pointed to by `pcVar1`. If a character is a lowercase of uppercase letter (as per ASCII values),
it modifies the character. In ASCII, '`' is just before 'a' and '{' is just after 'z'. Similarly, '@' is just before 'A' and '[' is just after 'Z'. 
Therefore, this condition checks if the character is an uppercase letter ('A' to 'Z') or a lowercase letter ('a' to 'z'). 
If the character is between 'a' and 'm' or 'A' and 'M', it shifts the character 13 places forward.
This makes me think that it is a ROT13 cipher and if the character is between 'n' and 'z' or 'N' and 'Z', it
shifts the character 13 places backwards. Hence, I deduced that we need to use ROT13 cipher to decrypt the flag.

<br> Next, I decided to set a breakpoint at `0x00401933`, right before the `if` statement being called.
<br><br> I am going to use `gdb` to load the program to examine the contents of registers and memory.
After the breakpoint, we take a look at what is on the stack registers. <br><br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/eacbe972-fb71-4ce5-8f2b-50a882ec72ad)

<br> We can see that there is something on the stack, `Gevcyr Bar Avar` and `Gur sbk whzcf bire gur png`. It looks gibberish at first,
but we know that since it is being `ROT13ed`, we can take the content into [here](https://www.dcode.fr/rot-13-cipher).
After decoding, the messages are `Triple One Nine` and `The fox jumps over the cat` respectively.
<br><br>
Since the flag format is `xxx xxx xxxxx xxxx xxx xxx`, we know that the flag is `The fox jumps over the cat`.

