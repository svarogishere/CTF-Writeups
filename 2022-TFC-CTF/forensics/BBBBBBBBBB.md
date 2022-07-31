# BBBBBBBBBB

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/BBBBBBBBBB-1.png">

So we download the image and if we try to open it we will not be able to. 

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/BBBBBBBBBB-2.png">

Let’s open this file in hexeditor or in my case even notepad++ would do the trick and notice that there are a bunch of BBBBBBBBBB in a file which is actually bad strings:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/BBBBBBBBBB-3.png">

Remove all BBBBBBBBBB strings from a file with find and replace or in any hex editor. Save it. Now you can open the image and get the flag.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/BBBBBBBBBB-4.png">
