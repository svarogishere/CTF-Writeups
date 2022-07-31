# Pattern 

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pattern-1.png">

So we got this main.py file as well as nc connection to the binary itself, if we connect to the binary we have two choices.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pattern-2.png">

Basically, we multiple the first pattern as many times, but clearly this wont get us far, so let’s analyze main.py.

https://github.com/swarogisreal/CTF-Writeups/blob/c3ca40560171d4345af2b1755e22757d37a856b7/2022-TFC-CTF/code/pattern-main.py#L1-L32

There is an interesting part of the code here and that is the python format string, I believe that we can manipulate the message class to retrieve the flag via this functionality. What helped me to better understand how I can exploit Python format string functionality is the following article: 
<br>
https://lucumr.pocoo.org/2016/12/29/careful-with-str-format/ 
<br>
So the payload that we need to construct in order to retrieve the flag is the following: 
<br><br>
{message.__str__.__globals__[FLAG]}
<br><br>
Message part is the Message Class, __str__ as well as __globals__ to access global variables and retrieve the flag. And Voila! We got it!

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pattern-3.png">
