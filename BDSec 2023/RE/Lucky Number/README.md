# Lucky Number
### Description
### Find the lucky number and get your rewards :D

### Download Link : lucky_number.run

### MD5 of the file : 4fc64afc55f6aac260254cf4ef944ed0

### Flag Format : BDSEC{lucky_number_here}

### Example Flag : BDSEC{2023}

### Author : NomanProdhan

<br>Upon opening the file in ghidra, we see the following:

![image](https://github.com/Jurf3d/CTF/assets/139546647/a1a83ed2-10a6-47fc-b0a1-de13975f9db4)

<br> For this, I am going to rename the functions and variables for better readability. <br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/df1965b5-7d2d-4341-8535-021c007ca1af)

<br> The `doSomething` function is just going to reverse the numbers. For example, if I type `12345`, it will return `54321`. <br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/4b2e4b5f-161c-4880-b9c8-6e3115446723)

<br> Alright, lets get debugging!

![image](https://github.com/Jurf3d/CTF/assets/139546647/7100d25f-4d6e-4d12-a7a9-7cf9dada699c)

I am going to set a breakpoint at `cmp` to see what digit is it comparing to.

![image](https://github.com/Jurf3d/CTF/assets/139546647/51247397-3d3d-4121-afd8-9e8d4448f809)

<br> We see that `rax` which is the input is `54321` because of the reverse function and it is comparing with `rdx` which is `20365011073`.
So, we need to reverse it and it becomes `37011056302`. Next, we take this number and run the program again. <br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/bcd678f5-2ddb-4edf-8b35-90622f8e9b4a)

Flag: BDSEC{37011056302}
