# Capture message 2
## Level: 1 Score 10 Category crypto
### Hm hm hm. We have seen this before... a long time ago. But we are to stupid to crack it...help us, again! I guess the original content of this weird garbage is english. Maybe that help's you to break it! Hint: Flag content should be lowercase.
### Link: https://github.com/SecurityValley/PublicCTFChallenges/tree/master/crypto/weird_but_old
<br><br>
Upon following the link, we are given a file. The contents are:

```
XOVUD IXW EDBVQQVQB GF BDG ZDHP GVHDA FN WVGGVQB EP KDH WVWGDH FQ GKD EXQR XQA FN KXZVQB QFGKVQB GF AF FQUD FH GIVUD WKD KXA SDDSDA VQGF GKD EFFR KDH WVWGDH IXW HDXAVQB ELG VG KXA QF SVUGLHDW FH UFQZDHWXGVFQW VQ VG XQA IKXG VW GKD LWD FN X EFFR GKFLBKG XOVUD IVGKFLG SVUGLHDW FH UFQZDHWXGVFQWWF WKD IXW UFQWVADHVQB VQ KDH FIQ CVQA XW IDOO XW WKD UFLOA NFH GKD KFG AXP CXAD KDH NDDO ZDHP WODDSP XQA WGLSVA IKDGKDH GKD SODXWLHD FN CXRVQB X AXVWPUKXVQ IFLOA ED IFHGK GKD GHFLEOD FN BDGGVQB LS XQA SVURVQB GKD AXVWVDW IKDQ WLAADQOP X IKVGD HXEEVG IVGK SVQR DPDW HXQ UOFWD EP KDH PFL WKFLOA LWD VOVRDODIVWUXHHFOO XW NOXB SODXWD NFHCXG GKD NOXB EDNFHD WLECVGGVQBGKDHD IXW QFGKVQB WF ZDHP HDCXHRXEOD VQ GKXG QFH AVA XOVUD GKVQR VG WF ZDHP CLUK FLG FN GKD IXP GF KDXH GKD HXEEVG WXP GF VGWDON FK ADXH FK ADXH V WKXOO ED OXGD IKDQ WKD GKFLBKG VG FZDH XNGDHIXHAW VG FUULHHDA GF KDH GKXG WKD FLBKG GF KXZD IFQADHDA XG GKVW ELG XG GKD GVCD VG XOO WDDCDA YLVGD QXGLHXO ELG IKDQ GKD HXEEVG XUGLXOOP GFFR X IXGUK FLG FN VGW IXVWGUFXGSFURDG XQA OFFRDA XG VG XQA GKDQ KLHHVDA FQ XOVUD WGXHGDA GF KDH NDDG NFH VG NOXWKDA XUHFWW KDH CVQA GKXG WKD KXA QDZDH EDNFHD WDDQ X HXEEVG IVGK DVGKDH X IXVWGUFXGSFURDG FH X IXGUK GF GXRD FLG FN VG XQA ELHQVQB IVGK ULHVFWVGP WKD HXQ XUHFWW GKD NVDOA XNGDH VG XQA NFHGLQXGDOP IXW MLWG VQ GVCD GF WDD VG SFS AFIQ X OXHBD HXEEVGKFOD LQADH GKD KDABD
```
<br><br>
Again, we use [cipher-identifier](https://www.dcode.fr/cipher-identifier) to identify the cipher.
The cipher is Mono-alphabetic Substitution. Upon decryption, we get the following:

```
ALICE WAS BEGINNING TO GET VERY TIRED OF SITTING BY HER SISTER ON THE BANK AND OF HAVING NOTHING TO DO ONCE OR TWICE SHE HAD PEEPED INTO THE BOOK HER SISTER WAS READING BUT IT HAD NO PICTURES OR CONVERSATIONS IN IT AND WHAT IS THE USE OF A BOOK THOUGHT ALICE WITHOUT PICTURES OR CONVERSATIONSSO SHE WAS CONSIDERING IN HER OWN ZIND AS WELL AS SHE COULD FOR THE HOT DAY ZADE HER FEEL VERY SLEEPY AND STUPID WHETHER THE PLEASURE OF ZAKING A DAISYCHAIN WOULD BE WORTH THE TROUBLE OF GETTING UP AND PICKING THE DAISIES WHEN SUDDENLY A WHITE RABBIT WITH PINK EYES RAN CLOSE BY HER YOU SHOULD USE ILIKELEWISCARROLL AS FLAG PLEASE FORZAT THE FLAG BEFORE SUBZITTINGTHERE WAS NOTHING SO VERY REZARKABLE IN THAT NOR DID ALICE THINK IT SO VERY ZUCH OUT OF THE WAY TO HEAR THE RABBIT SAY TO ITSELF OH DEAR OH DEAR I SHALL BE LATE WHEN SHE THOUGHT IT OVER AFTERWARDS IT OCCURRED TO HER THAT SHE OUGHT TO HAVE WONDERED AT THIS BUT AT THE TIZE IT ALL SEEZED XUITE NATURAL BUT WHEN THE RABBIT ACTUALLY TOOK A WATCH OUT OF ITS WAISTCOATPOCKET AND LOOKED AT IT AND THEN HURRIED ON ALICE STARTED TO HER FEET FOR IT FLASHED ACROSS HER ZIND THAT SHE HAD NEVER BEFORE SEEN A RABBIT WITH EITHER A WAISTCOATPOCKET OR A WATCH TO TAKE OUT OF IT AND BURNING WITH CURIOSITY SHE RAN ACROSS THE FIELD AFTER IT AND FORTUNATELY WAS MUST IN TIZE TO SEE IT POP DOWN A LARGE RABBITHOLE UNDER THE HEDGE
```
<br><br>
We can see that the flag is ILIKELEWISCARROLL. The description said that it must be lowercase. <br><br>
Hence the flag is: SecVal{ilikelewiscarroll}
