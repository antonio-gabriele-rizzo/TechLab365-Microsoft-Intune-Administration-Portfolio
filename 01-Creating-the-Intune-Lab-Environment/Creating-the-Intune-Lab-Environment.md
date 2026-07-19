# Creating the Intune Lab Environment

## Introduction

Microsoft Intune is Microsoft's cloud-based endpoint management solution that enables organisations to manage and secure Windows, macOS, Android and iOS devices from a single administration portal.

In this chapter, I created a Microsoft Intune laboratory by adding a **Microsoft Intune Plan 1 Trial** to my existing **TechLab Microsoft 365** tenant, which had already been configured in my previous Microsoft 365 and Microsoft Entra ID repositories.

Rather than creating a separate Microsoft 365 tenant solely for Microsoft Intune, I decided to continue using my existing environment. This approach provided a more realistic enterprise deployment while allowing Microsoft Intune to integrate immediately with Microsoft Entra ID, existing user accounts and Microsoft 365 services.

During the preparation of this laboratory, I also discovered an additional prerequisite that had not been identified during the initial planning phase. Before Android Enterprise devices could be enrolled successfully, Microsoft Intune required a connection to Managed Google Play. This configuration became an important part of the laboratory and has therefore been included within this chapter to ensure the environment can be reproduced successfully.

This environment will be used throughout the remainder of this portfolio as I continue to configure users, groups, Android Enterprise, compliance policies, configuration profiles, application deployment, endpoint security and device management.

---

# Objectives

By completing this chapter, I learned how to:

- Understand the purpose of Microsoft Intune.
- Verify the licensing requirements.
- Activate Microsoft Intune Plan 1 Trial.
- Integrate Microsoft Intune with an existing Microsoft 365 tenant.
- Verify that the subscription had been provisioned successfully.
- Access the Microsoft Intune Admin Center.
- Configure Managed Google Play for Android Enterprise.
- Prepare the laboratory for the remaining practical exercises.

---

# Prerequisites

Before beginning this chapter, I ensured that the following prerequisites had already been completed:

- Microsoft 365 Business tenant
- Global Administrator permissions
- Microsoft Entra ID configured
- Internet connectivity
- Supported web browser

Because this laboratory builds upon my previous Microsoft 365 and Microsoft Entra ID repositories, the tenant, administrative accounts and licensing were already available before Microsoft Intune was introduced.

---

# What is Microsoft Intune?

Microsoft Intune is Microsoft's cloud-based **Mobile Device Management (MDM)** and **Mobile Application Management (MAM)** solution.

It enables administrators to manage devices from a single cloud-based administration platform without relying on traditional on-premises infrastructure.

Using Microsoft Intune, I can:

- Enrol organisational devices.
- Deploy applications.
- Configure security policies.
- Create compliance policies.
- Perform remote device management.
- Monitor managed devices.
- Secure corporate data across multiple platforms.

Microsoft Intune integrates directly with Microsoft Entra ID and Microsoft 365 to provide a modern cloud-based endpoint management solution.

This integration enables user identities, licences, devices and security policies to operate together as part of Microsoft's cloud ecosystem.

---

# Microsoft Cloud Architecture

The TechLab environment uses the following Microsoft cloud architecture:

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

Microsoft 365 provides the productivity services used throughout the organisation.

Microsoft Entra ID provides identity management, authentication and authorisation.

Microsoft Intune provides centralised endpoint management by applying security policies, compliance rules and configuration settings to managed devices.

This layered architecture allows identities, productivity services and endpoint management to work together as a single cloud-based solution.

---

# Licensing Requirements

Microsoft Intune requires an appropriate Microsoft licence before devices can be enrolled and managed.

Microsoft Intune can be licensed either as a standalone product or as part of selected Microsoft 365 subscriptions.

Common licensing options include:

- Microsoft Intune Plan 1
- Microsoft Intune Plan 2 *(advanced add-on features)*
- Microsoft 365 Business Premium
- Microsoft 365 E3
- Microsoft 365 E5

For this laboratory, I activated **Microsoft Intune Plan 1 Trial**.

The trial provides all of the functionality required to build a practical Microsoft Intune laboratory while allowing every exercise within this repository to be completed without requiring an Enterprise subscription.

---

# Creating the Microsoft Intune Trial

To begin the deployment, I opened the Microsoft Intune Trial page using my web browser.

