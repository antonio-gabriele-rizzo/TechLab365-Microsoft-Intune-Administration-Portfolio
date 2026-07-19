# Creating the Intune Lab Environment

## Introduction

Microsoft Intune is Microsoft's cloud-based endpoint management solution that enables organisations to securely manage Windows, macOS, Android and iOS devices from a single administration platform.

For this portfolio, I used the existing **TechLab Microsoft 365** tenant that was previously created throughout my Microsoft 365 and Microsoft Entra ID repositories. Rather than creating a new tenant, I extended the existing environment by activating a **Microsoft Intune Plan 1 Trial**, allowing all Microsoft cloud services to remain integrated within the same laboratory.

Building the laboratory in this way more accurately reflects how Microsoft Intune is introduced into an existing organisation. Instead of deploying a completely separate environment, organisations typically add Intune to an established Microsoft 365 tenant so that identities, licences and cloud services work together.

This chapter documents the complete process of preparing the Intune laboratory, activating the trial subscription, verifying the licence, accessing the Microsoft Intune Admin Center and completing the additional configuration required before Android Enterprise devices can be managed.

The completed laboratory will be used throughout the remaining chapters of this repository.

---

# Objectives

By completing this chapter, I achieved the following objectives:

- Understood the purpose of Microsoft Intune.
- Reviewed the licensing requirements for Microsoft Intune.
- Activated a Microsoft Intune Plan 1 Trial.
- Added Intune to an existing Microsoft 365 tenant.
- Verified that the subscription had been successfully provisioned.
- Accessed the Microsoft Intune Admin Center.
- Configured the Managed Google Play connector for Android Enterprise.
- Prepared the environment for the remaining laboratory exercises.

---

# Prerequisites

Before beginning this chapter, the following prerequisites were already in place:

- An existing Microsoft 365 tenant.
- Microsoft Entra ID configured.
- Global Administrator permissions.
- Internet connectivity.
- A supported web browser.
- Completion of the previous Microsoft 365 and Microsoft Entra ID repositories.

---

# Understanding Microsoft Intune

Microsoft Intune is Microsoft's cloud-based endpoint management platform that combines **Mobile Device Management (MDM)** and **Mobile Application Management (MAM)** capabilities.

It enables administrators to manage both corporate-owned and personally owned devices while enforcing organisational security policies and protecting company data.

Unlike traditional on-premises management solutions, Intune is delivered entirely as a cloud service. Administrators can configure devices, deploy applications, enforce compliance policies and monitor enrolled devices without maintaining management servers within their own infrastructure.

Throughout this repository, Microsoft Intune will be used to:

- Enrol Windows devices.
- Configure device compliance policies.
- Deploy applications.
- Configure device restrictions.
- Manage Windows Update policies.
- Protect organisational data.
- Monitor managed devices.

---

# Microsoft Cloud Architecture

The laboratory environment is built using Microsoft's cloud ecosystem.

```text
Microsoft 365
      │
      ▼
Microsoft Entra ID
      │
      ▼
Microsoft Intune
      │
 ┌────┴────┐
 │         │
Windows  Android
```

Each Microsoft cloud service performs a specific role within the environment.

**Microsoft 365** provides productivity services such as Exchange Online, SharePoint Online and Microsoft Teams.

**Microsoft Entra ID** provides identity management, authentication and access control.

**Microsoft Intune** provides endpoint management by controlling devices, applications and security policies.

Keeping all three services within the same tenant simplifies administration and allows them to integrate seamlessly.

---

# Licensing Requirements

Before Microsoft Intune can be used, an appropriate licence must be assigned to the tenant.

Microsoft provides several licensing options depending on organisational requirements.

Common licensing options include:

- Microsoft Intune Plan 1
- Microsoft Intune Plan 2
- Microsoft 365 Business Premium
- Microsoft 365 E3
- Microsoft 365 E5

For this laboratory I selected **Microsoft Intune Plan 1 Trial**.

The trial provides sufficient functionality to complete every practical exercise included within this repository while avoiding additional licensing costs.

---

# Creating the Microsoft Intune Trial

To begin building the laboratory, I opened the Microsoft Intune Trial page and signed in using the existing Global Administrator account from my TechLab Microsoft 365 tenant.

Using the existing tenant meant that Microsoft Intune could integrate directly with Microsoft Entra ID without requiring any additional tenant configuration.

![Microsoft Intune Trial Sign-up](screenshots/intune-trial-signup-page.png)

After signing in, Microsoft recognised that an existing Microsoft 365 tenant was already associated with the account.

Instead of creating a new environment, I chose to continue using the existing tenant that had already been configured during the previous repositories.

This approach keeps all Microsoft cloud services together within a single administrative environment and more closely reflects how Microsoft Intune would normally be introduced into an existing organisation.

![Existing Microsoft 365 Tenant](screenshots/intune-existing-tenant-account.png)

Microsoft then presented the available subscription options.

For this laboratory I selected **Microsoft Intune Plan 1 Trial**, which provides the core endpoint management capabilities required throughout the remainder of this portfolio.

![Microsoft Intune Plan 1 Trial](screenshots/intune-trial-selected.png)

