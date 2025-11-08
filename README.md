# Azure VM Assignment – Ubuntu Linux

**Student Name:** Murat Gürpınar

## **Purpose**
The purpose of this assignment is to enable students to gain the skills to create, configure, and perform basic management of virtual machines on the Azure platform.

---

## **Assignment Steps**

### **1. Create an Azure Account**
- Free Azure trial account with student benefits used.

### **2. Create a Resource Group**
- Name: `Murat_Gurpinar_RG`
- Location: West Europe

### **3. Create a Virtual Machine**
- Name: `Murat_Gurpinar_VM`
- OS: Ubuntu Server 20.04 LTS
- Size: Standard_B1s
- Public IP assigned
- SSH enabled (port 22)
- Default disk and networking settings used

### **4. Connect to the Virtual Machine**
- Connected via **Azure Bastion** using SSH.
- Verified VM is running and accessible.

### **5. Create and Connect to Azure File Share**
- Storage Account: `muratgurpinarstorage`
- File Share: `sharedfiles`
- Mounted on VM:
  `sudo mount -t cifs //muratstorage01.file.core.windows.net/sharedfiles /mnt/azfileshare \
-o vers=3.0,username=muratstorage01,password=<STORAGE_KEY>,dir_mode=0777,file_mode=0777,serverino`

	•	Verified creating, reading, and deleting files works.

### **6. Tasks on the Virtual Machine**

Apache Web Server
	•	Installed Apache:
  
  `sudo apt install apache2 -y
sudo systemctl start apache2`

MySQL Database
	•	Installed MySQL server:

  `sudo apt install mysql-server -y
sudo mysql_secure_installation`

Samba File Sharing
	•	Installed Samba:

  `sudo apt install samba -y`
Configured shared folder at /srv/samba/shared
	•	Verified read/write access from VM

Azure File Share Usage
	•	Mounted File Share
	•	Created, read, deleted test files
	•	Verified functionality


### **7. Screenshots**
<img width="849" height="673" alt="Screenshot 2025-11-08 at 22 50 52" src="https://github.com/user-attachments/assets/ab64e93f-993b-40f7-8066-ad17110882e8" />
<img width="1434" height="712" alt="Screenshot 2025-11-08 at 22 53 49" src="https://github.com/user-attachments/assets/f813e319-2ab3-4c01-975a-92fd800ba1bd" />
<img width="1262" height="204" alt="Screenshot 2025-11-08 at 22 52 19" src="https://github.com/user-attachments/assets/8a5ffc99-04df-4ba7-a6e0-27d3739aead2" />

### **7.Problems Encountered**
	•	Initial SSH connection blocked by NSG → resolved by adding inbound rule for port 22.
	•	File Share mount required cifs-utils → installed via sudo apt install cifs-utils -y.


