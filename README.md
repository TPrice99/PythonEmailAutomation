<h1>Python Email Automation</h1>


<h2>Description</h2>
Project will deminstrate how to use Python to send an automated email. I will be using Pycharm to write my python code.
<br />

<h2>Languages and Utilities Used</h2>

- <b>Python</b>

<h2>Environments Used </h2>

- <b>Pycharm - Download: https://www.jetbrains.com/pycharm/</b>

<h2>Program walk-through:</h2>

<p align="center">
You will need access to 2 gmail accounts for this program to work. You will need a sender email and a receiver email. <br/>
<br/>
On the sending email account. You will need to go to your Google Account settings then go to security. Near the 2 factor authenication section you will see a tab called App Passwords. You will click it. <br/>
<img src="https://i.imgur.com/qCoiSKx.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
Then select the other option and put the name as python. <br/>
<img src="https://i.imgur.com/HO5IeFr.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
It will then pop up an app password that will be used in the python code. You should write it down or copy it to notepad. <br/>
<img src="https://i.imgur.com/bPEs2qF.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>

Now it's time to use python to send an email. Here is the python code that I used: <br/> <br/>


```diff 
import smtplib
import ssl
from email.message import EmailMessage

subject = "Email From Python"
body = "This is a test from Python"
receiver_email = "RECEIVER EMAIL"
sender_email = "SENDER EMAIL"
password = "APP PASSWORD"

message = EmailMessage()
message["From"] = sender_email
message["To"] = receiver_email
message["Subject"] = subject
message.set_content(body)

context = ssl.create_default_context()

with smtplib.SMTP_SSL("smtp.gmail.com", 465, context=context) as server:
    server.login(sender_email, password)
    server.sendmail(sender_email, receiver_email, message.as_string())
```
<br/>
<br/>
You should receive an email that looks something like this.  <br/>
<img src="https://i.imgur.com/h6v21sx.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Thank you for checking this out. Let me know if you have any issues and I'll try to help.<br/>
