# Pong

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pong-1.png">

When we open the website we get the following page:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pong-2.png">

Clearly indicates that it is OS Command Injection, let’s try with whoami command:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pong-3.png">

If we list the root folder we can spot the flag.txt

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pong-4.png">

All we have to do is to read the file now:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pong-5.png">
