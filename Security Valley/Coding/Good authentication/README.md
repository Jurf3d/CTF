# Good authentication
## Level: 1 Score 10 Category coding
### After your first strike, the development team has increased the power of there login function. Are you strong enough to break it again?
### Link: https://github.com/SecurityValley/PublicCTFChallenges/tree/master/coding/good_authentication
<br><br>
Upon clicking the link, we are given yet another Node.js script.

```js
const readline = require('readline').createInterface({
    input: process.stdin,
    output: process.stdout
});

readline.question('Please enter password \n', password => {
    console.log(`Gonna check if ${password} is correct`);
    readline.close();
    validate(password)
});

function validate(password) {

    if (password.length != 12) {
        throw new Error("pass violation. wrong password length");
    }


    const block1 = Array.from(password).slice(0, 4)
    const block2 = Array.from(password).slice(4, 8)
    const block3 = Array.from(password).slice(8, 12)

    const block = [
        block1,
        block2,
        block3
    ]

    let crafted = "";

    for (let i = 0; i < block.length; i++) {
        for (let a = 0; a < block[i].length; a++) {
            if (i == 0) {
                crafted += String.fromCharCode(String(block[i][a]).charCodeAt(0) ^ 7)
            } else if (i == 1) {
                crafted += String.fromCharCode(String(block[i][a]).charCodeAt(0) ^ 11)
            } else {
                crafted += String.fromCharCode(String(block[i][a]).charCodeAt(0) ^ 9)
            }
        }
    }

    if(crafted !== "sontTbxTjffe") {
        throw new Error("pass violation. wrong credentials");
    }


    banner(password);
}

function banner(payload) {
    console.info("that was great !!!");
    console.info("run the following command to get the flag.")
    console.info(`curl -X POST http://ctf.securityvalley.org:7777/api/v1/validate -H 'Content-Type: application/json' -d '{"pass": "${payload}"}'`)
}
```

<br>In the code, the validate function breaks down the password into three blocks of four characters: <br>
`block1` = The first four characters <br>
`block2` = The next four characters <br>
`block3` = The final four characters <br>

These blocks will be stored in an array called `block`. Each character in the blocks is XOR-ed with a different value depends on its block.
In this case: <br>
`block1` is XOR-ed with 7. <br>
`block2` is XOR-ed with 11. <br>
`block3` is XOR-ed with 9. <br>

Then it is compared to the string `sontTbxTjffe`. If it doesn't match, it will show wrong credentials. If true, then it will give us the flag.


So I wrote a python code to decipher the password:
```py
xor_values = [7, 11, 9]
coded_string = "sontTbxTjffe"
password = ""

for i in range(len(coded_string)):
    char = coded_string[i]
    xor_value = xor_values[i // 4]  # Select the correct XOR value based on char position
    original_char = chr(ord(char) ^ xor_value)
    password += original_char

print(password)
```
<br><br>
Upon running the script, it shows the password is `this_is_cool`
<br><br>
Next, we run the following in the terminal:
<br><br>
![image](https://github.com/Jurf3d/CTF/assets/139546647/2eb3ece2-c7f8-42b3-9720-d806b0184eb1)

Flag: SecVal{9R34t_y0u_X0R3d}