I then signed in using my existing Microsoft 365 Global Administrator account that had previously been configured for the TechLab365 tenant.

Because the tenant already existed, Microsoft recognised the environment and prepared the trial for activation without requiring any additional tenant configuration.

![Microsoft Intune Trial Sign-up](screenshots/intune-trial-signup-page.png)

---

# Using an Existing Microsoft 365 Tenant

After signing in, Microsoft detected my existing TechLab365 Microsoft 365 tenant automatically.

Rather than creating a new environment, I continued using the existing tenant because it already contained Microsoft Entra ID, administrative accounts and the Microsoft 365 configuration completed in my previous repositories.

Using the existing tenant also meant that Microsoft Intune could integrate immediately with Microsoft Entra ID and existing cloud identities, creating a much more realistic enterprise deployment.

![Existing Microsoft 365 Tenant](screenshots/intune-existing-tenant-account.png)

---

# Selecting Microsoft Intune Plan 1 Trial

Microsoft displayed the available subscription options that could be activated within the tenant.

For this laboratory, I selected:

```text
Microsoft Intune Plan 1 (Trial)
```

This subscription provides the core Microsoft Intune functionality required to complete every practical exercise within this repository, including device enrolment, compliance policies, configuration profiles, application deployment and endpoint security.

![Microsoft Intune Plan 1 Trial](screenshots/intune-trial-selection.png)

---

# Configuring Renewal Settings

Before activating the trial, I reviewed the subscription settings presented by Microsoft.

For this laboratory, the following configuration was used:

| Setting | Value |
|---------|-------|
| Licence Quantity | 1 |
| Subscription Length | 1 Month |
| Billing Frequency | Monthly |

After reviewing the configuration, I ensured that recurring billing would not continue after the evaluation period so that the subscription would expire automatically once the trial had finished.

This prevented unexpected charges while still allowing sufficient time to complete the Microsoft Intune laboratory.

![Renewal Settings](screenshots/intune-trial-renewal-settings.png)

---

# Activating the Trial

After reviewing the subscription settings, I activated the Microsoft Intune Plan 1 Trial by selecting **Start Free Trial**.

Microsoft processed the request and began provisioning the Microsoft Intune service within my existing Microsoft 365 tenant. The activation process only took a few moments before the confirmation screen appeared, indicating that the trial had been successfully added.

At this stage, Microsoft automatically associated the licence with my tenant, making Microsoft Intune available alongside the existing Microsoft 365 services.

Successfully activating the trial completed the licensing stage of the deployment and allowed me to continue configuring the Microsoft Intune environment.

![Microsoft Intune Trial Activated](screenshots/intune-trial-activated.png)

---

# Verifying the Subscription

After the activation process had completed, I returned to the Microsoft 365 Admin Center to verify that the Microsoft Intune subscription had been added successfully.

From the navigation menu, I opened:

```text
Billing
    └── Your products
```

The **Microsoft Intune Plan 1 Trial** subscription appeared alongside the existing Microsoft 365 subscriptions, confirming that the licence had been provisioned correctly.

Performing this verification before continuing was an important step, as it confirmed that Microsoft Intune had been successfully associated with the tenant and was ready for use.

![Products Overview](screenshots/intune-products-overview.png)

---

# Opening Microsoft Intune Admin Center

Once the subscription had been activated successfully, I accessed the Microsoft Intune Admin Center.

There are several ways to access the administration portal.

### Method 1

Open the Microsoft 365 Admin Center:

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

Alternatively, Microsoft Intune can be accessed directly by browsing to:

```text
https://intune.microsoft.com
```

During this laboratory, I discovered that Microsoft Intune was not immediately available after activating the trial. Microsoft required several minutes to complete the provisioning process before the service appeared within the list of available Admin Centers.

Once provisioning had completed, the Microsoft Intune Admin Center opened successfully and displayed the main administration dashboard, confirming that the service was fully operational.

> **Note**
>
> Although the subscription becomes active almost immediately, Microsoft may require a short period to provision the Intune service. During this time, the Microsoft Intune Admin Center may not appear within the Microsoft 365 Admin Centers list.

![Microsoft Intune Admin Center](screenshots/intune-admin-center-home.png)

---

# Configuring Managed Google Play

Before I could begin enrolling Android Enterprise devices, I needed to configure **Managed Google Play**.

Although Microsoft Intune had been activated successfully, Android Enterprise management could not be used until Microsoft Intune had been connected to Google's Android Enterprise services.

