<h1>Investigating with Splunk</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
In this project i will attempt to solve investigating with splunk room on tryhackme
<br />


<h2>Languages and Utilities Used</h2>

- <b>SPL</b> 
- <b>Splunk</b>

<h2>Environments Used </h2>

- <b>Tryhackme</b> (21H2)

<h2>Project walk-through:</h2>

<p align="center">
Questions Page: <br/>
<img src="https://imgur.com/QnNcWbp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Question 1:  <br/>
  For this question the index is main hence the expression index=main to list all event
<img src="https://imgur.com/I4zDPX7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Answer for question 1: <br/>
<img src="https://imgur.com/54r2eBA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
For question 2 i added "Net User" to the search bar as this is the command for adding a new user so for the attacker to create a backdoor user he must have used this command :  <br/>
<img src="https://imgur.com/EHQ2bK9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Answer to Question 2:  <br/>
<img src="https://imgur.com/hkoD1as.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Question 3 Regarding this question as the backdoor user is A1berto i added "registry" to the search bar the registry key path is shown below:  <br/>
<img src="https://imgur.com/mmmGnxn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Answer to question 3:  <br/>
<img src="https://imgur.com/LgBtU6R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Question 4 the SPL expression i used was just index=main and then went ahead to check the users field which we can clearly see the attacker tried to impersonate Alberto:  <br/>
<img src="https://imgur.com/HMctKx6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Answer to question 4:  <br/>
<img src="https://imgur.com/ykBId34.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Answer to question 4:  <br/>
<img src="https://imgur.com/ykBId34.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

For Question 5 i added commandline field to main fields and from the field wnteries we can see the command used to remotely add a backdoor user:  <br/>
<img src="https://imgur.com/ykBId34.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Answer to question 5:  <br/>
<img src="https://imgur.com/6U0rhkR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Commandline entry:  <br/>
<img src="https://imgur.com/nAFhd5c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Answer to question 5:  <br/>
<img src="https://imgur.com/2lHSYfG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

With Question 6 the SPL expression is "index=main A1berto Category=logon" this is because we alrerady know the account is A1berto and 
category=logon is the required frield to get the number of attempts:  <br/>
<img src="https://imgur.com/mJ17UqY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Answer to question 6:  <br/>
<img src="https://imgur.com/epJCrOi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Question 7 to begin with SPL expression is "index=main A1berto" a closer look at the field accountname has James as the only entry
a closer look will give the hostname and to be sure we can see the payload :  <br/>
<img src="https://imgur.com/QAP3BNN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Answer to question 7:  <br/>
<img src="https://imgur.com/46Dfzw4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Question 8 the SPL expression is "index=main eventID=4103" this is because powersehell logging has the eventcode to be4103 as reference in this docment 
https://docs.splunk.com/Documentation/UBA/5.3.0/GetDataIn/AddPowerShell#:~:text=Verifying%20PowerShell%20logging,4688%20and%20Process_Name%20contains%20PowerShell
:  <br/>
<img src="https://imgur.com/ZLIuwTO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Answer to question 8:  <br/>
<img src="https://imgur.com/fI2TsTs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Answer to question 7:  <br/>
<img src="https://imgur.com/46Dfzw4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>




<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
