# Random

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pwn-1.png">

So let’s download the binary and check which type it is:
<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pwn-2.png">

Great, usual ELF 64-bit, lets analyze it with Ghidra, after opening up the file I have gone after searching the generate string among the given code, I eventually opened up the main function where we can investigate what the code does.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pwn-3.png">

Notice the hex code that I have highlighted above. Since when we run the program we are prompted to choose to generate number with 1 as only option, anything else will fail us.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pwn-4.png">

But we will not get far with this approach, buffer overflow is non existing, cuz only one input as a number is accepted which we can state because of %d format specifier. There is very interesting else if option after the first one, we have the following hex code 0x539 which when we translate into decimal we get the number 1337, also after this else if conditional statement we can see if our input is equal to this number we will print out the flag. And that is exactly what happens.

<img src="https://github.com/swarogisreal/CTF-Writeups/blob/main/2022-TFC-CTF/images/pwn-5.png">
