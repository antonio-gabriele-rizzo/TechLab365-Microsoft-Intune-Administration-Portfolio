# 08 – Device Management

## Introduction

After enrolling an Android Enterprise device into Microsoft Intune, the next stage of the device lifecycle is ongoing management. Whilst enrolment establishes the management relationship between the device and the Intune service, administrators must also be able to monitor device health, review inventory information, verify policy deployment and perform remote administrative actions throughout the lifetime of the managed endpoint.

Microsoft Intune provides a comprehensive Device Management interface that centralises information relating to enrolled devices. From a single location, administrators can review hardware details, operating system information, compliance status, deployed applications, assigned policies and available remote management actions. This centralised approach simplifies endpoint administration whilst allowing organisations to maintain visibility across their managed device estate.

During this laboratory, I explored the management capabilities available for my Android Enterprise Personally-Owned Work Profile device. I reviewed the device overview, examined the available management and monitoring features, verified that the Configuration Profile created in the previous chapter had been successfully assigned to the device and performed a manual synchronisation between the device and Microsoft Intune.

Although the management experience differs between Personally-Owned Work Profile, Corporate-Owned Work Profile and Fully Managed Android Enterprise devices, the concepts demonstrated throughout this chapter form the foundation of day-to-day Microsoft Intune administration.

---

# Objectives

After completing this chapter, I will be able to:

- Navigate the Microsoft Intune Device Management interface.
- Review information collected from an enrolled Android Enterprise device.
- Understand the purpose of the Device Overview page.
- Perform remote management actions from Microsoft Intune.
- Monitor device inventory and configuration information.
- Verify Configuration Profile assignments.
- Synchronise an Android Enterprise device with Microsoft Intune.
- Explain the role of Device Management within the Microsoft Intune administration lifecycle.

---

# Prerequisites

Before starting this chapter, I had already completed:

- Chapter 01 – Creating the Intune Lab Environment
- Chapter 02 – Intune Administration Center Overview
- Chapter 03 – User and Group Preparation
- Chapter 04 – Android Device Enrolment
- Chapter 05 – Deploying Android Applications with Managed Google Play
- Chapter 06 – Compliance Policies
- Chapter 07 – Configuration Profiles

In addition, the following components were already configured:

- Microsoft Intune tenant
- Android Enterprise connector
- Personally-Owned Android Enterprise device
- Microsoft Company Portal
- Android Test Users Security Group
- Successful Android Enterprise enrolment
- Managed Google Play integration
- Android Device Restrictions Configuration Profile

---

# Understanding Device Management

Once a device has been enrolled into Microsoft Intune, administrators require a central location from which they can manage and monitor that device throughout its operational lifecycle. The Device Management workspace provides this functionality by consolidating information relating to hardware, software, policy deployment, compliance and remote administrative actions.

Rather than configuring policies directly, Device Management focuses on monitoring the current state of enrolled devices and providing administrators with tools to investigate issues, verify successful deployments and perform operational tasks remotely.

Common activities performed within the Device Management workspace include:

- Reviewing device inventory.
- Monitoring compliance status.
- Viewing installed applications.
- Checking deployed Configuration Profiles.
- Synchronising devices with Microsoft Intune.
- Performing remote administrative actions.
- Reviewing hardware and operating system information.

These capabilities allow administrators to maintain visibility across managed devices whilst reducing the need for direct physical access. In enterprise environments, this centralised management model enables IT departments to support users regardless of their geographical location, improving operational efficiency and reducing support costs.

For Android Enterprise Personally-Owned Work Profile devices, Microsoft Intune manages only the corporate work profile. Consequently, administrators can monitor and manage corporate resources without accessing personal applications, photographs, messages or other private user data. This separation remains one of the key security and privacy benefits of the Android Enterprise Work Profile deployment model.

---

To begin reviewing the enrolled Android Enterprise device, navigate to:

```text
Microsoft Intune Admin Center

Devices
    └── All devices
```

From the list of enrolled devices, select the Android Enterprise device that was enrolled during Chapter 04.

![Android Device Overview](screenshots/android-device-overview.png)

---

# Reviewing the Device Overview

After selecting the enrolled Android Enterprise device from **Devices > All devices**, Microsoft Intune opens the **Overview** page. This page provides administrators with a consolidated summary of the device's current state and acts as the primary management dashboard for the selected endpoint.

Rather than navigating through multiple menus, administrators can immediately determine whether the device is healthy, compliant and communicating successfully with the Intune service.

During my laboratory, the Overview page displayed information including:

- Device name
- Management name
- Ownership
- Compliance status
- Device manufacturer
- Device model
- Operating system
- Primary user
- Enrolment information
- Last successful check-in time

In addition to the device information, the Overview page also provides quick access to several remote administrative actions that can be performed directly from Microsoft Intune.

These actions include:

- **Retire** – Removes corporate data whilst leaving personal data intact.
- **Wipe** – Performs a factory reset on supported devices.
- **Delete** – Removes the device record from Microsoft Intune.
- **Remote lock** – Locks the device remotely.
- **Sync** – Forces the device to check in immediately with Microsoft Intune.
- **Reset passcode** – Resets the work profile passcode when supported.

