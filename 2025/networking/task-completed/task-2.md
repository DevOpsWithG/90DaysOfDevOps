
### Task 2. Protocols and Ports for DevOps ⚙️
Networking protocols define how data is exchanged over a network.

#### Commonly Used Protocols & Ports:
- **HTTP** (Port 80) - For web traffic (insecure).
- **HTTPS** (Port 443) - Secure web traffic.
- **SSH** (Port 22) - Secure remote server management.
- **FTP** (Port 21) - File transfer (insecure).
- **DNS** (Port 53) - Resolves domain names to IP addresses.

#### Why Are These Important for DevOps?
- **SSH** allows you to securely access servers.
- **HTTP/HTTPS** are essential for serving web applications.
- **DNS** is critical for domain name resolution in deploying services.

**1. HTTP (HyperText Transfer Protocol)**
**Port: 80**
Use Case: HTTP is the protocol used for serving web pages and web applications over the internet.
Why It's Relevant to DevOps:
DevOps professionals often deal with web servers, APIs, and microservices that rely on HTTP to communicate with users and other services. 
When deploying web applications, HTTP is often used in the development and testing phases before moving to secure environments.
Example: When you deploy a web app on a server (e.g., NGINX or Apache), it communicates via HTTP on port 80. DevOps teams use tools like 
curl to test endpoints, which relies on HTTP for communication.

**2. HTTPS (HyperText Transfer Protocol Secure)**
**Port: 443**
Use Case: HTTPS is the secure version of HTTP, encrypting the communication between the client and server to ensure confidentiality and 
integrity.
Why It's Relevant to DevOps:
In production environments, security is paramount. HTTPS ensures secure communication over the web, protecting data and user privacy.
DevOps engineers must configure SSL/TLS certificates to enable HTTPS on web servers and services.
Example: When hosting an e-commerce site or any web application handling sensitive data (such as user credentials or payment information), 
DevOps engineers must set up HTTPS to secure communication on port 443.

**3. SSH (Secure Shell)**
**Port: 22**
Use Case: SSH provides a secure way to log in to and execute commands on remote servers.
Why It's Relevant to DevOps:
SSH is a must-have tool for DevOps engineers managing cloud infrastructure, virtual machines, and containers. It's used to securely 
connect to servers, automate scripts, and run remote commands during deployment and maintenance tasks.
Many CI/CD pipelines use SSH for deploying applications to remote servers.
Example: When setting up an AWS EC2 instance, DevOps engineers use SSH to connect to the instance, configure the environment, and deploy 
applications.

**4. FTP (File Transfer Protocol)**
**Port: 21**
Use Case: FTP is used to transfer files between a client and server.
Why It's Relevant to DevOps:
Although less common in modern DevOps workflows (due to alternatives like SCP or S3), FTP is still used in legacy systems for transferring 
large files between environments or managing website content.
FTP might be configured for backup systems or in environments where a simple file transfer method is needed.
Example: When managing an older web server, DevOps teams might use FTP to upload content such as static files, images, or backups.

**5. DNS (Domain Name System)**
**Port: 53**
Use Case: DNS is the system that translates human-readable domain names (e.g., example.com) into IP addresses.
Why It's Relevant to DevOps:
DNS is a key component in every web and cloud environment. DevOps professionals must manage DNS records when setting up cloud infrastructure, 
ensuring that domain names resolve to the correct IP addresses or load balancers.
Understanding DNS is important for configuring services like Kubernetes, CDNs, or SSL certificates that rely on domain resolution.
Example: When configuring a new website, DevOps teams update the DNS records to point the domain to the IP address of the web server. 
Tools like dig or nslookup are used to troubleshoot DNS issues.

**6. SMTP (Simple Mail Transfer Protocol)**
**Port: 25** (default), 587 (for secure submission)
Use Case: SMTP is used to send emails over the internet.
Why It's Relevant to DevOps:
Email alerts and notifications are a crucial part of many DevOps monitoring and incident management systems. SMTP is used to send 
notifications from services like Prometheus, Nagios, or Jenkins to email inboxes.
DevOps engineers often configure SMTP for sending automated emails during deployments or system failures.
Example: A CI/CD pipeline might send a notification email to the team using SMTP after a successful build or deployment.

**7. IMAP/POP3 (Email Retrieval Protocols)**
Ports:
IMAP (Internet Message Access Protocol): 143 (non-encrypted), 993 (encrypted)
POP3 (Post Office Protocol): 110 (non-encrypted), 995 (encrypted)
Use Case: IMAP and POP3 are protocols for retrieving emails from a server.
Why It's Relevant to DevOps:
Like SMTP, these protocols are used in email systems, which may be part of automated reporting, alerting, or feedback loops within DevOps 
environments.
Example: IMAP can be configured to retrieve emails for automated reporting tools or monitoring systems, providing important feedback about 
system status.

**8. Telnet (Telecommunication Network)**
**Port: 23**
Use Case: Telnet is used for remote communication and management of devices.
Why It's Relevant to DevOps:
Telnet is mostly replaced by SSH due to security vulnerabilities, but it's still used in some legacy systems. DevOps teams might need to 
configure or troubleshoot older hardware or software environments where Telnet is still in use.
Example: If you are working with legacy network equipment (e.g., routers or switches), Telnet might still be in use for remote access, 
although it’s not encrypted.

**9. RDP (Remote Desktop Protocol)**
**Port: 3389**
Use Case: RDP allows users to connect to and control Windows-based systems remotely.
Why It's Relevant to DevOps:
When managing Windows servers or virtual machines in the cloud, RDP is essential for remote management and troubleshooting.
DevOps teams use RDP to manage, configure, and monitor Windows-based infrastructure, especially in environments using tools like Microsoft 
Azure.
Example: A DevOps engineer might use RDP to connect to a Windows Server in an AWS EC2 instance for configuring Windows-specific software 
or services.

**10. LDAP (Lightweight Directory Access Protocol)**
**Port: 389 (non-encrypted), 636 (encrypted)**
Use Case: LDAP is used to access and manage directory information services over a network (e.g., user authentication).
Why It's Relevant to DevOps:
LDAP is often used in enterprise environments for authentication and directory services, such as managing users and permissions.
DevOps teams use LDAP to authenticate users against a centralized database (like Active Directory) when configuring services or 
internal applications.
Example: Setting up centralized user authentication in a large organization involves using LDAP to allow multiple services to 
authenticate users through a single directory.

