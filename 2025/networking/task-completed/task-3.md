### 3. AWS EC2 and Security Groups 🔐
 
**AWS EC2** (Elastic Compute Cloud) provides scalable computing power, while 
**Security Groups** act as virtual firewalls, controlling inbound and outbound traffic for your instances.

#### Steps to Launch an EC2 Instance:
1. Log into the AWS Management Console.
2. Navigate to **EC2** under the Compute section.
3. Select the **Launch Instance** option.
4. Choose an **Amazon Machine Image (AMI)** (e.g., Amazon Linux, Ubuntu).
5. Select the instance type (t2.micro for free tier).
6. Configure instance details and add storage.
7. Create a **Security Group** with rules:
   - Allow **SSH (Port 22)** from your IP for secure login.
   - Open **HTTP/HTTPS (Port 80/443)** if hosting a web service.
8. Review and launch your instance.
