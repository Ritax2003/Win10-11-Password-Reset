# Win10/11/8 Login Password Reset
## A guide to help you reset your windows 10/11/8 login password in case you have forgotten it. Not intended for unethical use.
![#f03c15](https://placehold.co/15x15/f03c15/f03c15.png) `Disclaimer : Do it at your on risk. Although risk of bricking /damaging system by this process is very low, but just in case. I will not be responsible for any damage occured to your system.`

![#c5f015](https://placehold.co/15x15/c5f015/c5f015.png) `Imagine the scenario : you woke up in morning, opened your laptop/pc after getting ready for study/work. And bam!. You have forgotten login password or the fingerprint sensor in laptop is not detecting your finger. 
Exactly this situation has happened to me. I have an ASUS vivobook with fingerprint sensor and i use fingerprint to login for daily use, so i don't need to remember the password/pin. One day, a glitch occured and my fingerprint was not being detected by my laptop. and this was just before my exam too. Panic ensues!!`

![#1589F0](https://placehold.co/15x15/1589F0/1589F0.png) `So how to do it?`

1. Restart multiple times by holding the power key until you see this screen : <br>
![image](https://github.com/user-attachments/assets/f3f77419-0e15-45a6-8cca-e7a81417fc35) <br>
<code>it will show the message "Please wait, diagnosing your pc.."</code>
2. Go to <code>Advanced Options</code> <br>
![image](https://github.com/user-attachments/assets/6c3e5833-ee8a-4860-9915-59e8e78eb7f2) <br>
3. Go to <code>Troubleshoot -> Command Prompt</code> <br>
![image](https://github.com/user-attachments/assets/f1bcb6f1-2020-4009-90da-95fb78fbe74a) <br>
4. Now in this step, you can get stuck.<br>
![image](https://github.com/user-attachments/assets/874e4ec9-c6aa-430b-82cd-9fa7a79c8c74) <br>
   <table>
     <tr>
       <td>Asking for Bitlocker Encryption Key (option 1)</td>
       <td>Asking, but option 1 failed (Option 2) [This is more advnced option]</td>
     </tr>
     <tr>
       <td>
          Go to : <a href="https://aka.ms/myrecoverykey"> Microsoft Account </a> <br>
          Type the recovery key found here, Drive type should be "OSV". This means the drive is used as OS Volume , where os is installed.
       </td>
       <td>
          This requires you to have any recovery media (can be of another pc, or can be of windows 8/10/11 - needed only to trigger the CMD.)
          <ol>
          <li>Connect the recovery media to pc.</li> 
          <li>Go to BIOS/UEFI and change the boot priority, with the recovery media set as the topmost priority.</li>
          <li>Start PC after saving the BIOS.</li>
          <li>
              <img src="https://github.com/user-attachments/assets/68733f1f-fcb0-47a0-847a-a86679624cab"> <br>
             When Windows installer screen comes , press <code>Shift + F10</code> to open CMD.</li>
          </ol>
       </td>
     </tr>
   </table>
5. Type <code>regedit</code> to open the registry editor.
6. Click on <code>HKEY_LOCAL_MACHINE</code> <br>
![image](https://github.com/user-attachments/assets/b004af4e-a1d4-4a1a-9724-250deac7715e)<br>
7. Click on <code>File</code>, then click<code>Load Hive</code> <br>
![image](https://github.com/user-attachments/assets/49f1ae78-8ade-47a3-bac8-1811d8fd0852)
8. Click on <code>This PC</code> , then select the drive where OS is (sometimes C: will not be shown, select the OS drive by checking the size or content)<br>
![image](https://github.com/user-attachments/assets/117bb0e6-6acc-4503-bab2-3ce10737d7c7)
9. Click on <code>Windows</code>, then <code>System32</code> then <code>Config</code> then double click on <code>System</code>.
10. Type <code>KeyName</code> as <code>1234</code>.
11. Then go to <code>HKEY_LOCAL_MACHINE</code> then goto <code>1234</code>.
12. Go to <code>Setup</code>
13. On the Right side, you will see <code>CMDLINE</code>. double click on it and change the value to <code>cmd.exe</code>.
14. On the same right side, check for <code>SetupType</code>. double click on it and change the value <code>data</code> to 2. The data should be enteres in Hexadecimal mode.<br>
![image](https://github.com/user-attachments/assets/b2c7ef41-e85b-4022-96a4-988ff4e68d0a)
15. Now in the left side, click on <code>1234</code>, and go to <code>FILE</code> and click <code>Unload Hive</code>.
16. Now Close the registry editor , then either exit CMD by typing <code>exit</code> in CMD and pressing enter or just closing the window. For those using recovery media approach (option 2), cancel the windows installation.
17. #### IF using recovery media approach, you can reorder the boot order to what it was before. (Before doing the reboot).
18. Reboot the PC, in next restart CMD will open by default.
19. type <code>net user</code>. and press enter.<br>
![image](https://github.com/user-attachments/assets/ad2f87c5-bb70-4363-a3f6-5a9c7b3fbaa5)

20. type <code>net user (account name) *</code> and enter. in space of account name, type your account name you have found from step 19. REMOVE THE BRACES.<br>
![image](https://github.com/user-attachments/assets/af8c6ea9-1772-403f-a4e2-2c2796dde0c3)
21. Type a password : don't type anything , just press enter.
22. Retype/Confirm : don't type anything , just press enter.
23. #### IF YOUR NAME HAS SPACE IN IT LIKE "ANDREW JONES" :
    type as : 1. net user "ANDREWJONES" *
                          or
              2. net user "ANDREW JONES" * .
24. Exit CMD by typing <code>exit</code> in CMD and pressing enter .
25. ![#f03c15](https://placehold.co/15x15/f03c15/f03c15.png) `Now windows will open without asking any password., HOWEVER, YOU WILL BE LOGOUT OF ALL ACCOUNT, ALL OF YOUR GMAIL ACCOUNT WILL BE REMOVED FROM PC, YOU HAVE TO LOGIN IN ALL ACCOUNT FROM START`
26. AND PLEASE. REMEMBER THE NEW PIN/PASSWORD FROM NOW ON.