While configuring this integration, I initially attempted to register Managed Google Play by using the tenant's default **onmicrosoft.com** account.

During testing, I discovered that this approach was unsuitable because the registration process required a Google account capable of completing the Android Enterprise association.

To resolve the issue, I repeated the registration using my **TechLab365 organisational email address**, which allowed the Managed Google Play tenant to be created successfully.

Once the registration had completed, Microsoft Intune established a trusted connection with Google's Android Enterprise services.

This immediately enabled Android Enterprise functionality within Microsoft Intune, allowing Android devices to be enrolled during the following chapters of this repository.

This became an important lesson learned during the project because it had not been identified during the original planning of the laboratory. Without completing this configuration, Android Enterprise enrolment cannot proceed successfully.

![Managed Google Play Registration](screenshots/intune-managed-google-play-registration.png)

![Managed Google Play Connected](screenshots/intune-managed-google-play-connected.png)

> **Lessons Learned**
>
> During the initial configuration, I assumed that the tenant's default **onmicrosoft.com** account could be used to register Managed Google Play. Testing quickly demonstrated that a suitable Google account was required to complete the Android Enterprise association successfully.
>
> Resolving this issue using my TechLab365 organisational email address highlighted the importance of validating prerequisites during a real deployment rather than relying solely on planning documentation.

---

# Key Learnings

Completing this chapter provided a solid understanding of how Microsoft Intune integrates with the wider Microsoft cloud ecosystem and highlighted the importance of preparing the environment correctly before attempting to manage devices.

The key lessons learned were:

- Microsoft Intune provides cloud-based endpoint management for Windows, macOS, Android and iOS devices.
- Microsoft Intune integrates directly with Microsoft Entra ID to provide identity-driven device management.
- An appropriate Microsoft licence is required before Intune services become available.
- Microsoft Intune Plan 1 provides all of the core functionality required for this laboratory.
- A trial subscription can be added to an existing Microsoft 365 tenant without creating a separate environment.
- Microsoft Intune may require several minutes to complete the provisioning process after the trial has been activated.
- The Microsoft Intune Admin Center is the primary portal used to manage users, devices, applications and security policies.
- Android Enterprise cannot be configured until Managed Google Play has been connected successfully.
- Validating prerequisites during a deployment is just as important as completing the configuration itself.
- Documenting unexpected issues and their resolutions improves both troubleshooting and future deployments.

---

# Skills Demonstrated

During this chapter, I demonstrated the following practical skills:

- Understanding Microsoft Intune architecture.
- Evaluating Microsoft licensing requirements.
- Activating Microsoft Intune Plan 1 Trial.
- Integrating Microsoft Intune with an existing Microsoft 365 tenant.
- Verifying cloud service provisioning.
- Accessing and navigating the Microsoft Intune Admin Center.
- Configuring Managed Google Play.
- Preparing Android Enterprise for device enrolment.
- Troubleshooting cloud service configuration.
- Producing professional technical documentation using Markdown and GitHub.

---

# Chapter Summary

In this chapter, I successfully prepared the Microsoft Intune laboratory environment that will be used throughout the remainder of this repository.

Rather than deploying Microsoft Intune within a new tenant, I integrated the service into my existing TechLab365 Microsoft 365 environment. This approach allowed me to continue building upon the Microsoft Entra ID configuration that had already been completed while creating a realistic enterprise administration environment.

The Microsoft Intune Plan 1 Trial was activated successfully and the subscription was verified within the Microsoft 365 Admin Center before accessing the Microsoft Intune Admin Center for the first time.

During the preparation of the laboratory, I also discovered that Android Enterprise enrolment requires a successful Managed Google Play connection before Android devices can be managed. Documenting this configuration as part of the environment preparation ensures that future deployments can be reproduced without encountering the same issue.

By the end of this chapter, the following tasks had been completed successfully:

- Activated Microsoft Intune Plan 1 Trial.
- Verified the Microsoft Intune subscription.
- Confirmed successful provisioning of the Microsoft Intune service.
- Accessed the Microsoft Intune Admin Center.
- Connected Microsoft Intune to Managed Google Play.
- Prepared the environment for Android Enterprise.
- Verified that the laboratory was ready for device enrolment.

With the Microsoft Intune environment fully prepared, the next chapter introduces the Microsoft Intune Admin Center in greater detail, exploring the main administrative areas before continuing with user preparation, device enrolment and endpoint management.

