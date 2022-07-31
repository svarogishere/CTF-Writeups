# DISCORD SHENANIGANS V2

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/discord-1.png">

Well as the challenge says we are going to spam a lot discord bot for this. So I tried /flag in bot-commands channel:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/discord-2.png">

I do not get much from it so the next step was to DM the bot directly. Since he want’s us to be polite I used the following command /flag please

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/discord-3.png">

This is decent hint. I realized that I Have to exfiltrate something so it must be an image right? Well another perfect hint came by in the #announcement channel

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/discord-4.png">

So let’s check images. First I stumbled upon the GIF image, clearly checking it through exiftools did not reveal any flag. But the next image that is kinda easy to skip is this one

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/discord-5.png">

So let’s download the image (with text current status) and upload it to any exiftool online, in my case: https://jimpl.com/ 
<br>
And Voila! Here is our flag!

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/discord-6.png">
