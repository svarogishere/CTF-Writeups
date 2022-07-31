# Are you the Admin?

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/are-you-the-admin-1.png">

So we have the following website with three files which turns out to be source code of the web app.
<br>
If we open a web app and try to create test users we get the following output:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/are-you-the-admin-2.png">

Okay let’s analyze the source code. As we can see this code functionality from file index.tsx is responsible for creating the user. We have only one option to create a username, but what if we can also input admin username and manipulate the isAdmin key to be true in order to reveal the flag?

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/are-you-the-admin-3.png">

If we analyze another file schema.prisma we can see that there is a syntax or JSON query that is accessing SQLite DB. There we see that we can format following JSON payload and try to create admin username.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/are-you-the-admin-4.png">

If we intercept the create functionality from web app with ZAP we can see that HTTP POST request is sent in JSON format.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/are-you-the-admin-5.png">

Let’s try to manipulate this with the following payload:

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/are-you-the-admin-6.png">

If we send the request we will see the 200 status code indicate that it passed through, lets navigate to web app and refresh the page. And Voila! We got the flag!

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/are-you-the-admin-7.png">
