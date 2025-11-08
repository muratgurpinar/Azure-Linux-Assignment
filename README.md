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
```bash
sudo mount -t cifs //muratgurpinarstorage.file.core.windows.net/sharedfiles /mnt/azfileshare \
-o vers=3.0,username=muratgurpinarstorage,password=<STORAGE_KEY>,dir_mode=0777,file_mode=0777,serverino
