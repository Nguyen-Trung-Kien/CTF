# Hi 

![image](https://user-images.githubusercontent.com/65381453/132948094-16b45476-a3f7-498e-b75f-32e06f2a08e7.png)

Download here [challenge.zip](https://github.com/anhchangmutrang/CTF/files/7147838/challenge.zip)

unzip and i have 1 items

![image](https://user-images.githubusercontent.com/65381453/132948264-1a60e349-a28f-4ef6-a3a8-559cb9e43c06.png)

![image](https://user-images.githubusercontent.com/65381453/132948336-4aff469f-94cc-48c4-9b5c-61e87cf47dcb.png)

what's this ?

I can't get any information in this picture, then i just remember "strings" in command , try

![image](https://user-images.githubusercontent.com/65381453/132948423-1adf1222-1f51-4a4d-94f3-ce791d2a6b5d.png)

i saw flag.zip, use binwalk 

![image](https://user-images.githubusercontent.com/65381453/132948437-39ab54a1-f2ab-48c9-a2c8-6e463272c899.png)

next i unzip flag.zip 

![image](https://user-images.githubusercontent.com/65381453/132948507-59cbd46d-42f1-422b-81bf-4c5c788ee270.png)

```
 unsupported compression method 99
```

I found the solution for this by using 7zip

![image](https://user-images.githubusercontent.com/65381453/132948642-837dc36c-eef1-4a60-8d1a-6f3416561e57.png)

but if u want to unzip i must be have password , but i don't have..

## Find password
when i use binwalk to unzip the picture there is another picture, see what it is

![image](https://user-images.githubusercontent.com/65381453/132948785-55d3a752-9af7-4dd7-ab8c-1eff44075998.png)

oh,After a while I discovered the rule

```
the row below will take the number of each number in the row above 
```
is it difficult to understand? 

oke

Line 1: 12 -> one 1 and one 2

deduce : Line 2: 1 + 11+ 12 -> 11112

Line 2: 11112 -> four 1 and one 2

deduce : Line 3: 2 + 41 + 12 -> 24112

Line 3: 24112 -> two 2 + one 4 + two 1

deduce : Line 4: 3 + 22+14+21 -> 3221421

Line 4: 3221421 -> one 3 + three 2 + two 1+ one 4

deduce : Line 5: 4 +13+32+21+14 -> 413322114

Line 5: 413322114 -> two 4+ three 1+two 3+ two 2

deduce : Line 6: 5 + 24+ 31+23+22 -> 524312322

Line 6: 524312322 -> one 5 + four 2+ one 4 + two 3 + one 1

deduce : line 7: 6 + 15+42+14+23+11 -> 61542142311

this is password and 

![image](https://user-images.githubusercontent.com/65381453/132949626-c53f0e1a-1f7c-4db3-b019-41cbb6027321.png)

i have flag.txt

![image](https://user-images.githubusercontent.com/65381453/132949641-ad15ac4a-e45b-44ee-8063-6f9a7d81a909.png)

base64 decode



```
GZHPGS{Q3y_M3_Q4574z_E4s70_W4a_U4z_O1_Q3y0_W4a_Pu00a_X0a4z}
```

see , but it's not the correct form of flag.

#### DO u Know rot13 ?


