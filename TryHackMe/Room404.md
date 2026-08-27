hello there! today im walking you through Room404.

firstly (as always), i use nmap to do basic recon:
<img width="1367" height="756" alt="image" src="https://github.com/user-attachments/assets/9b2ae4bd-08c9-4998-bdf2-40c5a90d76cf" />

ssh and http ports are open. and would you have a look! there's apparently a git repository!

the natural next step is to attempt to curl said repository:
<img width="1888" height="373" alt="image" src="https://github.com/user-attachments/assets/efff9a9e-cbda-47cf-bcee-16f984a59490" />

looks like its vulnerable.

i used the first tool that i met when i searched "git repo dumper" and i found <a href="https://github.com/arthaud/git-dumper">this.</a>

i ran the tool and stored the output in a directory called "dumpedrepo":
<img width="1897" height="765" alt="image" src="https://github.com/user-attachments/assets/9e5ef33e-748a-4eae-a4ab-a8a385ea3e36" />

once that was done, all i had left to do was navigate the dump and find the flag:
<img width="1900" height="212" alt="image" src="https://github.com/user-attachments/assets/ae93ae10-098e-457b-981f-dc7129a1f672" />

tada! that's it, thank you for your time.




