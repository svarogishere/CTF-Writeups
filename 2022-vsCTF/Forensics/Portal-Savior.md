As the challenge says:
<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-1.png"/>

We need to find the hidden message in a file “mayday” <br>
After downloading the file we try to determine it’s file type.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-2.png"/>

ASCII, nothing special, let’s try to read it.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-3.png"/>

Now we see that the file is actually some ancient image file format, and of course our best friend now is google. Now we can see a very interesting website that contains binaries and useful information regarding this Picture Format. URL: http://portalwiki.asshatter.org/index.php/Aperture_Image_Format.html 

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-4.png"/>

After reading through the website and learning a bit more about APF files in general, we can see that there are three programs that can be used in order to view this image.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-5.png"/>

In my case I have used the Method 1 or the binary written in QBASIC, running in DOS. Downloaded the binary and unzip-ed it as usual. Now time to start the binary and see briefly how it works.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-6.png"/>

We open it up and we can see that we can switch between two images. With two options 1 (for the next image) and 9 (to exit).

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-7.png"/>
<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-8.png"/>

After further reading we can see that the Images are stored in the DATA folder where the binary exists. So we shall try to edit our “mayday” file naming it exactly as it is the name of one of the files in a DATA folder in order to try and view in in a given binary. So rename “mayday” file to “APERTURE.APF” and put in a DATA folder replacing the old file. After that run the binary again.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-9.png"/>

The good thing is that your file opened, but the bad thing is that it most likely requires some modification. Comparing the old deleted APERTURE.APF with our downloaded mayday file we can notice the difference.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-10.png"/>

It seems that our binary cares greatly about line endings, let’s try to remove extra lines and format the first 6 lines of our file as they are in a file “APERTURE.APF”.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-11.png"/>

Rename our mayday file again to “APERTURE.APF” and copy it (actually replace it with already existing one) to DATA folder. Run the binary.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-vsCTF/Images/portal-savior-12.png"/>

Voila! We got the flag 😊
