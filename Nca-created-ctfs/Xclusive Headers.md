
This challenge was made for the CTF which was organised by our team
**NCA@Nepal**. This challenge was a **Forensics challenge** where the players were given the **PCAP** file with the various images of clues and the scene behind the challenge.

%% Here should be link for the challenge or the file of the challenge %%

Well, to solve this challenge players were needed to go through 2 challenge firstly, analyse the challenge which was given using **Wireshark** which will show us the packets. After launching the Wireshark and analyzing some of the packet we can see 2 kind of header, as the name says **( Xclusive headers)** there are something to 
do with the headers. 

![[Pasted image 20240927180527.png]]

There are 2 kind of headers 
1- X-Header :
2- X-Special-Header:

So, there is something suspicious in both headers what needed to be done was players needed to do this ```strings Chal.pcap | grep "X-Special-Header:"```
because as it says **Special** it will give output like this.
![[Pasted image 20240927181832.png]]
Well, there are many thing which is encoded in come kind of ciphers but there was really something suspicious in those ciphers those were this `{}` why there was 2 cipher code inside `{}` that was the suspicious part of the output. So, what should be doing that we need to decode that code inside the `{}` `9EEADi^^3:E]` & `=J^b|!h|sf` this code was encoded using the **ROT 47** so, we need to decode the code i prefer to use `https://gchq.github.io/CyberChef/` to decode the ciphers.

![[3.png]]

After decoding the cipher what we get the shorten link `https://bit.ly/3MP9MD7` which will lead us to some raw picture which is hosted in github. The image which the link leads us is this.
![[4.png]]
Well, now after we get the image what we have to do is download the image and we have to extract it because the flag is embed in the image which is given to the players. Well i prefer `Steghide` to extract the image file but there is a problem with it. While extracting the image it ask for the passphrase but we don't know the passphrase. So, what we can see is in the image which is provided in the zip file of the scene there is something mention in the conversation.
![[Pasted image 20241001195810.png]]
It says `"ROCKYOU"` so, we need to brute force the passphrase in the image file. What i like to use is `Stegseek` which is one of the best in terms of brute force the passphrase. 

![[5.png]]

After using the `Stegseek` using this command  `stegseek background.jpg /path/to/your/wordlist` after running the tool for brute force we can see the passphrase is found which is `/ivancito65/`.
So, after the passphrase is found it also gives us the extracted file of the image in where i hided the flag which was this.

![[7.png]]

Flag : `NCA{y4y_y0u_f0und_7the_F14g}`
