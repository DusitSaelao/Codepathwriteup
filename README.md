# Codepathwriteup
## Codepath Extra Credit: CTF WriteUp 
RL88 on the BangNull discord server left a file and hint for members to solve.  The file contained a string of letters and numbers, in upper and lower case.  The hint was, “I encoded the flag in base64 15 times and got the attached in the text file. Find the flag. Do not decode manually. Try to do this through terminal or cyberchef. (Note: 15 times is something that you could do by hand. But the number of times can be increased to a really high number and you could be forced to perform the operation through the terminal.)”

1. Seeing that the flag was encoded, my mind first went to what the encoding might be.  When trying to determine what encoding I am dealing with, I try to take note of what characters that are present or not present.  Does the string have just letters or a combination of numbers, letters, and special characters?  Take notice of things like special characters or capitalization.  Luckily, the format of the encoding and *hint* made it obvious that it was base64.
2. Since the hint included the tools I *could use* (terminal or cyberchef), I decided to go with **cyberchef**.
3. Last step was just a matter of determining how many times the flag was encoded.  Cyberchef *agreed* that it was encoded in base64 and by clicking on the “wand” button, it began to add “from base64” to the recipe. The *hint* confirmed it was encoded 15 times. I added “convert to base64” fifteen times, it worked!

![NCL Challenge](/ncl.JPG)
________________________________________________

CVE: 2015-3440

By using JavaScript in the comments, an attacker can inject a script that is executed when the comment is viewed.  The comment had to be larger than 64kb to overflow the buffer and run.

Leave a comment to bypass the initial moderation.  Once the admin approves that comment, the subsequent comments left are also approved.
Creating a script with 64kb of “A” was a little bit of a challenge.  I started by opening a notepad and using the col count to create 1100 “A”s, which I trippled to get 3300, then I doubled that to get 6600.  The last step was to multiply that by ten to get 66,000 A’s.
The comment with the script is as follows -
<a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAA64kbAA
'></a>
I entered the script into the comment and got this -
![CVE2015-3440](/wordpressbroke.JPG)
