# Calendar

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/calendar-1.png">

Okay let’s navigate to the website, as we can see it is a WordPress website so clearly our best friend is wpscan for sure.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/calendar-2.png">

Let’s run wpscan with the following command to enumerate pretty much everything:
<br><br>
wpscan --api-token <api-token> -e --url http://01.linux.challenges.ctf.thefewchosen.com:56916/
<br><br>
What is interesting is that there are quite a few vulnerabilities tied to the Calendar plugin, some of them are rabbit holes such as CVE-2021-24946 dumped whole DB for nothing. But what we aim for is this one CVE-2021-24147.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/calendar-3.png">

Let’s research for public exploits. Which can be found on the following link: https://wpscan.com/vulnerability/c7b1ebd6-3050-4725-9c87-0ea525f8fecc 

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/calendar-4.png">

Let’s append this path to our target website. And save it as XML.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/calendar-5.png">

Open up the downloaded XML file and Voila! Here is the password we need for our flag!

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/calendar-6.png">
