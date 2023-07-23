# Binary101
We are presented with a binary file. First things first, we are going to look into the file type.

```
binary101: ELF 64-bit LSB executable, x86-64, version 1 (GNU/Linux), statically linked, BuildID[sha1]=7d6a1956c9fc0f21320dd30859b54744457b2759, for GNU/Linux 3.2.0, not stripped
```

<br>As we can see, it is a 64-bit executable, statically linked and it is not stripped.
You can read more about static vs dynamic linked [here](https://blog.hubspot.com/website/static-vs-dynamic-linking#:~:text=Essentially%2C%20static%20linking%20involves%20compiling,when%20the%20app%20is%20launched.).
Not stripped means that if we reverse the file, we will be able to see the function names and things like that
which will make it easier to analyze. <br>
<br>Next we load the file into ghidra. <br><br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/c3d86835-5304-4783-8dff-6765e9544788)

<br>
Upon analyzing it, we can see that there is string comparison being done and if it is equal to 0, it will print out some data. So lets see what that data is.<br><br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/02fabed8-1310-476c-ab64-8d8d29ff7b9f)

<br> As we can see, the data is `Secret Message: Code Is Gold`.<br>
Hence the flag is `Code Is Gold`.




