## 📌 Tasks

### **1️⃣ User & Group Management**
- **Task:**  
  - Create a user `devops_user` and add them to a group `devops_team`.
  - Set a password and grant **sudo** access.
  - Restrict SSH login for certain users in `/etc/ssh/sshd_config`.
- **Solutions:**
  1. Creating user `devops_user` and some other users `tester` and `devloper`
      ```
      sudo useradd -m devops_user -s /bin/bash
      ```
   
  2. Verifying if devops_user created 
     ```
     cat /etc/passwd | grep devops
     devops_user:x:1003:1003::/home/devops_user:/bin/bash
     ```
  
  3. Similarly creating and verifyifing  user `tester` and `developer`
     ```
     tester:x:1004:1004::/home/tester:/bin/bash
     developer:x:1005:1005::/home/developer:/bin/bash
     ```
  
  4. Creating a group `devops_team` and verifying it
     ```
     sudo groupadd devops_team
     cat /etc/group | grep devops_team
     devops_team:x:1006:
     ```
  
  5. Adding multiple user to devops_team and verifying it
     ```
     sudo gpasswd -M devops_user,tester devops_team
     cat /etc/group | grep tester
     devops_team:x:1006:devops_user,tester
     ```
  
  6. Removing user devops_user from group tester
     ```
     sudo gpasswd -d devops_user tester
     Removing user devops_user from group tester
     ```
  
  7. Giving sudo permission to users
     ```
     sudo usermod -aG sudo devops_user
     sudo:x:27:ubuntu,devops_user
     ```

  6. To append the user to group where some users are already present
     ```
     sudo usermod -aG devops_team developer
     devops_team:x:1006:devops_user,tester,developer
     ```
  9. Updating password for devops_user
      ```
      ubuntu@ip-172-31-45-204:~$ sudo passwd devops_user
      New password:
      Retype new password:
      passwd: password updated successfully
      ```
  10. Restricting ssh for tester user and tester group
  
      Add below lines by doing `sudo vi /etc/ssh/sshd_config`
      ```
      DenyUsers tester
      DenyGroups tester
      ```



  
