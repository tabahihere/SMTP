# SMTP

# Mail Transfer Agent- MTA

  - names: mail relay, mail router, Internet mailer, most common MTA.
  - MTA: mail transfer agent, a message transfer agent, or a mail transport agent.
  - MUA: an email client – an app you use to handle the email-related stuff. 


## **What is an MTA?**

A mail/message transfer agent (MTA) is a software that transfers emails between the computers of a sender and a recipient. 

- MTA receives an email from the mail/message submission agent (MSA).
- MSA receives it from the mail user agent (MUA).
- Once the MTA gets the email, relaying comes into play. are often called mail relays.
- Then it hits the mail delivery agent (MDA).
- The email sending is carried out using SMTP (or extended SMTP), and for the final stage (MDA to MUA), POP3 or IMAP4 is used. For more on differences between these    email protocols, read SMTP vs. IMAP vs. POP3. 

![image](https://user-images.githubusercontent.com/73932937/116781191-0d9f5580-aa9f-11eb-85d0-18886acab81d.png)



## MTAs do the following:

- accept emails sent from mail user agents
- query the MX records and select a mail server to transfer emails
- send auto-response messages if an email has failed to reach the destination

## Mail queueing in MTAs:

- use a store-and-forward model of mail handling.
- Outgoing mail is put into a queue and waits for the recipient’s server response.
- If the mail fails to be delivered during the established term, it will be returned to the mail client.

### Three major factors that email deliverability is based on: 
1. **sender’s reputation**

	reputation of the domain and IP address, if untrustworthy, all emails from it will end up in the spam folder, or even bounced back, for new MTP slowly increase     sending capacity, receiving domain sets its limits on incoming mail if it is exceeded sending mail server may be identified as untrustworthy so you can set         dynamically limit sending.
	blacklist is a common issue with the sender’s reputation.

2. **infrastructure & authentication**
   
3. **content**

## On-premise MTA vs. cloud-based SMTP relay – which is better?

### An on-premise MTA:
set up according to your requirements. 

_Pros:_

- You can manage every aspect of email sending configurations
- Improved dependability 
- Integrability with inhouse tools and software
- Connectability of the email marketing infrastructure with inhouse data sources 
- No or almost no limitations by APIs or web hook restrictions
- Capability to send tons of emails without any delays or other speed pains 
- Full control of the email sending configuration

_Cons:_

- On premise MTAs are expensive. Pricing starts with $6K for installation, configuration, and IP warmup
- You need space to accommodate hardware
- Setting up is time consuming (approx. 3 months)
- You bear full responsibility for managing infrastructure and the security the email database.
- Not easy to scale


# Simple Mail Transfer Protocol

**Ref:**
https://medium.com/@jonathansychan/smtp-simple-mail-transfer-protocol-ed443b1f51d7
https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/


  SMTP is part of the application layer of the TCP/IP protocol. Using a process called “store and forward,” SMTP moves your email on and across networks. It works closely with something called the Mail Transfer Agent (MTA) to send your communication to the right computer and email inbox.


- Application layer protocol.
- A connection-oriented text-based protocol.
- SMTP servers commonly use TCP on port 25. Email Message Submission is often sent on port 587.

![image](https://user-images.githubusercontent.com/73932937/116781246-5f47e000-aa9f-11eb-91aa-eb1820bc2dfc.png)


## THE 6 MAIN STEPS of SMTP (protocol):

1. Email is submitted by a MUA to a mail server’s MSA (message submission agent)
2. The message is transferred to the server’s MTA (the MTA and MSA are usually hosted on the same SMTP server)
3. The MTA checks the MX record of the recipient domain and transfers the message to another MTA (this step can occur multiple times until the message is received 	by the proper receiving server)
4. The message is handed off to the MDA, which saves messages in the proper format for retrieval by the receiving MUA
5. The receiving MUA requests the message from the MDA (usually with POP3 or IMAP)
6. The message is delivered to the receiving MUA‘s inbox


## Working of SMTP

### Composition of Mail:

A user sends an e-mail by composing an electronic mail message using a Mail User Agent (MUA). Mail User Agent is a program which is used to send and receive mail. The message contains two parts: body and header. The body is the main part of the message while the header includes information such as the sender and recipient address. The header also includes descriptive information such as the subject of the message. In this case, the message body is like a letter and header is like an envelope that contains the recipient's address.
Submission of Mail:
 After composing an email, the mail client then submits the completed e-mail to the SMTP server by using SMTP on TCP port 25.

### Delivery of Mail: 

E-mail addresses contain two parts: username of the recipient and domain name. For example, vivek@gmail.com, where "vivek" is the username of the recipient and "gmail.com" is the domain name.
If the domain name of the recipient's email address is different from the sender's domain name, then MSA will send the mail to the Mail Transfer Agent (MTA). To relay the email, the MTA will find the target domain. It checks the MX record from Domain Name System to obtain the target domain. The MX record contains the domain name and IP address of the recipient's domain. Once the record is located, MTA connects to the exchange server to relay the message.

### Receipt and Processing of Mail: 

Once the incoming message is received, the exchange server delivers it to the incoming server (Mail Delivery Agent) which stores the e-mail where it waits for the user to retrieve it.

### Access and Retrieval of Mail: 

The stored email in MDA can be retrieved by using MUA (Mail User Agent). MUA can be accessed by using login and password

