# INCLUDE WHAT MATTERS

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/include-what-matters-1.png">

Okay let’s open up the web app and see what we got.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/include-what-matters-2.png">

After clicking on Your test link we can conclude that most likely this is an LFI vulnerability.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/include-what-matters-3.png">

Let’s confirm it with /etc/passwd

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/include-what-matters-4.png">

Okay we are limited only to read files that we know of, but since the flag is hidden we will have hard time guessing it. Let’s try to chain it into RCE. What helped me achieve this is the following tweet:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/include-what-matters-5.png">

So all we need to do is first check if we can access logs file, which we can.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/include-what-matters-6.png">

Now let’s intercept request with ZAP or Burp and input the command execution function within the User Agent header.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/include-what-matters-7.png">

Send the request and now let’s try to list all files and directories from root path / by appending the following path to the ZAP or Burp GET Request: ?file=/var/log/apache2/access.log&c=ls /

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/include-what-matters-8.png">

Voila! As we can see the flag is in root folder. Let’s read it by simply putting in the /hidden_fl4g.txt as value in file parameter.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/include-what-matters-9.png">
