**🛡️ Security Incident Report**\
**Incident Title**: Malicious File Download via HTTP\
**Analyst**: Basma\
**Date**: July 26, 2025\
**System Affected**: Web server of *yummyrecipesforme.com*\
**Incident Type**: Brute force attack & malware distribution

---

### **Section 1: Identify the network protocol involved in the incident**

The network protocol involved in this incident is the **Hypertext Transfer Protocol (HTTP)**, which operates at the **application layer** of the TCP/IP model.\
The incident was associated with unauthorized access and malware delivery through the website *yummyrecipesforme.com*. All traffic between users and the web server was transmitted over HTTP.

During the investigation, the cybersecurity analyst used the tool **tcpdump** while accessing the website. The packet capture logs confirmed that the malicious file was transmitted using the HTTP protocol.

---

### **Section 2: Document the incident**

Multiple users contacted the help desk to report that they were prompted to download and run a file claiming to provide access to new recipes on *yummyrecipesforme.com*. After executing the file, their devices became noticeably slower.

The website administrator attempted to log into the admin account on the server but discovered the account had been locked.\
A cybersecurity analyst launched the website inside a **sandbox environment** to safely analyze its behavior and used **tcpdump** to monitor network traffic during the session.

While visiting the website, the analyst was prompted to download a file titled as "free recipes". After executing the file, the browser was redirected to a **malicious site** named *greatrecipesforme.com*. The tcpdump logs revealed that initially, the browser contacted *yummyrecipesforme.com* via HTTP, downloaded and executed the file, and then suddenly redirected traffic to the malicious domain's IP address.

The senior security analyst examined the **source code** of both websites as well as the downloaded file. The analysis uncovered that the attacker had injected malicious code into *yummyrecipesforme.com*, which prompted users to download a file disguised as a **browser update**. Based on the admin's report of being locked out, it was concluded that the attacker likely used a **brute force attack** to gain access to the administrator account and carry out the attack.

---

### **Section 3: Recommend one remediation for brute force attacks**

To prevent future brute force attacks, the cybersecurity team recommends the following actions:

- **Enforce password history restrictions**: Prevent users from reusing old or default passwords, especially during password resets.
- **Mandate frequent password changes**: This limits the window of opportunity for attackers in case a password is compromised.
- **Enable Two-Factor Authentication (2FA)**: Add an extra layer of protection by requiring a one-time password (OTP) sent via email or phone after password entry. Even if the attacker successfully guesses the password, 2FA makes it significantly harder to access the account.

---

🎯 **Note**: This report was created as part of a cybersecurity learning activity and is based on a fictional incident inspired by the [Google Cybersecurity Certificate](https://www.coursera.org/professional-certificates/google-cybersecurity) learning materials.
