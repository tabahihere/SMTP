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
