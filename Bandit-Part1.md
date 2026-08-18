My Journey Through OverTheWire Bandit (Part 1)
INTRODUCTION - 
At the beginning of my journey, I didn’t know anything about cybersecurity. I used AI to research the field and build a roadmap, which highly recommended starting with OverTheWire's Bandit wargame. Honestly, when I first opened the site, it filled me with a sense of terror. I knew something heavy was coming, and at the time, my Linux knowledge was limited to just ls, cd, and cat.
Eventually, I learned how Bandit works: you have to solve each level using the links and man pages provided in the instructions. Your task is to use those commands to solve the puzzle and retrieve the password for the next level (pro-tip: always store your passwords in a text file so you can go back to older levels if needed!).
I wrote my own step-by-step guides as I played, but I won’t be posting them here. There are already hundreds of sites where you can get the direct answers. Instead, in this first post, I want to share the core concepts, the challenges I faced, and my approach to solving the first 15 levels.

Section 1:The Basics
The Basics (Levels 0-4) The very first level was overwhelming, and trying to understand SSH was eating my brain. I took full help from AI to solve it initially, but I made sure to actually learn what the tool does. I now know it very well—it is the standard protocol used to get secure remote access to another computer over the internet.
After getting over that initial hurdle, Levels 1 through 4 were pretty easy. They mostly focused on advanced uses of the cat command, like figuring out how to read hidden files or files with spaces in their names without confusing the terminal.

Section 2:Searching for files
This section actually didn't feel very tough. It was mostly about going through the provided links and reading parts of the documentation needed to solve the level. The hardest part was figuring out how to find the exact terminologies and flags to sort the search properly. Once I understood how to read the documentation, I was able to use the find command to query the entire server for a file based on its exact byte size and owner. I also learned a crucial trick: adding 2>/dev/null to the end of my search to throw all the annoying "Permission Denied" errors into a black hole!

Section 3: Text Manipulation
While the previous section was about finding files, this section was about finding a needle in a haystack of text. The core strategy remained the same—reading documentation to find the right flags—but the real game-changer here was learning how to use the Linux Pipeline (|). Instead of running one command at a time, I learned how to chain them together like an assembly line. For example, by piping the output of sort directly into uniq -u, I was able to instantly extract the single unique password out of a massive text file.

Section 4: Decoding and Decompression
he first level in this section (Base64 decoding) was relatively easy. However, the second level was tough. I didn’t understand how to implement the tr tool for the ROT13 cipher at first. I used AI to break down the command so I could understand exactly how each part of the solution was working.
The third level was even tougher. I was faced with a massive hex dump and had no idea what was going on until I took a step back to research. I learned what a hex dump is, and studied the differences between decompression tools like tar, bzip2, and gzip (including how they differ in speed and safety). Once I understood what the tools actually did, the level became pretty easy. I reversed the hex dump and repeatedly decompressed the files like a Russian Nesting Doll until I found the password!
Section 5 : Networking Basics
n this section, I was introduced to SSH keys. I learned how, instead of always typing a password to connect to a server, I can authenticate securely using a private key file. I learned how to pass that file into my connection command (ssh -i privatekey.ssh) and used it to successfully log into the next level.
In the final level of this block, I learned about Netcat (nc). I used it to build a two-way connection to an open port on the server. By sending my current level's password through that connection, the server responded by giving me the password for the next level!

What’s next?
Up until this point, I was mostly just learning how to work with files. But the later levels surprised me by introducing much more complex terms and advanced topics. Some of those levels genuinely made me rethink my approach. It was tough, but I pushed ahead. I will share the story of how I overcame those advanced hurdles in my next blog post.
