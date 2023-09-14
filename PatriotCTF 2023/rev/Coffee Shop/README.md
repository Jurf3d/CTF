# Coffee Shop
### Description
### I hate it when coffee shops misspell my name! Are you able to find what it is?

### Flag format: CACI{FirstnameLastname}

### Author: CACI

```java
package defpackage;

import java.util.Base64;
import java.util.Scanner;

/* renamed from: CoffeeShop  reason: default package */
/* loaded from: CoffeeShop.jar:CoffeeShop.class */
class CoffeeShop {
    CoffeeShop() {
    }

    public static void failure() {
        System.out.println("Sorry! You didn't get it right...");
    }

    public static void success() {
        System.out.println("Nice! You got it!");
        System.out.println("Submit the name you entered inside CACI{} to get points!");
    }

    public static void main(String[] strArr) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("What's my name?");
        String encodeToString = Base64.getEncoder().encodeToString(scanner.nextLine().getBytes());
        if (encodeToString.length() != 20) {
            failure();
        } else if (!encodeToString.endsWith("NoZXI=")) {
            failure();
        } else if (!encodeToString.startsWith("R2FsZU")) {
            failure();
        } else if (!encodeToString.substring(6, 14).equals("JvZXR0aW")) {
            failure();
        } else {
            success();
        }
    }
}
```

<br> The conditions shows that the string is `R2FsZUJvZXR0aWNoZXI=` and after you convert the base64, you get `GaleBoetticher`.<br>
<br> Flag: CACI{GaleBoetticher}.