The availability of these actions depends on both the Android Enterprise enrolment method and the capabilities supported by the device. Personally-Owned Work Profile devices intentionally expose fewer administrative actions than Fully Managed or Corporate-Owned devices in order to preserve user privacy.

The lower section of the Overview page also displays the **Device actions status** table. This area records remote actions initiated by administrators, allowing confirmation that management operations have completed successfully.

In my environment, no remote actions had yet been executed, so the Device actions status section was empty.

![Android Device Overview](screenshots/android-device-overview.png)

---

## Understanding the Device Overview Information

Although the Overview page appears relatively simple, each item provides valuable operational information.

### Ownership

The **Ownership** field identifies whether the device is classified as:

- Personal
- Corporate

Since my Android device was enrolled using the Android Enterprise Personally-Owned Work Profile enrolment method, Microsoft Intune correctly identified the device as **Personal**.

This distinction is important because many Intune features become available only for Corporate-Owned devices.

### Compliance

The **Compliance** field immediately indicates whether the device satisfies all assigned Compliance Policies.

Because the Compliance Policy created in Chapter 06 had already been deployed successfully, the device reported a status of **Compliant**.

This status is particularly important when organisations implement Conditional Access policies, as only compliant devices may be permitted to access corporate resources such as Microsoft 365 services.

### Last Check-in

One of the most useful operational indicators is the **Last check-in time**.

Each time an enrolled device communicates with Microsoft Intune, the service records the latest successful synchronisation time.

Administrators frequently use this value when troubleshooting because it confirms whether:

- the device is online;
- Intune communication is functioning correctly; and
- recently deployed policies are likely to have been received.

Devices that have not checked in for an extended period often require additional investigation before administrators begin troubleshooting policy deployment issues.

---

> **Interview Tip**
>
> The **Last Check-in** timestamp is one of the first values experienced Intune administrators verify during troubleshooting. If a device has not checked in recently, new applications, Compliance Policies or Configuration Profiles cannot be expected to deploy until communication with the Intune service is restored.
>
> ---

# Reviewing Hardware Information

One of the advantages of Microsoft Intune is its ability to collect hardware and operating system information from enrolled devices automatically. This information allows administrators to maintain an accurate inventory of managed endpoints without requiring physical access to the device.

To review the hardware information, I selected:

```text
Monitor
    └── Hardware
```

The **Hardware** page displayed detailed information about my enrolled Android Enterprise device, including:

- Manufacturer
- Model
- Android version
- Operating system build
- Storage capacity
- Available storage
- Physical memory
- Serial number
- IMEI (where supported)
- Wi-Fi MAC address
- Battery information

Collecting this information centrally provides significant operational benefits. Rather than asking users to locate technical information themselves, administrators can quickly retrieve device specifications directly from Microsoft Intune.

Hardware inventory also assists with:

- Troubleshooting hardware-related issues.
- Verifying supported Android versions.
- Asset management.
- Capacity planning.
- Identifying devices approaching end of support.

For organisations managing hundreds or thousands of devices, this inventory becomes an invaluable source of information for both technical support teams and asset management processes.

![Android Device Hardware](screenshots/android-device-hardware.png)

---

# Reviewing Device Properties

After reviewing the hardware inventory, I examined the device properties.

The **Properties** page contains administrative information relating to how the device is represented within Microsoft Intune rather than describing the physical hardware itself.

Unlike the Hardware page, which focuses on technical specifications, the Properties page provides information used for administrative management and policy assignment.

The information available included:

- Device name
- Management name
- Ownership
- Device category
- Primary user
- Enrolment type
- Microsoft Entra device information
- Management status

Reviewing these properties allows administrators to confirm that devices have been enrolled using the expected method and assigned to the correct user.

This information is particularly useful when troubleshooting enrolment issues or validating that organisational naming standards have been applied consistently across managed devices.

For example, confirming that my device was enrolled as an **Android Enterprise Personally-Owned Work Profile** device verified that the correct enrolment method had been used during Chapter 04.

Similarly, reviewing the ownership information confirmed that Microsoft Intune correctly classified the device as **Personal**, ensuring that the management capabilities available matched the selected enrolment model.

![Android Device Properties](screenshots/android-device-properties.png)

---

# Verifying Configuration Profile Assignments

One of the most important administrative tasks after deploying Configuration Profiles is confirming that they have been assigned successfully.

Rather than assuming that previously created policies are targeting the correct devices, Microsoft Intune allows administrators to review all Configuration Profile assignments directly from the managed device.

This provides an additional verification step, ensuring that the intended policies are available to the enrolled endpoint.

During my laboratory, I reviewed the Configuration Profile assignments associated with the Android Enterprise device.

The assignment information confirmed that the **Android Work Profile Device Restrictions** profile created in the previous chapter had been successfully assigned to the **Android Test Users** Microsoft Entra Security Group.

Reviewing assignments in this way provides confidence that policy targeting has been configured correctly before administrators begin troubleshooting configuration or compliance issues.

