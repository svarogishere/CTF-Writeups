# Roblox 2

As the challenge says.
<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/Roblox-2-1.png"/>

This one is a bit trickier, but if we follow the simple steps and think a bit creatively, it ends up not being so hard to solve. So since it is obvious that the challenge will not hide the answer to the flag in the same directory as Roblox 1 challenge did, we had to undertake different approach. In case that someone reads this challenge and does not read the Roblox 1 write-up, I will provide programs that I have used to mount .ad1 images.
<br><br>
So we download both disc image files. The program (FTK Imager) that I have used to mount the disc image and analyze file system that it contains can be downloaded on the following link: https://www.exterro.com/ftk-imager 
<br><br>
After usual installation start the program, go to the top bar and select File --> Add Evidence Item.
<br><br>
Select Image File and add both roblox.ad1 and roblox.ad2. After which you will mount disc images.
<br><br>
Since all the games and login sessions regarding Roblox has to go through a Browser, most likely Chrome, I have set my mind on to analyze the History of Chrome in order to find out the activity that user had regarding the Roblox game. 
<br><br>
With simple Google research we can find out that Chrome History is stored on the following path in file system: C:\Users\<username>\AppData\Local\Google\Chrome\User Data\Default. We should navigate to that folder. After a few rabbit holes where I focused on investigation the Chrome history, were there is a tons of games that the user search for (brute forcing the solution is not the point), interesting idea got up in my mind. I have gone after to analyze previous sessions activity, as at first we have to find users alt account. So navigate to the following folder in current directory: Sessions. Open up the Tabs file as the one from the PrtScr. And search for “Username” keyword.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/Roblox-2-2.png"/>

We can see the main account that we already submitted for Roblox 1 challenge, so we must be on a good track, let’s keep searching for other accounts.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/Roblox-2-3.png"/>

And Voila! We got the alt user, even better his login session, after which as usual he started playing some game on Roblox which in this case is the “Theme-Park-Tycoon-2”. So we got the flag vsctf{ themeparktycoon2}.
