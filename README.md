# Active Directory Simulation – Bayotech Solutions

This project is the deployment of a Windows Server Domain Controller (Active Directory) for a company called **Bayotech Solutions**. It includes domain setup, client configuration, OU design, group policies, and access control in an enterprise environment.

---

## Company Structure

**Bayotech Solutions** is a small IT services firm with the following structure:

- 1 × Windows Server (AD Domain Controller)
- 1 × Windows 8 Client PC (IT Department)
- 1 × Windows 8 Client PC (Sales Department)

---

## Project Objectives

- Configure an AD Domain Controller on Windows Server  
- Join client PCs to the domain  
- Create Organizational Units (OUs)  
- Implement basic Group Policies for access control  
- Simulate a centralized IT environment  

---

## Network Design

```
Internet
   ↓
Router (Gateway: 10.0.2.1)
   ↓
Switch
 ┌──────┬─────────────┬──────────────┐
 │      │             │              │
Server  PC1 (Win 8)   PC2 (Win 8)
```

| Device          | IP Address | Role                              |
|-----------------|-------------|-----------------------------------|
| Windows Server  | 10.0.2.3    | AD Domain Controller (DC)         |
| Windows 8 PC    | DHCP        | Client (IT Department)            |
| Windows 8 PC    | DHCP        | Sales Department                  |

---

## Domain Configuration

- **Domain Name:** `Bayotech.com`  
- **Server Name:** `BAYOTECH`  
- **Static IP:** `10.0.2.3`  
- **AD Roles Installed:** AD DS, DNS (DHCP)

---

## Organizational Units (OUs)

Created using **Active Directory Users and Computers**:

```
Bayotech.com
├── OU: Atlanta
│   └── Users: Jsmith_ITATL


├── OU: UK
│   └── Users:Branson_saleUK
```

---

## Group Policy (GPO)

Created and linked using **Group Policy Management Console (gpmc.msc)**:

- **GPO Name:** `DisableShutdown`
- **Linked to:** OU: Atlanta
- **Policy Configured:**
  - `Computer Configuration` → `Administrative Templates` → `Start Menu and Taskbar`
  - Set **"Remove and prevent access to the Shut Down, Restart, Sleep, and Hibernate commands"** to **Enabled**


**Result:**  
Prevents domain users from shutting down, restarting, or putting the system to sleep — enforcing controlled access and reducing unauthorized system downtime in Atlanta OU.

---

## Screenshots

- AD Domain Structure  
- GPO Editor Screenshot  
- PC Joined to Domain  
- [Result of Denied Shutdown command access System](https://github.com/Afijabi71/Active-Directory-Simulation-Bayotech-Solutions/blob/main/Screenshots/Access_denied_1.png)

---

## Key Takeaways

- Gained practical experience with Windows Server roles and domain setup  
- Implemented centralized access control using Group Policy  
- Learned how to structure users and departments with OUs  
- Applied IAM concepts in a real-world simulated environment  

---

## Author

**Adebayo Fijabi**  
*Cybersecurity Analyst*
