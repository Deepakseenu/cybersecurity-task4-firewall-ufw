# 🔥 Cybersecurity Task 4 – Firewall Configuration Using UFW on Kali Linux

## 🎯 Objective
The goal of this task is to understand and apply basic firewall rules using **UFW (Uncomplicated Firewall)** on **Kali Linux running inside VMware**. You will configure rules to block and allow traffic, test the changes, and verify the firewall's effectiveness.

---

## 🛠 Environment & Tools

- **OS:** Kali Linux (Virtual Machine inside VMware)
- **Firewall Tool:** UFW (Uncomplicated Firewall)
- **Test Tool:** Telnet (for port testing)
- **User Access:** Root or sudo privileges

---

## ⚙️ Steps with Commands, Explanations & Screenshots

---

### ✅ Step 1: Install UFW

Kali Linux might not come with UFW pre-installed.
```bash
#sudo apt update && sudo apt install ufw -y

### ✅ Step 2: Enable UFW
```bash
#sudo ufw enable
📸 Screenshot: ufw_enabled.png
✅ Activates the firewall on your system.

### ✅ Step 3: Check Current Firewall Status
```bash
#sudo ufw status numbered
📸 Screenshot: ufw_status.png
✅ Displays currently active rules.

### ✅ Step 4: Block Inbound Traffic on Port 23 (Telnet)
```bash
#sudo ufw deny 23
📸 Screenshot: deny_port_23.png
✅ This blocks insecure Telnet traffic.

### ✅ Step 5: Allow Inbound SSH on Port 22
```bash
#sudo ufw allow 22
📸 Screenshot: allow_ssh.png
✅ Allows secure remote login via SSH.

### ✅ Step 6: Install Telnet Client (for Testing)
If not already installed:
```bash
#sudo apt install telnet -y

### ✅ Step 7: Test Connection to Port 23
```bash
#telnet localhost 23
📸 Screenshot: telnet_test.png
❌ Expected: Connection refused or similar message
✅ This confirms port 23 is successfully blocked.

### ✅ Step 8: Delete the Deny Rule (Unblock Port 23)
```bash
#sudo ufw delete deny 23
📸 Screenshot: rule_deleted.png
✅ Removes the block from port 23.