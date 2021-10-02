# hi
![image](https://user-images.githubusercontent.com/65381453/135704374-a039b3ca-d6a2-41ea-8a7a-9e6e9d7f5504.png)

```
Hi there! We used to work together back in our old company DEEMA. I recently had a problem with my computer and lost all the files on it. I remember creating a backup of my files on the company's servers. I know it's been a while, but could you please try to access those files? I would be very grateful!
```
backgroud

![image](https://user-images.githubusercontent.com/65381453/135704397-f2566dfd-9b55-465d-bd34-84b3c3437664.png)

so , first i things SSTI, and i try it , but i false

![image](https://user-images.githubusercontent.com/65381453/135704453-f11025cc-982f-403c-8c21-b422c2f9e1ed.png)

when i take solution in my friend PHUCZ , 

![image](https://user-images.githubusercontent.com/65381453/135704521-7e6d64a8-65ae-415b-bf59-73690a6eb0b2.png)

```
the lab has no security holes
```

uzz, i see 
```
We're sorry for the inconvenience but only Clancy can access this website at the moment.
```
Clancy ? username is Clancy ?
![image](https://user-images.githubusercontent.com/65381453/135704623-5aa39c28-3889-42b7-b71f-741a3e08c700.png)

yeh, it's true , next 

```
We're sorry, but only administrators can access this page!
```
use burpsuite

![image](https://user-images.githubusercontent.com/65381453/135704705-3645cb3b-486c-4b89-902a-c854927e4bac.png)

False -> True

then i take a message

![image](https://user-images.githubusercontent.com/65381453/135704727-c1250e9f-9f50-4b48-8340-4932ed0a9c16.png)

```
All admins are required to use the special DeemaBrowser to access the admin page. Please switch your browser from Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:92.0) Gecko/20100101 Firefox/92.0 to DeemaBrowser to continue
```

oke i change User-Agent: to  DeemaBrowser

![image](https://user-images.githubusercontent.com/65381453/135704809-33b0e1a8-f681-4d2e-aeac-48dc7aa98a4c.png)

and result

![image](https://user-images.githubusercontent.com/65381453/135704813-a4f5f9e6-9e7b-4de4-84e5-a3cd5b0d5ae4.png)

```
Basic Authorization not provided. Please provide a Basic Authorization with the passphrase "What'sTheMagicWord?"
```

i insert Authorization 

![image](https://user-images.githubusercontent.com/65381453/135704875-b3180928-512d-47f0-a02a-d678a82ea8e1.png)

result

![image](https://user-images.githubusercontent.com/65381453/135704884-16493548-8249-4cdf-867d-9e2e61af76e2.png)

messager is This file was only accessible in April of 2021. Today's current date hasn't been provided, so access has been blocked!

i give date 

![image](https://user-images.githubusercontent.com/65381453/135704924-cea72b38-4052-4557-9937-463d04ad02ad.png)

next messager is
```
This file was only accessible on Monday, 5th April 2021, at 12:00:00 GMT. Unless you have a time machine, access has been blocked
```
![image](https://user-images.githubusercontent.com/65381453/135704958-ae11759d-8f82-486c-a161-2f83168d44d9.png)

i have flag
![image](https://user-images.githubusercontent.com/65381453/135704959-28f14b1d-f4bb-4641-895a-4ee31afff7b3.png)

slove

