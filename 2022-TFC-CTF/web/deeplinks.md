# Deeplinks

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/deeplinks-1.png">

When we navigate to the given website we see the following page:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/deeplinks-2.png">

Since there is nothing in source code, such as hidden comments, etc. We approach content brute force with common.txt wordlist:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/deeplinks-3.png">

We see interesting paths such as .well-known/apple-app-site-association. When we open it up in a browser we are prompted to save the file. After we read the file that we have downloaded we can see the flag in JSON format:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/deeplinks-4.png">