Before activating the subscription, Microsoft displayed the renewal settings.

The trial was configured using the following options.

| Setting | Value |
|---------|-------|
| Licence Quantity | 1 |
| Subscription Length | 1 Month |
| Billing Frequency | Monthly |

After activating the subscription, I disabled recurring billing to ensure that the trial would expire automatically rather than converting into a paid subscription.

![Renewal Settings](screenshots/intune-trial-renewal-settings.png)

Once the configuration had been reviewed, I selected **Start Free Trial**.

Microsoft provisioned the licence and confirmed that the Microsoft Intune Plan 1 Trial had been successfully added to the tenant.

At this point, the licensing requirements for Microsoft Intune had been completed successfully.

![Microsoft Intune Trial Activated](screenshots/intune-trial-activated.png)

---

# Verifying the Subscription

After the trial had been activated, I verified that the subscription had been successfully added to the Microsoft 365 tenant.

From the Microsoft 365 Admin Center, I navigated to:

```text
Billing
    └── Your products
```

The list of subscriptions now included **Microsoft Intune Plan 1 Trial**, confirming that the licence had been provisioned successfully.

Verifying the subscription before continuing was an important step because Microsoft Intune services are not available until the licence has been assigned correctly to the tenant.

This also confirmed that the tenant was now licensed to use Microsoft Intune throughout the remainder of this repository.

![Products Overview](screenshots/intune-products-overview.png)

---

# Opening the Microsoft Intune Admin Center

Once the licence had been successfully provisioned, I accessed the Microsoft Intune Admin Center.

There are two methods of opening the administration portal.

### Method 1

Access the Microsoft 365 Admin Center.

```text
https://admin.microsoft.com
```

Then navigate to:

```text
Show all
    └── Admin centers
            └── Microsoft Intune
```

### Method 2

Open the Microsoft Intune Admin Center directly.

```text
https://intune.microsoft.com
```

During my laboratory build, Microsoft required several minutes to provision the new service before Microsoft Intune appeared within the list of available Admin Centers.

This delay is normal when a new Intune subscription is first activated.

Once provisioning had completed, the Microsoft Intune Admin Center loaded successfully and displayed the default administration dashboard.

This confirmed that the Intune environment had been created correctly and was ready for further configuration.

![Microsoft Intune Admin Center](screenshots/intune-admin-center-home.png)

---

# Configuring Managed Google Play

Although the Microsoft Intune environment was now operational, I discovered that the Android Enterprise components had not yet been configured.

Microsoft Intune can manage Android Enterprise devices only after a connection has been established with **Managed Google Play**.

Without this configuration, Android Enterprise enrolment, managed Google Play applications and Android work profiles cannot be deployed.

To verify the current configuration, I navigated to:

```text
Tenant administration
    └── Connectors and tokens
            └── Managed Google Play
```

The portal confirmed that the Managed Google Play connector had been configured successfully.

The page displayed a **Success** status together with the most recent synchronisation time, confirming that communication between Microsoft Intune and Google's enterprise management platform had been established.

This integration enables Microsoft Intune to synchronise approved Android applications, deploy managed Google Play apps to enrolled devices and support Android Enterprise management throughout the remainder of this laboratory.

Completing this configuration ensured that both Windows and Android device management capabilities were fully available before continuing with the subsequent chapters.

![Managed Google Play Connected](screenshots/managed-google-play-connected.png)

---

# Key Learnings

Throughout this chapter, I developed a practical understanding of how Microsoft Intune integrates into the wider Microsoft cloud ecosystem.

The key learning outcomes included:

- Understanding the purpose of Microsoft Intune.
- Reviewing Microsoft Intune licensing options.
- Activating a Microsoft Intune Plan 1 Trial.
- Extending an existing Microsoft 365 tenant rather than creating a new environment.
- Verifying that the Intune subscription had been successfully provisioned.
- Accessing the Microsoft Intune Admin Center.
- Understanding the provisioning delay that occurs after activating a new Intune subscription.
- Configuring the Managed Google Play connector for Android Enterprise.
- Preparing the laboratory for Windows and Android device management.

---

# Skills Demonstrated

During this chapter, I demonstrated the following technical skills:

- Microsoft Intune tenant deployment.
- Microsoft 365 licence management.
- Microsoft cloud service integration.
- Microsoft Intune administration.
- Android Enterprise preparation.
- Managed Google Play integration.
- Microsoft 365 administration.
- Technical documentation using GitHub and Markdown.

---

# Chapter Summary

In this chapter, I successfully created the Microsoft Intune laboratory by extending my existing Microsoft 365 tenant with a Microsoft Intune Plan 1 Trial.

I verified that the subscription had been successfully provisioned, confirmed access to the Microsoft Intune Admin Center and completed the additional Managed Google Play configuration required to support Android Enterprise devices.

By the end of this chapter, the laboratory environment was fully prepared for the remaining exercises within this repository, providing a solid foundation for managing Windows and Android devices using Microsoft Intune.

The next chapter introduces the Microsoft Intune Admin Center in greater detail and explores the primary administrative areas used to manage users, devices, applications, security and endpoint configuration.