In larger enterprise environments where multiple Configuration Profiles may target the same device, reviewing policy assignments is an essential troubleshooting technique because it allows administrators to identify conflicting or missing policies quickly.

![Configuration Profile Assignments](screenshots/configuration-profile-assignments.png)

---

# Synchronising the Device

Microsoft Intune periodically synchronises managed devices to ensure that the latest policies, applications and configuration changes are delivered successfully. Although this process occurs automatically at regular intervals, administrators can also initiate a manual synchronisation whenever immediate communication with the device is required.

Manual synchronisation is particularly useful after deploying:

- Configuration Profiles
- Compliance Policies
- Managed Applications
- Endpoint Security Policies

Rather than waiting for the next scheduled check-in, a manual synchronisation instructs the device to contact the Microsoft Intune service immediately and retrieve any pending updates.

To perform a manual synchronisation, I selected **Sync** from the device Overview page.

Following the synchronisation request, Microsoft Intune attempted to establish communication with the enrolled Android Enterprise device.

During my laboratory, the device synchronised successfully, updating the **Last check-in** time. However, the **Device actions status** section remained empty.

This behaviour is expected for Android Enterprise Personally-Owned Work Profile devices because Microsoft Intune does not always record manual synchronisation requests within the Device Actions history. Unlike Windows devices, Android Enterprise work profile devices often process synchronisation silently without generating an administrative action record.

Understanding this behaviour is important when troubleshooting Android Enterprise devices, as the absence of an entry within the Device Actions history does not necessarily indicate that synchronisation has failed.

Instead, administrators should verify successful communication by reviewing the **Last check-in** timestamp together with the device's compliance state.

---

# Device Management Best Practices

Throughout this laboratory, I observed several administrative practices that contribute to effective endpoint management within Microsoft Intune.

Firstly, administrators should regularly monitor device check-in times. Devices that have not communicated with Microsoft Intune for an extended period may fail to receive newly deployed policies, applications or configuration updates.

Secondly, reviewing the device overview before performing remote actions helps confirm that the correct endpoint has been selected, particularly in environments where users may own multiple managed devices.

Configuration Profile assignments should also be verified whenever new policies are deployed. Confirming that the intended Security Groups have been targeted can prevent unnecessary troubleshooting caused by incorrect policy assignments.

Finally, administrators should understand the capabilities and limitations of each Android Enterprise enrolment method. Personally-Owned Work Profile devices intentionally expose fewer management features than Corporate-Owned or Fully Managed devices in order to preserve user privacy whilst maintaining organisational control over corporate resources.

Applying these practices helps ensure that administrative tasks are performed efficiently whilst reducing the likelihood of configuration errors.

---

# Key Learnings

Throughout this chapter, I learned that:

- Microsoft Intune provides a centralised interface for managing enrolled Android Enterprise devices.
- The Device Overview page provides immediate visibility into the health and management status of an enrolled endpoint.
- Hardware inventory is collected automatically and assists with asset management and technical support.
- Device Properties provide important administrative information regarding enrolment, ownership and management.
- Configuration Profile assignments can be verified directly from the managed device.
- Manual device synchronisation accelerates policy delivery but may not always generate an entry within the Device Actions history for Android Enterprise Personally-Owned Work Profile devices.
- Understanding the differences between Android Enterprise enrolment methods is essential when performing day-to-day administration.

---

# Skills Demonstrated

Throughout this chapter, I demonstrated the following Microsoft Intune administration skills:

- Android Enterprise device administration.
- Endpoint inventory management.
- Hardware inventory review.
- Device property verification.
- Remote device management.
- Manual device synchronisation.
- Configuration Profile verification.
- Microsoft Intune troubleshooting.
- Endpoint lifecycle management.
- Technical documentation using GitHub and Markdown.

---

# Interview Tip

A common interview question for IT Support Engineers, Service Desk Analysts and Junior Endpoint Administrators is:

> **"What information would you check first when troubleshooting a managed device in Microsoft Intune?"**

A good answer would include:

- Confirm the device has checked in recently.
- Verify the compliance status.
- Review the enrolled user and ownership type.
- Confirm that the required Configuration Profiles and Compliance Policies have been assigned.
- Check whether any recent remote actions have been performed.
- Review the hardware and operating system information to ensure the device supports the deployed policies.

Demonstrating a structured troubleshooting methodology is often more valuable during an interview than simply listing Microsoft Intune features.

---

# Chapter Summary

In this chapter, I explored the Device Management capabilities available within Microsoft Intune for an Android Enterprise Personally-Owned Work Profile device.

I reviewed the Device Overview page, examined the hardware inventory collected by Microsoft Intune, inspected the device properties and verified that the Configuration Profile created in the previous chapter had been assigned successfully.

I also performed a manual synchronisation between the managed device and Microsoft Intune, observing how Android Enterprise Personally-Owned Work Profile devices report synchronisation differently from Windows devices.

This exercise demonstrated the day-to-day administrative tasks performed by Endpoint Administrators when managing Android Enterprise devices and reinforced the importance of monitoring device health, verifying policy deployment and understanding the operational lifecycle of managed endpoints.
