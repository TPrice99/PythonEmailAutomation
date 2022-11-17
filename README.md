<h1>Python Email Automation</h1>


<h2>Description</h2>
Project will deminstrate how to use Python to send an automated email. I will be using Pycharm to write my python code. I also imported emails from an excel spreadsheet.
<br />

<h2>Languages and Utilities Used</h2>

- <b>Python</b>
- <b>Excel</b>

<h2>Environments Used </h2>

- <b>Pycharm - Download: https://www.jetbrains.com/pycharm/</b>

<h2>Program walk-through:</h2>

<p align="center">
You will need access to 2 gmail accounts for this program to work. You will need a sender email and a list receiver emails. <br/>
<br/>
On the sending email account. You will need to go to your Google Account settings then go to security. Near the 2 factor authenication section you will see a tab called App Passwords. You will click it. <br/>
<img src="https://i.imgur.com/qCoiSKx.jpg" height="80%" width="80%"/>
<br/>
<br/>
Then select the other option and put the name as python. <br/>
<img src="https://i.imgur.com/HO5IeFr.jpg" height="80%" width="80%"/>
<br/>
<br/>
It will then pop up an app password that will be used in the python code. You should write it down or copy it to notepad. <br/>
<img src="https://i.imgur.com/bPEs2qF.jpg" height="80%" width="80%"/>
<br/>
<br/>

<br/>
<br/>
Now lets create an email list using excel <br/>
<img src="https://i.imgur.com/N16I9ks.jpg" height="80%" width="80%"/>
<br/>
<br/>    
    
Now it's time to use python to send an email. Here is the python code that I used: 
<br/> 
<br/>


```diff 
import pandas as pd
import smtplib
import ssl
from email.message import EmailMessage

sender_email = "Sender Email"
password = "APP Password"

# establishing connection with gmail
server = smtplib.SMTP_SSL('smtp.gmail.com', 465)
server.login(sender_email, password)

# reading the spreadsheet
email_list = pd.read_excel('FILE LOCATION')

# getting the names and the emails
names = email_list['Name']
emails = email_list['Email']
    
# setting the subject line of the emial
message = EmailMessage()
subject = "Message from python"
message["Subject"] = subject

context = ssl.create_default_context()

# iterate through the records
for i in range(len(emails)):
    # for every record get the name and the email addresses
    name = names[i]
    receiver_email = emails[i]

    # the message to be emailed
    body = "Hello " + str(name) + "YOUR MESSAGE TO SEND OUT"
    message.set_content(body)
    # sending the email
    server.sendmail(sender_email, receiver_email, message.as_string())
    print("sent email to", receiver_email)

# close the smtp server
server.close()
```
<br/>
<br/>
You should receive an email that looks something like this.  <br/>
<img src="https://i.imgur.com/h6v21sx.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Thank you for checking this out. Let me know if you have any issues and I'll try to help.<br/>
