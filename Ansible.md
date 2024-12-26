# Ansible

Ansible is an open-source automation tool used for **configuration management**, **application deployment**, **task automation**, and **IT orchestration**. It simplifies the management of servers, applications, and infrastructure by allowing users to define and automate tasks in the form of **playbooks**.

Ansible is commonly used for:
- Server provisioning
- Application deployment
- Configuration management
- Various IT automation tasks

It is platform-agnostic and supports a wide range of operating systems, making it a popular choice for **DevOps** and **system administrators** to streamline and automate their tasks.

![image](https://github.com/user-attachments/assets/05a775d1-709b-424b-a00e-9927bd23034a)

Here’s the content restructured into neatly organized, explainable notes with clear headings and explanations:

---

## **Ansible Overview**

Ansible is an open-source automation tool used for:  
- **Configuration management**  
- **Application deployment**  
- **Task automation**  
- **IT orchestration**

It simplifies server, application, and infrastructure management by enabling tasks to be defined and automated using **playbooks**. Ansible is platform-agnostic and widely used by **DevOps** engineers and **system administrators**.

---

## **Key Concepts in Ansible**

### **1. Control Machine (Master)**
- The **control machine** is the system where Ansible is installed.  
- It is used to run tasks on **managed hosts**.  
- Any machine with Python installed can act as a control machine, except **Windows**.  

### **2. Managed Nodes (Slaves or Hosts)**
- These are the systems that Ansible connects to and performs tasks on.  
- Managed nodes can run on a wide range of operating systems.  
- No agent software is required on managed nodes, as Ansible uses **SSH** for connectivity.  

---

## **Features and Core Components of Ansible**

### **1. Agentless**
- Ansible does not require any agent software on the managed hosts.  
- It uses **SSH** (Secure Shell) to connect and execute tasks on remote systems.  
- This simplifies setup and reduces overhead.

### **2. Playbooks**
- Playbooks are YAML files that define a set of tasks to be executed on target hosts.  
- They are human-readable, easy to write, and can include:  
  - **Server configurations**  
  - **Software installations**  
  - **File transfers**  
- Playbooks can also be version-controlled for better management.  

### **3. Inventory**
- The **inventory** is a list of hosts that Ansible manages.  
- It can be defined in various formats:  
  - Simple text files (e.g., `hosts.ini`)  
  - Dynamic inventory scripts for cloud-based environments.  
- The inventory helps identify which hosts are targeted for specific tasks.  

### **4. Modules**
- Modules are reusable components used to perform specific tasks.  
- Built-in modules support:  
  - **Configuring system settings**  
  - **Installing software**  
  - **Managing files**  
- Users can also create **custom modules** to extend functionality.  

### **5. Ad-hoc Commands**
- Ad-hoc commands allow immediate task execution from the command line.  
- These are useful for one-time tasks or quick checks.  

**Example Command:**  
```bash
ansible all -m ping
```

**Explanation:**
- `all`: Targets all hosts in the inventory.  
- `-m ping`: Uses the `ping` module to check connectivity.  

### **6. Roles**
- Roles are a structured way to organize playbooks, variables, and tasks.  
- They promote reusability and simplify complex configurations.  
- Roles can be shared and reused via **Ansible Galaxy**.

### **7. Community and Ecosystem**
- Ansible has a vibrant community contributing to modules and roles on **Ansible Galaxy**.  
- This ecosystem allows users to leverage pre-written configurations and scripts.

---

## **Ansible History**

### **Origin (2006–2012)**
- **Michael DeHaan** developed a precursor tool called **Cobbler**, focused on server provisioning.  
- He identified limitations in existing tools for managing infrastructure, inspiring Ansible's creation.

### **Founding of AnsibleWorks (2012)**  
- AnsibleWorks, the company behind Ansible, was founded in 2012.  
- The goal was to create an efficient, user-friendly automation tool addressing the shortcomings of other tools.

### **Initial Release and Open Source (2012)**  
- Ansible was released as an open-source project in 2012.  
- It gained attention for its **simplicity**, **agentless architecture**, and **ease of use**.

### **Community Growth and Adoption (2013–2015)**  
- Ansible attracted a growing community of users and contributors.  
- Its robust capabilities for configuration management, deployment, and orchestration made it a popular choice.

### **Acquisition by Red Hat (2015)**  
- Red Hat acquired Ansible in 2015, integrating it into their ecosystem.  
- This boosted Ansible's visibility in the open-source and enterprise communities.

### **Evolution and Updates (2015–Present)**  
- Ansible expanded to support:  
  - **Cloud provisioning**  
  - **Application deployment**  
  - **Network automation**  
- It continued receiving updates to stay relevant in the evolving DevOps and IT automation landscape.

---

## **Key Takeaways**
- **Agentless Architecture**: Reduces complexity by using SSH.  
- **Playbooks**: YAML-based, human-readable task definitions.  
- **Extensibility**: Large library of built-in and community modules.  
- **Platform-Agnostic**: Supports various operating systems and cloud providers.  
- **Community-Driven**: Strong ecosystem with contributions on Ansible Galaxy.

---

# Step 1 : 
launch three ubuntu instances in aws
