# Impossibrawler!
### Description
### How do I beat these guys?!

### Author : barrwani

<br> This is my first time ever reversing a game, it was great fun! <br>
<br> We are given a `.exe` file and the `.pck` file where the `.exe` will just open the game and you cannot beat it no matter what you do.
So, we need to look at the pck file. I basically decompile it using https://github.com/bruvzg/gdsdecomp

<br> After that, there are a lot of scripts in the file but the most interesting one is at `Level_1.gd` and `Level_2.gd`. <br>

<br> Level_1.gd script:

![image](https://github.com/Jurf3d/CTF/assets/139546647/a9c386e4-0800-4afd-9db3-25958edc529a)

<br> Level_2.gd script:

![image](https://github.com/Jurf3d/CTF/assets/139546647/8bfc72e6-545b-44ba-98ae-1cd947124264)

<br> In level 1, if there are no enemies left, it will generate a seed based on `Vals.hits ^ enemies_left ^ Vals.playerdmg` 
and use the `randf()` function to generate a random floating point number and assigns it to `Vals.sd`.
After that, it will go to level 2.

<br> In level 2, if there are no enemies left, it will take the `integer` of `Vals.sd` and use generate a floating
point number and assigns to `fbytes`. The `Vals.sd` will then be updated with this new random float value and
converts the `fbytes` float value into its string representation. Finally, it converts the `fbytes` into its ASCII
 values and encodes them into hex format.

<br> So basically during level 1, the seed will always be 0 because of the condition of the enemy left. Also, since
level 2's is taking integer value of `sd`, we know that it will always be 0. Hence, it will not change the flag value.
<br><br>

![image](https://github.com/Jurf3d/CTF/assets/139546647/36c76416-650c-465c-adb6-63bdd5a1ca45)

<br> GDscript https://gdscript-online.github.io/#H4sIAAAAAAAAA22QQQrCMBBF180pQlYJYiniSnDtrgsPYEmTqRY0lZmoLeLdTVptVQwk8DPv_5kEWg_OEs8bC-yqkaPb8zXfamebU345lYAbcIDaN5g6uEnFGKsuzvACQdtOqhVLou9QewrGJUtCQkoANqj-csezsBfZwFVl5yGSEcPQpgqRfYWiYyiz5Iy183JQ6isz3pNVb0TM4xKTDsekXvAf-v8cXzOMCHmcRnkFHTV99Pmtjm36Jx_3Y2rqm0KTqWup0gO0BTgTfl5OTkP6Znx1F3zWG2dcPIR6AltZ7W2nAQAA
