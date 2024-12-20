
# How to Create a Virtual Machine from an Instance in AWS (Ubuntu Linux)

This guide explains how to create an AWS EC2 instance running Ubuntu Linux, enable root login with a password, and create a reusable custom image.

---

## **Step 1: Launch an Instance in AWS**
1. **Log in to the AWS Management Console**.
2. Navigate to **EC2** (Elastic Compute Cloud) and click **Launch Instances**.
3. Configure the instance:
   - **AMI**: Choose an Ubuntu Linux AMI (e.g., Ubuntu Server 22.04 LTS).
   - **Instance Type**: Select based on your needs (e.g., `t2.micro` for free tier).
   - **Key Pair**: Create or select an existing key pair for secure SSH access.
   - **Security Groups**: Allow SSH (port 22) access. Optionally restrict access to your IP.
4. Launch the instance and wait for it to start.

---

## **Step 2: Connect to the Instance**
1. Use an SSH client to connect to the instance:
   ```bash
   ssh -i /path/to/key.pem ubuntu@<instance-public-ip>
   ```
   Replace `<instance-public-ip>` with the instance's public IP address.

---

## **Step 3: Enable Root Login and Set a Root Password**
1. **Switch to Root User**:
   ```bash
   sudo -i
   ```
2. **Set a Password for the Root Account**:
   ```bash
   passwd root
   ```
   Enter and confirm a new password.

3. **Edit the SSH Configuration File**:
   Open the SSH configuration file:
   ```bash
   nano /etc/ssh/sshd_config
   ```
   Modify the following lines:
   - Set `PermitRootLogin` to:
     ```plaintext
     PermitRootLogin yes
     ```
   - Ensure `PasswordAuthentication` is set to:
     ```plaintext
     PasswordAuthentication yes
     ```

4. **Restart the SSH Service**:
   ```bash
   systemctl restart sshd
   ```

---

## **Step 4: Log in as Root**
1. Disconnect from the current session:
   ```bash
   exit
   ```
2. Reconnect using the root account and password:
   ```bash
   ssh root@<instance-public-ip>
   ```
   Enter the root password you set earlier.

---

## **Step 5: (Optional) Create a Custom AMI**
If you want to create a reusable image:
1. Navigate to **EC2** > **Instances** in the AWS Console.
2. Select the instance, click **Actions**, and choose **Create Image**.
3. Provide a name for the image, and AWS will create an AMI (Amazon Machine Image).

---

## **Important Notes**
- **Security Risks**: Enabling root login with a password is insecure for production systems. Use SSH key pairs for better security.
- **Restrict Access**: Limit SSH access to trusted IPs in the security group.
- **Testing Only**: This setup is recommended for testing environments, not production.

---

### **Need Help?**
If you encounter any issues, consult AWS documentation or contact support.
