# 1. Binary Search
## Solution
This is the first time I've done a binary search, so I followed [This guide](https://www.youtube.com/watch?v=0qzEqPWw6Oc)
### Using floor division
Repeat the following until you've finished the 10 guesses:
- Formula: 
$$
low end + high end/(FloorDivideBy)2
$$
	- Floor division = Truncate the decimal off of the answer
### Process during CTF
*Keep in mind that the binary to guess changes each time this activity is instanced, so the process won't be the same the next time*
What to do when higher vs lower is returned:
- Higher: First number in formula is replaced
- Lower: second number in formula is replaced

[1-1000] 1+10000 / 2 = 500
- Returned: Lower
[1-500] 1+500 / 2 =  250
- Returned: Higher
[250-500 ]250+500 / 2 = 375
- Returned: Lower
[250-375] 250+375 / 2 = 312
- Returned: Lower
[250-312] 250+312 / 2 = 281
- Returned: Lower
[250-281] 250+281 / 2 = 265
- Returned: Higher
[265-281] 265+281 /  2 = 273
- Returned: Lower
[265-273] 265+273 / 2 = 269
- Returned: Lower
[265-269] 265+269 / 2 = 267

# 2. heap0
## Problems
The webshell gave me some choices (2-5), but I didn't know that I actually had to type the # option of the choice and press enter. At first I just entered 'print' which exited me from the server?
## Solution
The current state of the heap is:
Heap State:
+-------------+----------------+
[\*] Address   ->   Heap Data   
+-------------+----------------+
[\*]   0x624fe5a652b0  ->   pico
+-------------+----------------+
[\*]   0x624fe5a652d0  ->   bico
+-------------+----------------+

The goal is to write into the heap
1. Choice 2 (write to buffer)
	- Enter your own text by overflowing the buffer (can type a bunch of As)
2. (optional) Confirm that the heap has been written into by entering the 1st choice (Print Heap)
3. Choice 4 (Print Flag)
# 3. Super SSH
## Solution
1. Start instance with:
```
ssh -p 61166 ctf-player@titan.picoctf.net
```
2. Enter password 1ad5be0d
# 4. Time Machine
There's a false positive on VirusTotal for the zip file, but I used https://www.browserling.com/ just in case to open the zip file in a VM
## Solution
### Method 1
1. Unzip the zip file
2. Go into the folder
3. Find the commit file & open it in the notepad (key is here)
### Method 2
1. Use:
```
git log
