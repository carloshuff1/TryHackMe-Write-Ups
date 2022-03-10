https://tryhackme.com/room/investigatingwindows

Question 1. Whats the version and year of the windows machine?

*You can quickly find this information through the systeminfo command in windows command prompt.

    Answer: Windows server 2016

Question 2. Which user logged in last?

    Answer: administrator

Question 3. When did John log onto the system last?

*The "Net User" command can be used to find the last logon. You can also find this through searching through the security events in event viewer.

    Answer: 03/02/2019 5:48:32 PM

Question 4. What IP does the system connect to when it first starts?

*HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run is a registry key that is commonly used to posr exploitation to maintain persistence on a machine. When checking that path in the box you can see a entry that says "C:\TMP\p.exe -s \\10.34.2.3 'net user' > C:\TMP\o2.txt

    Answer:10.34.2.3

Question 5. What two accounts had administrative privileges (other than the Administrator user)?

*Opening the Local Users and Groups program with "lusrmgr.msc" you can see Guest and Jenny under the Administrators members. 

    Answer: Jenny, Guest

Question 6. Whats the name of the scheduled task that is malicous.

*Under the actions of Clean File System it runs a powershell file named nc.ps1 and listens on port 1348. This is not normal activity.

    Answer:Clean file system

Question 7. What file was the task trying to run daily?

    Answer: nc.ps1

Question 8. What port did this file listen locally for?

    Answer: 1348

Question 9. When did Jenny last logon?

*Net user jenny

    Answer: never

Question 10. At what date did the compromise take place?

Answer format: MM/DD/YY

    Answer: 03/02/2019

Question 11. At what time did Windows first assign special privileges to a new logon?

Answer format: MM/DD/YYYY HH:MM:SS AM/PM

    Answer: 03/02/2019 4:04:49 PM

Question 12. What tool was used to get Windows passwords?

*Under the "GameOver" task you can see that it runs "mim.exe" and uses sekurlsa::logonpasswords which is a common IOC for mimikatz.

    Answer: Mimikatz

Question 13. What was the attackers external control and command servers IP?

    Answer: 76.32.97.132

Question 14. What was the extension name of the shell uploaded via the servers website?

    Answer: .jsp

Question 15. What was the last port the attacker opened?

    Answer: 1337

Question 16. Check for DNS poisoning, what site was targeted?

*You can check for DNS poisoning by navigating to the hosts file. There you can see they assigned a malicious IP to google.com (76.32.97.132 instead of 8.8.8.8)

    Answer: google.com
