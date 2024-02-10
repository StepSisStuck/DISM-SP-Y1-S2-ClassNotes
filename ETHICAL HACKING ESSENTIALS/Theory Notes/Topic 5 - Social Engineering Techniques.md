# Topic 5 - Social Engineering Techniques

# Table of Contents
- [Topic 5 - Social Engineering Techniques](#topic-5---social-engineering-techniques)
- [Table of Contents](#table-of-contents)
- [What is Social Engineering?](#what-is-social-engineering)
  - [Techniques of Social Engineering](#techniques-of-social-engineering)
- [Shoulder Surfing](#shoulder-surfing)
- [Dumpster Diving](#dumpster-diving)
- [Piggybacking](#piggybacking)
- [Types of Social Engineering Attacks](#types-of-social-engineering-attacks)
  - [Viewing Email Headers](#viewing-email-headers)
    - [Example of Email Headers](#example-of-email-headers)
  - [Viewing Email Headers](#viewing-email-headers-1)


---

# What is Social Engineering?

- Using Knowledge of human psychology to manipulate people into revealing confidential information or performing actions
  - Example : An attacker might call an employee and pretend to be a member of the IT department, asking for the employee's password to fix a problem with the network
- Can be the biggest threat to an organization's security
- Most difficult to defend against
- Can be used to gain access to a network, steal information, or spread malware 

## Techniques of Social Engineering
- Urgency
  - "You need to do this now or you will be fired"
- Help with a problem
  - "I'm from IT and I need to fix your computer"
- Everyone else is doing it
  - "All your friends have already given me their passwords"
- Kindness
  - "I'm just trying to help you"
- Authority
  - "I'm from the FBI and I need to ask you some questions"
- Scarcity
  - "I only need your password for a few minutes"
- Fear 
  - "If you don't give me your password, you will be in big trouble"
- Trust
  - "I'm your friend and I need your password to help you"
- Greed
  - "I will give you a lot of money if you give me your password"
- Curiosity
  - "I'm just curious to see what you have on your computer"
- Intimidation
  - "I will hurt you if you don't give me your password"
- Flattery
  - "You are the best employee and I need your password to fix the network"
- Guilt
  - "I'm in trouble and I need your password to fix it"

# Shoulder Surfing

- Watching someone enter their password or PIN
- Can be done in person or by using a camera
- Shoulder surfers may stand close to the victim at an ATM or in a crowded place to see the victim enter their PIN
- Use of cameras to record the victim entering their password increases the risk of shoulder surfing


# Dumpster Diving
- Searching through trash for information
- Can be used to find passwords, credit card numbers, or other confidential information
- Lots of information can be found in the trash
  - Discarded documents - Windows XP manual - the company has upgraded their systems?
  - Company Organizational Chart - Who is the CEO?
  - Printout of Emails
  - Discarded Hard Drives - What data is on the hard drive?
- Documents should be shredded before being thrown away
- Using disk-cleaner software to erase data from hard drives before disposing of them

# Piggybacking

- Trailing an authorized person into a restricted area
- May be done by holding the door open for someone or by following closely behind them
- May be done by pretending to be on the phone or by carrying a large box

- All this can be used to gain access to a building or a secure area

# Types of Social Engineering Attacks
- Phishing
  - Spear Phishing
    - They are targeted at specific individuals or organizations
  - Whaling
    - Targeting high-profile individuals such as CEOs or CFOs
  - Smishing (SMS Phishing)
    - Sending text messages to trick people into revealing personal information
  - Vishing (Voice Phishing)
    - Using the telephone to trick people into revealing personal information
  - Pharming
    - Redirecting a website's traffic to a fake website
  - Watering Hole Attack
    - Attacker observes the websites that the target visits and infects one of those websites with malware
  - Baiting
    - Leaving a malware-infected device in a place where it is likely to be found


## Viewing Email Headers
- Email headers contain information about the sender and the path the email took to reach the recipient
- After viewing the email headers, you can determine if the email is legitimate or if it is a phishing email
- You can open the email headers, copy the information, and paste it into a text editor to view the headers
  - So you can see the path the email took to reach you
- Header information can be used to trace the source of the email
  - Unique identifiers in the header can be used to track the source of the email

### Example of Email Headers
```plaintext
From UOB Cards Marketing Fri May 15 20:28:30 2015
X-Apparently-To: mary@yahoo.com; Fri, 15 May 2015 20:28:36 +0000
Return-Path: <bounced@edm.uob.com.sg>
X-Originating-IP: [203.126.11.71]
Authentication-Results: mta1328.mail.bf1.yahoo.com  from=eDM.uob.com.sg; domainkeys=neutral (no sig);  from=eDM.uob.com.sg; dkim=neutral (no sig)
Received: from 127.0.0.1  (EHLO ntvwlpsg08) (203.126.11.71)
  by mta1328.mail.bf1.yahoo.com with SMTP; Fri, 15 May 2015 20:28:36 +0000
X-TM-IMSS-Message-ID:<291178ac0040454b@uob.com.sg>
Date: Sat, 16 May 2015 04:28:30 +0800
Return-Path: bounced@edm.uob.com.sg
To: mary@yahoo.com
From: UOB Cards Marketing <marketing@eDM.uob.com.sg>
Reply-To: helpme@uobgroup.com
Subject: <ADV>Enjoy 10% off at Sakae Sushi with UOB Cards (ref: 5818)
Message-ID: <59a58ef1a2fa8ee8af87c4aab1dc06a1@localhost.localdomain>
X-Priority: 3
X-Mailer: PHPMailer (phpmailer.sourceforge.net) [version 2.0.0 rc3]
MIME-Version: 1.0
Content-Type: multipart/alternative;
    boundary="b1_59a58ef1a2fa8ee8af87c4aab1dc06a1"
Content-Length: 20467

```
## Viewing Email Headers 
- Information in Email Headers to look out for
- Return-Path
  - The email address to which the email will be returned if it cannot be delivered
- Recepients
  - The email address of the recipient
- Type of Email Service
  - The email service that was used to send the email
- IP Address
  - The IP address of the sender
- Name of the Sender
  - The name of the sender
- Unique Identifiers
  - Unique identifiers in the header can be used to track the source of the email
- Date and Time
  - The date and time the email was sent
- Attachments
  - The email headers can also contain information about attachments
Use whois to find out more about the IP address of the sender




