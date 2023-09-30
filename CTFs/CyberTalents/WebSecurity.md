## 01 - Admin has the power

* By examining the source code we can find the user and password for the support user (username: support password: x34245323)
* Using burp we can intercept the connection and see the query sent
* Using burp we can edit the role from user to admin role = admin

#### flag: hiadminyouhavethepower

## 02 - This is Sparta

* By Checking the source code there is a suspicious script at the end of the file 

```
var _0xae5b=[
"\x76\x61\x6C\x75\x65", //value 
"\x75\x73\x65\x72", //user 
"\x67\x65\x74\x45\x6C\x65\x6D\x65\x6E\x74\x42\x79\x49\x64", //get element by ID
"\x70\x61\x73\x73" //pass
,"\x43\x79\x62\x65\x72\x2d\x54\x61\x6c\x65\x6e\x74", //Cyber-Talent
"\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x43\x6F\x6E\x67\x72\x61\x74\x7A\x20\x0A\x0A", //Congratz
"\x77\x72\x6F\x6E\x67\x20\x50\x61\x73\x73\x77\x6F\x72\x64"]; //wrong password
function check(){
var _0xeb80x2=document[_0xae5b[2]](_0xae5b[1])[_0xae5b[0]];

var _0xeb80x3=document[_0xae5b[2]](_0xae5b[3])[_0xae5b[0]];

if(_0xeb80x2==_0xae5b[4]
&&_0xeb80x3==_0xae5b[4])
{alert(_0xae5b[5]);} else {alert(_0xae5b[6]);}}
```
The code is hexadecimal characters that when decoded tells us that the username and password are Cyber-Talent using these username and password we can login and get the flag

#### flag: {J4V4_Scr1Pt_1S_Aw3s0me}

## 02 Iam A Legend
* By checking the source code we find that there is a weird script that uses only 6 characters mostly []+
* This is called java-script-fuck obfuscated text by decoding it *most sites just crashed so I found a write-up where someone else managed to decode it* we will get the username and pass which are Cyber Talent
* By using these username and password we get the flag 

#### flag: {J4V4_Scr1Pt_1S_S0_D4MN_FUN}

## 03 Cool Name Effect
* Try anytype of injection
  ```
  <script>
  ```
didn't work 

I used
  ```
  <noembed><img title="</noembed><img src onerror=alert(1)>"></noembed>
  ```
  
and got the flag

#### flag: ciyypjz

## 04 Encrypted Data
* By checking the source of the webpage we find that 

  ``` html
    <link rel="stylesheet" href="admin/assets/style.css">
  ```

* By going to the admin page we find the admin login in the source code there we find a hidden db
*admin/secret-database/db.json*

* by using this link we can access the database and get the flag {"flag":"ab003765f3424bf8e2c8d1d69762d72c"}
* The flag is md5 encrypted by decrypting it you will get the actual flag
#### flag: badboy