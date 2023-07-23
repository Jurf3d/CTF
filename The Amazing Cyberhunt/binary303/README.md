# binary303

We are given a binary file and when we run the file check, it looks weird. <br>
```
binary303: ELF 64-bit LSB executable, x86-64, version 1 (GNU/Linux), statically linked, no section header
```
<br> In ghidra, the functions are even harder determine what is going on. Based on my past experiences, this is telling me that it is an **UPX** file and we need to decompress it. But first, let us verify that.

![image](https://github.com/Jurf3d/CTF/assets/139546647/3b5e996a-8992-455c-a4f5-58ec79b639b5)

<br> Yep, we verified that it is indeed an **UPX** file. After that, we analyze it with ghidra and found that it is quite similar to `binary202`. So we use the same method to solve it. <br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/e8110963-8376-4498-8468-77845ffeb4d0)

<br> Since the flag format is `xxxxxx xx xxx xxx xxxxxx`, once deciphered, we get the flag `Yellow Is The New Purple`. 
