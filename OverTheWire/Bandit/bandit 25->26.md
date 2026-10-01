ok so im doing this one first cuz it kind of baffled the first time id done it.
i was planning on finishing everything first THEN documenting them but i HAVE to share this one.

ok so, assuming you solved the previous level, youll have private ssh key which you can use. sweet! easy right? lets try!
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/97b6be7a-da0e-484a-95d2-a90b8e9883c6" />
"alright, sweet! lets-"
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f649e7e9-632c-4e15-a515-0561e4388008" />
"umm. that can't be right. lets try again"
ill save you the hassle; it wont work. 
so, we're basically forced into using the previous lab to see what's going on.

if we read the level rules you'll notice it says something about the shell not being a standard bash shell
<img width="1607" height="387" alt="image" src="https://github.com/user-attachments/assets/a53a17ba-03fa-459e-ac27-3c615f34488d" />
to see WHAT kind of shell it is, we need to read the passwd file
<img width="1895" height="150" alt="image" src="https://github.com/user-attachments/assets/c8f898b0-7544-436e-958b-fcc3b012dd5f" />
look, i dont know about you, but I have never seen a showtext shell ever before in my life.
lets see what it contains
<img width="1871" height="182" alt="image" src="https://github.com/user-attachments/assets/8fbc7af1-9bc8-4200-9e75-98856cad5d6b" />
so its a shell script that calls a file called text.txt and exits the shell.
keep in mind how the file is displayed in the script: using more.

alright. so, what now?
now, im not going to act like i knew how to solve this by myself. i legit had no idea. so i searched it up, and apparently the person i found also searched it up and found it from someone else.
so, bear with me: this is going to get weird.

we're going to ssh in again.
"but yousuf, that didn't work last time!"
yeah i know. that's why we'll do a teeeeny tiny change.
<img width="1456" height="126" alt="image" src="https://github.com/user-attachments/assets/787cbd0f-e9c6-4691-be3e-ded6cada3507" />
yyyup. we need to resize the terminal and make it as small as possible.
"but that won't change anything!"
<img width="1461" height="175" alt="image" src="https://github.com/user-attachments/assets/0c0085b6-52ff-4c1f-9785-c8d0a6efdf7d" />
see how we didn't get kicked out? that's a step in the right direction

you might ask how that works? what's different?

more is a pager, meaning it shows a file one screen at a time. normally text.txt is short enough to fit on your screen, so more prints it all and quits right away. and since the login shell basically consists of this one command (it uses exec, so more actually replaces the shell), the moment more quits you're kicked out of the session.

BUT: if the file is too tall for your terminal, more stops after the first screenful and waits for your input. it never quits, so you don't get kicked out, and you get an interactive session we can work with.

"so, what now?"
now we enter vim by simply pressing v and enter vim's command-line mode using :

we can set and enter bash shell through said command mode (keep in mind you will not get an output on the first command)
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b478fbc3-82ff-4845-9e66-9db54612fa24" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d61ceb7d-3324-425c-9cda-65c56b904683" />
we're FINALLY in. now it's just a matter of accessing the passwords in /etc/bandit_pass/bandit26 AND /etc/bandit_pass/bandit27
<img width="811" height="328" alt="image" src="https://github.com/user-attachments/assets/f4b0509f-4a13-427a-8862-b5606fa02fac" />

(for bandit27's password you must use the bandit27-do setuid binary and call for the password)



that's it. we're in! thank you for your time.
