# TechLab – Microsoft Intune Administration Portfolio

![Microsoft Intune](https://img.shields.io/badge/Microsoft-Intune-0078D4?style=for-the-badge&logo=microsoft)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Android%20Enterprise-success?style=for-the-badge)
![Documentation](https://img.shields.io/badge/Documentation-Markdown-blue?style=for-the-badge)

---

# Project Overview

This repository documents my hands-on Microsoft Intune Administration laboratory, developed within a Microsoft cloud environment using Microsoft Intune, Microsoft Entra ID and a physical Android Enterprise device.

The project demonstrates the complete lifecycle of Android Enterprise device management, beginning with the creation of a Microsoft Intune tenant and progressing through device enrolment, application deployment, compliance management, configuration profiles, device administration, monitoring and troubleshooting.

Rather than simply describing Microsoft Intune features, this repository documents the practical tasks performed by an Endpoint Administrator when deploying and managing Android Enterprise devices in a modern cloud-based environment.

The laboratory was built using an existing Microsoft 365 tenant created during my previous Microsoft 365 Administration and Microsoft Entra ID Administration projects, demonstrating how Microsoft cloud services integrate to provide a complete endpoint management solution.

---

# Project Objectives

Throughout this project, I developed practical experience with Microsoft Intune by completing a series of hands-on administrative exercises.

The primary objectives of this repository were to:

- Understand Microsoft Intune architecture and licensing.
- Configure a Microsoft Intune laboratory environment.
- Explore the Microsoft Intune Admin Center.
- Prepare Microsoft Entra users and Security Groups.
- Enrol Android Enterprise devices.
- Deploy Android applications through Managed Google Play.
- Configure Compliance Policies.
- Deploy Configuration Profiles.
- Manage enrolled Android Enterprise devices.
- Monitor device health and deployment status.
- Troubleshoot common Microsoft Intune administration issues.
- Produce professional technical documentation suitable for a GitHub portfolio.

---

# Skills Demonstrated

Throughout this project I demonstrate practical experience with:

- Microsoft Intune Administration
- Endpoint Management
- Mobile Device Management (MDM)
- Mobile Application Management (MAM)
- Android Enterprise Administration
- Microsoft Entra ID Integration
- Android Device Enrolment
- Managed Google Play
- Application Deployment
- Compliance Policy Administration
- Configuration Profile Deployment
- Device Management
- Monitoring and Reporting
- Troubleshooting
- Technical Documentation
- GitHub Portfolio Development

---

# Technologies Used

| Technology | Purpose |
|------------|---------|
| Microsoft Intune Plan 1 | Cloud endpoint management |
| Microsoft Entra ID | Identity and access management |
| Microsoft 365 Admin Center | Tenant administration |
| Microsoft Intune Admin Center | Endpoint administration |
| Android Enterprise | Mobile device management platform |
| Microsoft Company Portal | Device enrolment |
| Managed Google Play | Enterprise Android application deployment |
| Microsoft Authenticator | User authentication |
| GitHub | Version control |
| Markdown | Technical documentation |

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Tenant | TechLab |
| Identity Platform | Microsoft Entra ID |
| Endpoint Management | Microsoft Intune Plan 1 |
| Device Platform | Android Enterprise |
| Enrolment Method | Personally-Owned Work Profile (BYOD) |
| Test Device | Android Smartphone |
| Application Store | Managed Google Play |
| Documentation | Markdown |
| Version Control | GitHub |

---

# Repository Structure

```text
TechLab-Microsoft-Intune-Administration-Portfolio
│
├── README.md
│
├── 01-Creating-the-Intune-Lab-Environment
├── 02-Intune-Administration-Center-Overview
├── 03-User-and-Group-Preparation
├── 04-Android-Device-Enrolment
├── 05-Deploying-Android-Applications-with-Managed-Google-Play
├── 06-Compliance-Policies
├── 07-Configuration-Profiles
├── 08-Device-Management
├── 09-Monitoring-and-Reports
└── 10-Troubleshooting-Scenarios
```

---

# Repository Statistics

| Metric | Value |
|---------|------:|
| Chapters | 10 |
| Screenshots | 60+ |
| Hands-on Exercises | 10 |
| Managed Platform | Android Enterprise |
| Documentation Format | Markdown |
| Project Status | ✅ Completed |

---

# Chapter Overview

## 01 – Creating the Intune Lab Environment

The repository begins by creating a dedicated Microsoft Intune laboratory using an existing Microsoft 365 tenant. In this chapter, I activate a Microsoft Intune Plan 1 Trial subscription, review the licensing requirements and verify that the Microsoft Intune Admin Center is available for endpoint administration.

### Topics covered

- Microsoft Intune overview
- Microsoft cloud architecture
- Licensing requirements
- Microsoft Intune Plan 1 Trial
- Creating the trial subscription
- Using an existing Microsoft 365 tenant
- Verifying the subscription
- Opening the Microsoft Intune Admin Center

### Skills developed

- Microsoft cloud administration
- Tenant provisioning
- Microsoft Intune licensing
- Endpoint management fundamentals

---

## 02 – Intune Administration Center Overview

Before managing endpoints, it is essential to understand the layout of the Microsoft Intune Admin Center. This chapter introduces the primary administrative areas used throughout the remainder of the repository, providing an overview of the portal and its key management features.

### Topics covered

- Dashboard
- Devices
- Users
- Groups
- Applications
- Reports
- Tenant Administration

### Skills developed

- Portal navigation
- Microsoft Intune administration
- Endpoint management concepts
- Administrative interface familiarisation

---

## 03 – User and Group Preparation

Microsoft Intune relies on Microsoft Entra ID for user identities and Security Groups. This chapter reviews the existing users and Security Groups created during the Microsoft Entra ID laboratory and confirms that the environment is correctly prepared for device enrolment and policy assignment.

### Topics covered

- Microsoft Entra ID users
- Microsoft Intune subscription verification
- Security Groups
- Group membership
- Administrative roles
- Environment readiness

### Skills developed

- Identity management
- Security Group administration
- Microsoft Entra ID integration
- Administrative planning

---

## 04 – Android Device Enrolment

This chapter demonstrates the enrolment of a physical Android smartphone using the **Personally-Owned Work Profile (BYOD)** deployment model. Microsoft Company Portal is used to register the device, create the Android Enterprise Work Profile and establish communication with Microsoft Intune.

### Topics covered

- Android Enterprise enrolment methods
- Microsoft Company Portal
- Device registration
- Android Work Profile creation
- Device synchronisation
- Device properties
- Compliance verification

### Skills developed

- Android Enterprise administration
- Device enrolment
- BYOD deployment
- Mobile Device Management (MDM)

---

## 05 – Deploying Android Applications with Managed Google Play

Applications are deployed to the enrolled Android Enterprise device using Managed Google Play. This chapter demonstrates how enterprise applications are approved, synchronised and assigned through Microsoft Intune before verifying successful deployment on the managed device.

### Topics covered

- Managed Google Play
- Connecting Google Play
- Approving applications
- Synchronising applications
- Application assignments
- Installation verification

### Skills developed

- Mobile Application Management (MAM)
- Application deployment
- Managed Google Play administration
- Android application lifecycle management

---

## 06 – Compliance Policies

Compliance Policies are one of the core security features within Microsoft Intune. In this chapter, I create and deploy an Android Enterprise Compliance Policy to evaluate whether enrolled devices meet the organisation's security requirements. The policy is then assigned, synchronised and verified using the enrolled Android device.

### Topics covered

- Compliance Policy overview
- Android Enterprise Compliance Policies
- Creating a Compliance Policy
- Configuring compliance settings
- Policy assignments
- Device synchronisation
- Compliance verification

### Skills developed

- Endpoint compliance management
- Security policy administration
- Android Enterprise compliance
- Microsoft Intune policy deployment

---

## 07 – Configuration Profiles

Configuration Profiles enable administrators to standardise device settings across managed endpoints. This chapter demonstrates how to create and deploy an Android Enterprise Device Restrictions profile, assign it to a Security Group and verify that the profile has been successfully delivered to the enrolled device.

### Topics covered

- Configuration Profile overview
- Android Enterprise Device Restrictions
- Creating a Configuration Profile
- Device restriction settings
- Policy assignments
- Profile deployment
- Deployment verification

### Skills developed

- Configuration Profile administration
- Device configuration management
- Android Enterprise device restrictions
- Policy deployment and validation

---

## 08 – Device Management

After devices have been enrolled and configured, administrators must manage them throughout their lifecycle. This chapter explores the day-to-day management capabilities available within Microsoft Intune, including reviewing enrolled devices, examining hardware information, performing remote administrative actions and managing individual Android Enterprise devices.

### Topics covered

- Managed device overview
- Device inventory
- Device properties
- Hardware information
- Remote device actions
- Managed applications
- Device lifecycle management

### Skills developed

- Endpoint administration
- Device lifecycle management
- Remote device management
- Android Enterprise administration

---

## 09 – Monitoring and Reports

Monitoring is essential for verifying that applications, Compliance Policies and Configuration Profiles have been successfully deployed. This chapter explores the reporting capabilities available within Microsoft Intune and demonstrates how administrators can monitor device compliance, application deployment and the health of managed Android Enterprise devices.

### Topics covered

- Reports workspace
- Device Compliance reports
- Configuration Profile monitoring
- Application deployment monitoring
- Managed device monitoring
- Device-level compliance reporting

### Skills developed

- Microsoft Intune monitoring
- Reporting and diagnostics
- Compliance reporting
- Deployment validation
- Endpoint monitoring

---

## 10 – Troubleshooting Scenarios

The repository concludes with a practical troubleshooting chapter based on issues encountered while building the laboratory. Rather than using simulated examples, this chapter documents real Microsoft Intune administration scenarios, demonstrating how to investigate reporting delays, verify Compliance Policies, troubleshoot Managed Applications and perform manual device synchronisation.

### Topics covered

- Troubleshooting methodology
- Device investigation
- Compliance validation
- Managed Application troubleshooting
- Manual device synchronisation
- Verifying successful remediation

### Skills developed

- Microsoft Intune troubleshooting
- Root cause analysis
- Endpoint diagnostics
- Application deployment troubleshooting
- Operational support

---

# Learning Outcomes

By completing this repository, I gained practical experience across the complete Android Enterprise administration lifecycle using Microsoft Intune.

The key learning outcomes include:

- Understanding the architecture of Microsoft Intune and its integration with Microsoft Entra ID and Microsoft 365.
- Configuring a Microsoft Intune tenant using Microsoft Intune Plan 1.
- Navigating the Microsoft Intune Admin Center and understanding its administrative structure.
- Preparing Microsoft Entra ID users and Security Groups for endpoint management.
- Enrolling Android Enterprise devices using the Personally-Owned Work Profile (BYOD) deployment model.
- Deploying Android applications through Managed Google Play.
- Creating and assigning Compliance Policies to managed devices.
- Deploying Configuration Profiles to standardise Android Enterprise settings.
- Managing enrolled devices throughout their lifecycle using Microsoft Intune.
- Monitoring compliance, application deployment and device health through Microsoft Intune reports.
- Applying a structured troubleshooting methodology to investigate and resolve common administration issues.
- Producing professional technical documentation suitable for a GitHub portfolio.

---

# Repository Prerequisites

To reproduce this laboratory, the following components are recommended:

- Microsoft 365 tenant
- Microsoft Entra ID tenant
- Microsoft Intune Plan 1 Trial (or equivalent licence)
- Global Administrator account
- Android smartphone compatible with Android Enterprise
- Internet connection
- Microsoft Company Portal
- Managed Google Play
- Modern web browser

Although the laboratory uses a trial subscription, the administrative workflows demonstrated throughout this repository are directly applicable to production Microsoft Intune environments.

---

# Related Repositories

This repository forms part of my Microsoft Cloud Administration learning portfolio and builds upon the previous projects:

- **TechLab – Microsoft 365 Administration Portfolio**
- **TechLab – Microsoft Entra ID Administration Portfolio**
- **TechLab – Microsoft Intune Administration Portfolio** *(this repository)*

Together, these repositories demonstrate the progression from Microsoft 365 tenant administration and identity management through to modern endpoint management using Microsoft Intune.

---

# Conclusion

This repository documents the complete lifecycle of managing Android Enterprise devices using Microsoft Intune, from preparing the cloud environment through to monitoring and troubleshooting managed endpoints.

By combining Microsoft Entra ID, Microsoft Intune and Android Enterprise, I created a practical laboratory that demonstrates the day-to-day responsibilities of an Endpoint Administrator working within a modern Microsoft cloud environment.

Rather than focusing solely on product features, the repository follows a structured administrative workflow, showing how devices are enrolled, applications are deployed, security policies are enforced, configuration settings are applied, devices are monitored and operational issues are investigated using Microsoft Intune.

Completing this project has strengthened my understanding of enterprise endpoint management while reinforcing best practices for technical documentation and GitHub portfolio development.

---

## Author

**Antonio Gabriele Rizzo**

GitHub Portfolio – Microsoft Cloud Administration Learning Series

- Microsoft 365 Administration
- Microsoft Entra ID Administration
- Microsoft Intune Administration

---

## License

This project is published for educational and portfolio purposes.

The documentation is based on hands-on experience gained while building a Microsoft Intune laboratory using Microsoft Intune Plan 1, Microsoft Entra ID and Android Enterprise.

Microsoft, Microsoft Intune, Microsoft Entra ID, Microsoft 365 and Android Enterprise are trademarks of their respective owners.
