# Easy authentication
## Level: 1 Score 5 Category coding
### Let's start simple in this game. We have collected a piece of javascript. There is a validate function but we don't know the password... can you hack it?
### Link: https://github.com/SecurityValley/PublicCTFChallenges/blob/master/coding/easy_authentication

<br><br>
We are given a javascript code:
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
    const pass = [106,117,115,116,95,119,97,114,109,105,110,103,95,117,112];
    const pa = Array.from(password);

    for(let i = 0; i < pa.length; i++) {
        if(pa[i].charCodeAt(0) !== pass[i]) {
            throw new Error("pass violation. wrong credentials");
        }
    }

    banner(password);
}

function banner(payload) {
    console.info("that was great !!!");
    console.info("run the following command to get the flag.")
    console.info(`curl -X POST http://ctf.securityvalley.org:7777/api/v1/validate -H 'Content-Type: application/json' -d '{"pass": "${payload}"}'`)
}
```

Based on the code, we know that the script is written in node.js because of the require function. The process.stdin and process.stdout are global objects in Node.js.
<br><br>
Most importantly, we look at the validate function. It checks if the entered password is correct or not. The password is in decimal form, so we need to change it back to ASCII code.

Decimals:
```
106 117 115 116 95 119 97 114 109 105 110 103 95 117 112
```

ASCII:
```
just_warming_up
```
<br>
Next we run the following on the terminal: <br><br>

![Screenshot 2023-07-16 075220](https://github.com/Jurf3d/CTF/assets/139546647/7a42d749-dc36-4f93-acd5-7731920c0d90)

Flag: SecVal{J4v45Cr1P7_15_57r4444N93}
