# Capture message
## Level: 1 Score 5 Category crypto
### We have captured a message. But what is the content??? Help us, please!
### Link: https://github.com/SecurityValley/PublicCTFChallenges/tree/master/crypto/old_history
<br><br>
We are provided with a message.txt file, the contents are as follow:

```
Riihuhg vdb ylvlwhg hoghuob dqg. Zdlwhg shulrg duh sodbhg idplob pdq iruphg. Kh bh ergb ru pdgh rq sdlq sduw phhw. Brx rqh ghodb qru ehjlq rxu iroob dergh. Eb glvsrvhg uhsoblqj pu ph xqsdfnhg qr. Dv prrqoljkw ri pb uhvroylqj xqzloolqj.

Dsduwphqwv vlpsolflwb ru xqghuvwrrg gr lw zh. Vrqj vxfk hbhv kdg dqg rii. Uhpryhg zlqglqj dvn hasodlq gholjkw rxw ihz ehkdyhg odvwlqj. Ohwwhuv rog kdvwlob kdp vhqglqj qrw vha fkdpehu ehfdxvh suhvhqw. Rk lv lqghhg wzhqwb hqwluh iljxuh. Rffdvlrqdo glplqxwlrq dqqrxqflqj qhz qrz olwhudwxuh whuplqdwhg. Uhdoob uhjdug hafxvh rii whq sxoohg. Odgb dp urrp khdg vr odgb irxu ru hbhv dq. Kh gr ri frqvxowhg vrphwlphv frqfoxghg pu. Dq krxvhkrog ehkdylrxu li suhwhqghg. Brx fdq xvh wklvmxolxv dv iodj exw grqw irujhw wr irupdw.

Qrz lqgxojhqfh glvvlplodu iru klv wkrurxjkob kdv whuplqdwhg. Djuhhphqw riihqglqj frppdqghg pb dq. Fkdqjh zkroob vdb zkb hoghvw shulrg. Duh surmhfwlrq sxw fhoheudwhg sduwlfxodu xquhvhuyhg mrb xqvdwldeoh lwv. Lq wkhq gduh jrrg dp urvh euhg ru. Rq dp lq qhduhu vtxduh zdqwhg.
```
<br><br>
We can use [cipher-identifier](https://www.dcode.fr/cipher-identifier) to identify the cipher. <br><br>

Upon identified, we know that it is caesar cipher. Decrypt it and you will get the following:

```
Offered say visited elderly and. Waited period are played family man formed. He ye body or made on pain part meet. You one delay nor begin our folly abode. By disposed replying mr me unpacked no. As moonlight of my resolving unwilling.

Apartments simplicity or understood do it we. Song such eyes had and off. Removed winding ask explain delight out few behaved lasting. Letters old hastily ham sending not sex chamber because present. Oh is indeed twenty entire figure. Occasional diminution announcing new now literature terminated. Really regard excuse off ten pulled. Lady am room head so lady four or eyes an. He do of consulted sometimes concluded mr. An household behaviour if pretended. You can use thisjulius as flag but dont forget to format.

Now indulgence dissimilar for his thoroughly has terminated. Agreement offending commanded my an. Change wholly say why eldest period. Are projection put celebrated particular unreserved joy unsatiable its. In then dare good am rose bred or. On am in nearer square wanted. 
```
<br><br>
We can see that the flag is `thisjulius` on the second paragraph. <br><br>
Flag: SecVal{thisjulius}
