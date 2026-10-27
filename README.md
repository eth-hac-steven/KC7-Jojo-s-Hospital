# KC7-Jojo-s-Hospital
Jojo's Hospital, a cornerstone of Lexington's healthcare system, faces a critical crisis. The stakes are immense: will the hospital recover its vital services and secure patient data 🏥 or succumb to the paralyzing ransomware attack? 🛡️


KC7-Jojo's Hospital: A Ransomware Investigation
desc: Jojo's Hospital, a cornerstone of Lexington's healthcare system, faces a critical crisis

```
{
  "hire_date": "2022-06-15 00:00:00+00:00",
  "name": "Anthony Davis",
  "user_agent": "Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 5.1; Trident/6.0)",
  "ip_addr": "10.10.0.1",
  "email_addr": "anthony_davis@jojoshospital.org",
  "company_domain": "jojoshospital.org",
  "username": "andavis",
  "role": "Senior IT Administrator",
  "hostname": "AMFB-MACHINE"
}
```
locked byte
2 million
secure-health-access.com


Scenario
JoJo's Hospital in Lexington, Kentucky, recently faced a serious cyberattack that locked their important files. The hackers sent a message to the hospital asking for money to unlock the files. They gave a specific amount of time to pay.

![rasmom-note](ransomnotes.png)

Q1; How many hours did the hackers give the hospital to pay the ransom?

A; 72 hrs

The ransomware group left a bold name at the top of the note.
Q2: What was the name of the ransomware group?
A: Lock byte


The ransomware group had a snarky and mean slogan:
Q: The slogan was: we spend your money, so ____
A: you dont have to 


Not only did the hackers ask the hospital for money, but they also sent scary emails to patients. They asked patients to pay money too, or their personal information would be shared.



Q: How much did the hackers ask the patients to pay?

A:10000

Q: What very important unique identifier number did the ransomware operators threaten to release?

A : Social security number

Q: How many total files were encrypted at the hospital?
A: 6420

Q: How many unique hostnames had files encrypted on them?
A : 321


Q: What was the Sha256 hash of this ransom file?
A: 97c348e95c8a8aeb8808f76434d73a92bbcb6b4586788365762b22624990b018


Q:What was the full path of this ransom file?

A: C:\\Users\\andavis\\Documents\\We_Have_Your_Data_Pay_Up.txt


Q: On how many hosts (machines) was this ransom file seen?
A: 1

This ransom note is a major clue! We can use it to figure out how the ransom might have happened.

What hostname was the ransom note seen on?

AMFB-MACHINE


Great, now that we know what hostname the file was seen on. We can figure out who it belongs to!

Q: What is the name of the employee whose host has the ransom note?

A: Anthony Davis


Run the query above. How many process events were executed on Anthony's machine during this time period?

ans 14

Let's read through the commands in the process_commandline column from the top down. Make sure you are sorting by time.

One of the command mentions a "ransomer". That's VERY suspicious!

What was the name of the ransomer file mentioned?

 lockbyte_ransomer.exe



When the attackers copied the ransomer file to the network share, what new name did they give it?

 spread_ransomware.exe



If we keep looking down in the data, we can see that the hackers actually stole some data from the hospital as well 😱

What tool did the attackers use to steal the data? This will be a .exe file

 patient_data_exporter.exe

We let the bosses know that the attackers actually stole some files. They were not at all thrilled to hear that. They want to know what the attackers actually stole.

The attackers stole files that they put into three zip files.

What information did the attackers put into patient_data_1.zip? Provide the full path of the network share \\something\like\this

 \\jojos-hospital-server\important_data\patient_records



What information did the attackers put into patient_data_2.zip? Provide the full path of the network share \\something\like\this

 \\jojos-hospital-server\important_data\archive\patient-records

What information did the attackers put into patient_data_3.zip? Provide the full path of the network share \\something\like\this

 \\jojos-hospital-server\important_data\old-patient-data


What domain (e.g. abcd.com) did the attackers send the stolen data to?

 secure-health-access.com

What command did they use to clear their tracks? Copy and paste the full command.

 cmd.exe /c del C:\Users\andavis\Documents\patient_data_*.zip







What domain was the patient data exporter file downloaded from?

 secure-health-access.com


When was the patient data exporter file downloaded? (copy and paste the exact timestamp)

 2024-06-17T14:22:29Z

How many distinct IPs does the domain secure-health-access.com resolve to?

 2


Which one of these IPs ends with the digit 1?

203.0.113.1

Which one of these IPs ends with the digit 1?

203.0.113.2

What additional domain name is associated with these IP addresses?

emr-help.net




let's take the actor IPs we found and look for any reconnaissance they conducted against the hospital website. InboundNetworkEvents contains information about browsing to our website.

How many requests did the hackers make to our website from these IPs?

 37

The hackers were curious about how to bypass ___ at Jojo's hospital.

 security

What was the first web request the hackers made using the term patient? (hint: it was a search). Paste the full url.

https://jojoshospital.org/search=JoJo%27s+Hospital+patient+records

When did this login occur?

2024-05-20 00:00:00


Which IP address did the actors use for the login?

203.0.113.1


Whose account did the hackers login to? (provide a first and last name)

 Anthony Davis

Whose credentials did the hackers use to access the hospital's network? (Enter first and last name)

Anthony Davis


What was the domain name observed in the sponsored search result?

raisinkanes.com

What is the legitimate domain for Raising Cane's?

raisingcanes.com


How many web requests do we see going to the fake raisinkanes domain?

26

How many unique employees were seen browsing to the fake raisinkanes domains? (hint distinct the src_ip)

24


When staff clicked on the fake advertisement, it took them to a harmful website. This website had a malicious URL.

Which of the malicious domains used for redirection starts with the word "nothing"?

nothing-to-see-here.net

Which of the malicious domains used for redirection starts with the word "totally"?

 totally-legit-domain.com

Now we must wonder what happens when the employees click on those suspicious domains and are redirected.

Looks like they are forced to download some suspicious files.

What is the name of the docx file they are redirected to?

Raisin_Kane_Promo_Offer.docx

What is the name of the pdf file they are redirected to?

 Raisin_Kane_Free_Meal_Voucher.pdf

What is the hostname of the first person to download the suspicious docx file?

 RQJQ-MACHINE

When did this download occur? (copy and paste the timestamp)

 2024-05-01T09:56:50Z

What was the Sha256 hash of the file?

bd886046266b909a8ca5f19f16e5606baf73194a70632c81fdc44ef39ba29712

Which browser was used to download this file? (look at the process_name)

 chrome

What was the name of the malicious file dropped by the attackers?

cobaltstrike.exe

What IP address do the hackers connect to using cobalt strike?

 93.238.22.122