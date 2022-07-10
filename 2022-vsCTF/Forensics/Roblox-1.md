# Roblox 1

As challenge says.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/roblox1-1.png"/>

So we download both disc image files. The program (FTK Imager) that I have used to mount the disc image and analyze file system that it contains can be downloaded on the following link: https://www.exterro.com/ftk-imager <br><br>
After usual installation start the program, go to the top bar and select File --> Add Evidence Item. <br><br>
Select Image File and add both roblox.ad1 and roblox.ad2. After which you will mount disc images.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/roblox1-2.png"/>

After that we perform quick search on google, we can generally find out where the Roblox logs and information is stored C:\Users\(Your Windows Username)\AppData\Local. So we navigate to the following directory: C:\Users\adminbot6000\AppData\Local\Roblox\logs\archive <br>

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/roblox1-3.png"/>

Open up the following log from a PrtScr.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/roblox1-4.png"/>

And simply search for username.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/roblox1-5.png"/>

You can see the username “ftcsvisgreat”. So we got the flag vstcf{ftcsvisgreat}.
