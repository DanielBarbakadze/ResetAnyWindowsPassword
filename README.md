# Here is my solution how to reset password on Windows without knowing it. (It doesn't work if BIOS is locked too)

Use recovery mode or OS installation method (keyboard shortcut for opening command prompt in this case is **SHIFT + F10**) to approach command and open it.
You would see in command prompt:
**x:\Sources>**

*Write:* **x:\Sources>** DISKPART
*Write:* **DISKPART>** list volume
Now you see list of partitions. Find which one stands for Operating System.
for ex: OS is on D (in “Ltr” column)
*Write:* **DISKPART>** cd d:
Now you see list of commands for DISKPART, but at that time you don’t need any of the, but exit.
*Write:* **DISKPART>** exit

*You would see:*
**Leaving Diskpart...
X:\Sources>**

*Write:* **X:\Sources>** d:
The X partition now is changed with D.
*You would see:* **D:\>**
*Write:* **D:\>** cd Windows\System32
*Write:* **D:\Windows\System32>** copy utilman.exe utilman1.exe
*You would see:*
		**1 file(s) copied.**
*Write:* **D:\Windows\System32>** copy cmd.exe cmd1.exe
*You would see this:*
		**1 file(s) copied.**
*Write:* **D:\Windows\System32>** del utilman.exe
*Write:* **D:\Windows\System32>** rename cmd.exe utilman.exe

After that close command prompt and restart the computer.

Whet your computer approach to lock screen window, click the **Utility Manager** icon (between *Internet access* and *Turn Off* icons, right down corner).
This would open command prompt immediately.

*You would see:*
**C:\Windows\system32>**

In terms we are running cmd now as an administrator, we can set passwords.

*Write:* **C:\Windows\system32>** net user 
Choose the target user’s username from printed users list. (For ex: Daniel)
*Write:* **C:\Windows\system32>** net user Daniel pass123 
Note that, you can **write nothing** after username, in this case there will be **no password for this user**.
*Write:* **C:\Windows\system32>** exit

Try to log in using new password.
Enjoy :)

