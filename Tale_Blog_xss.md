
## vendor
https://github.com/otale/tale

## describe


In the OptionsService class, the application does not properly validate or filter the `themeUrl` input. This oversight allows an attacker to inject malicious JavaScript code through URL manipulation. By crafting a malicious URL that includes executable HTML or JavaScript content, an attacker can exploit this vulnerability to perform a Cross-Site Scripting (XSS) attack.


## code analyze

In the `theme/setting` route, the `logo_url` output provided by the user is not filtered or sanitized, allowing an attacker to inject content such as `"> <img src=1 onerror=alert(/xss/)>` to close HTML tags and execute JavaScript. This leads to a **Stored XSS** vulnerability.

![Pasted image 20250221153414](https://github.com/dragonkeep/cve/blob/main/Tale_Blog_xss.assets/Pasted%20image%2020250221153414.png)

![Pasted image 20250221154759](https://github.com/dragonkeep/cve/blob/main/Tale_Blog_xss.assets/Pasted%20image%2020250221154759.png)

![Pasted image 20250221154926](https://github.com/dragonkeep/cve/blob/main/Tale_Blog_xss.assets/Pasted%20image%2020250221154926.png)

## POC 
![Pasted image 20250221154634](https://github.com/dragonkeep/cve/blob/main/Tale_Blog_xss.assets/Pasted%20image%2020250221154634.png)

![Pasted image 20250221154649](https://github.com/dragonkeep/cve/blob/main/Tale_Blog_xss.assets/Pasted%20image%2020250221154649.png)