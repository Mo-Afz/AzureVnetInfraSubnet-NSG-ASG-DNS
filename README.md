# AZ-104 Lab 04 – Implement Virtual Networking

## 📘 Overview

This repository contains a complete walkthrough of [AZ-104 Lab 04](https://github.com/MicrosoftLearning/AZ-104-MicrosoftAzureAdministrator/blob/master/Instructions/Labs/LAB_04-Implement_Virtual_Networking.md), which focuses on creating and managing virtual networks (VNets), subnets, NSGs, ASGs, and DNS zones within Azure. Every configuration step is documented with inline screenshots for learning and validation.

---

## 🧭 Task-by-Task Walkthrough

### Task 1: Create a Virtual Network and Subnets (Portal-Based)

1. **Initial state – no VNet present**  
   ![Initial state](notes/01-no-vnet-initial-state.png.png)

2. **Created CoreServicesVnet – overview**  
   ![CoreServicesVnet overview](notes/03-coreservices-vnet-overview.png.jpg)

3. **Subnet breakdown – SharedServicesSubnet and DatabaseSubnet**  
   ![Subnet details](notes/04-coreservices-vnet-subnet-breakdown.png.jpg)

4. **Architecture view of the full setup**  
   ![Network architecture](diagrams/az104-lab04-architecture.png)

5. **Subnet configuration via portal**  
   ![Subnet config step](templates/02-coreservices-vnet-subnet-config.png.jpg)

---

### Task 2: Export and Modify Template for VNet Deployment

1. **Exported template from CoreServicesVnet deployment**  
   ![ARM template export](templates/05-coreservices-arm-template-export.png.jpg)

2. **Edited `template.json` and added ManufacturingVnet**  
   ![Edited template JSON](templates/08-manufacturing-arm-temp-edited.png.jpg)

3. **Updated parameters for address space and subnets**  
   ![Parameter file edit](templates/09-manufacturing-arm-temp-parameters.png.jpg)

4. **ManufacturingVnet overview after deployment**  
   ![ManufacturingVnet overview](notes/10-manufacturing-vnet-overview.png.jpg)

---

### Task 3: Configure NSGs and ASGs

1. **Created Application Security Group: `asg-web`**  
   ![ASG creation](security/13-asg-web-creation.jpg)

2. **Created Network Security Group: `myNSGSecure` with rules**  
   ![NSG creation](security/14-myNSGSecure-rule.jpg)

3. **Associated NSG with SharedServicesSubnet**  
   ![NSG subnet link](security/15-nsg-subnet-link.png.jpg)

4. **Configured inbound rule to allow traffic from ASG**  
   ![Inbound rule setup](security/16-nsg-inbound-rule-asg.png.jpg)

5. **Confirmed inbound rule setup**  
   ![Inbound rule confirmation](security/17-nsg-inbound-rule-confirm.png.jpg)

6. **Created outbound rule to deny internet access**  
   ![Outbound rule creation](security/18-nsg-outbound-rule-create.png.jpg)

7. **Confirmed outbound rule**  
   ![Outbound rule confirmation](security/19-nsg-outbound-rules-confirm.png.jpg)

---

### Task 4: Configure Public and Private DNS Zones

1. **Created public DNS zone**  
   ![Public DNS zone creation](dns-config/20-dns-zone-creation.png.jpg)

2. **Added A record for web service**  
   ![A record creation](dns-config/21-dns-a-record-web.png.jpg)

3. **DNS zone overview**  
   ![DNS zone view](dns-config/22-dns-zone-overview.png.jpg)

4. **Verified name resolution with nslookup**  
   ![NSLookup validation](dns-config/23-dns-nslookup-validation.png.jpg)

5. **Created private DNS zone**  
   ![Private DNS zone creation](dns-config/24-private-dns-zone-creation.png.jpg)

6. **Linked private DNS zone to VNet**  
   ![VNet link setup](dns-config/25-private-dns-vnet-link.png.jpg)

7. **Added A record to private DNS zone**  
   ![Private A record](dns-config/26-private-dns-a-record-web.png.jpg)

---

## 📂 Repository Structure

| Folder        | Contents                                                  |
|---------------|-----------------------------------------------------------|
| `diagrams/`   | Network architecture visual                               |
| `dns-config/` | All public/private DNS zone steps                         |
| `notes/`      | Status confirmations and VNet overview                    |
| `security/`   | NSG/ASG creation, rules, and verification                 |
| `templates/`  | ARM template files and edits                              |

---

## 🎓 Learning Objectives

- Build and configure VNets via portal and templates
- Secure subnet traffic with NSGs and ASGs
- Implement and validate Azure public/private DNS zones
- Document full network lifecycle with embedded references

---

## 🔗 References

- [AZ-104 Lab 04 Instructions](https://github.com/MicrosoftLearning/AZ-104-MicrosoftAzureAdministrator/blob/master/Instructions/Labs/LAB_04-Implement_Virtual_Networking.md)
