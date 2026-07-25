# 08 – Device Management

## Introduction

Once a device has been successfully enrolled into Microsoft Intune, the focus shifts from deployment to ongoing management. Throughout the operational life of a managed endpoint, administrators are responsible for monitoring device health, reviewing hardware information, verifying policy deployment and performing remote administrative actions when required.

Microsoft Intune provides a centralised Device Management interface that enables administrators to view all enrolled devices from a single console. From this interface, administrators can review device information, inspect hardware inventory, monitor compliance, verify assigned policies and initiate remote management actions without requiring physical access to the endpoint.

During this laboratory, I explored the management capabilities available for my Android Enterprise Personally-Owned Work Profile device. I reviewed the device inventory, examined the device overview, inspected hardware and administrative properties, and verified that the Configuration Profile created in the previous chapter had been successfully assigned to the managed device.

Although the available management capabilities vary depending on the Android Enterprise enrolment method, the concepts demonstrated throughout this chapter represent many of the day-to-day administrative tasks performed by Microsoft Intune administrators.

---

# Objectives

After completing this chapter, I will be able to:

- Understand the purpose of Device Management within Microsoft Intune.
- Navigate the Microsoft Intune Device Management interface.
- Review enrolled Android Enterprise devices.
- Examine device overview information.
- Review hardware inventory collected by Microsoft Intune.
- Understand device properties and administrative information.
- Verify Configuration Profile assignments.
- Explain the role of Device Management throughout the endpoint lifecycle.

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

Enrolling a device into Microsoft Intune establishes a management relationship between the endpoint and the Microsoft cloud. Once enrolment has been completed, administrators require a central location from which they can monitor, maintain and support managed devices throughout their lifecycle.

The **Device Management** workspace provides this functionality by bringing together operational information collected from enrolled endpoints. Rather than focusing on policy creation, this area enables administrators to verify that deployed policies are functioning correctly whilst also providing the tools required to investigate problems and perform administrative actions remotely.

Common activities performed within Device Management include:

- Reviewing enrolled devices.
- Monitoring compliance status.
- Examining hardware inventory.
- Reviewing device properties.
- Verifying Configuration Profile assignments.
- Performing remote management actions.
- Synchronising devices with Microsoft Intune.

These capabilities reduce the need for physical access to managed devices and allow administrators to support users regardless of their location.

For Android Enterprise Personally-Owned Work Profile devices, Microsoft Intune manages only the corporate work profile. Personal applications, photographs, messages and user data remain outside the organisation's control, providing a balance between enterprise security and user privacy.

---

To begin reviewing enrolled devices, navigate to:

```text
Microsoft Intune Admin Center

Devices
    └── All devices
```

The **All devices** page displays every endpoint currently enrolled into Microsoft Intune.

For each managed device, administrators can quickly review information such as:

- Device name
- Platform
- Ownership
- Compliance status
- Operating system
- Last check-in
- Primary user

This page acts as the primary inventory view within Microsoft Intune and is often the first location administrators visit when troubleshooting endpoint issues or validating newly enrolled devices.

![Managed Devices Overview](screenshots/managed-devices-overview.png)

---

# Reviewing the Device Overview

From the **All devices** page, I selected my enrolled Android Enterprise device to open its management dashboard.

The **Overview** page provides a high-level summary of the device and acts as the central administration page for day-to-day endpoint management.

Rather than navigating through multiple sections, administrators can immediately determine whether the device is healthy, compliant and communicating successfully with Microsoft Intune.

The Overview page displayed information including:

- Device name
- Ownership
- Compliance status
- Device manufacturer
- Device model
- Android version
- Primary user
- Last successful check-in
- Available remote management actions

In addition to the device information, Microsoft Intune provides direct access to several remote administrative actions including synchronisation, remote lock, retirement and device wipe, depending upon the enrolment method and supported platform capabilities.

![Android Device Overview](screenshots/android-device-overview.png)

---

# Reviewing Hardware Information

One of the advantages of Microsoft Intune is its ability to collect detailed hardware and operating system information from enrolled devices automatically. This information provides administrators with a centralised hardware inventory, allowing them to review device specifications without requiring physical access to the endpoint.

To examine the hardware information, I navigated to:

```text
Monitor
    └── Hardware
```

The **Hardware** page displayed technical information relating to my enrolled Android Enterprise device, including:

- Manufacturer
- Model
- Android version
- Operating system build
- Total storage capacity
- Available storage
- Physical memory (RAM)
- Serial number
- IMEI (where supported)
- Wi-Fi MAC address

This information is extremely useful when supporting end users because it enables administrators to confirm device specifications before beginning more advanced troubleshooting.

For example, hardware inventory can be used to:

- Verify that a device meets the minimum operating system requirements for newly deployed applications.
- Confirm the device manufacturer and model when troubleshooting hardware-specific issues.
- Check storage availability before deploying large applications.
- Assist with asset management and device lifecycle planning.

In enterprise environments containing hundreds or thousands of managed devices, maintaining an accurate hardware inventory is essential for effective endpoint administration.

![Android Device Hardware](screenshots/android-device-hardware.png)

---

# Reviewing Device Properties

After reviewing the hardware inventory, I examined the administrative properties associated with the enrolled device.

Unlike the Hardware page, which focuses on the physical characteristics of the endpoint, the **Properties** page contains information describing how the device is managed within Microsoft Intune.

This information is used by administrators to validate enrolment details, confirm ownership and verify that the device has been registered correctly within the organisation.

The Properties page included information such as:

- Device name
- Management name
- Ownership
- Primary user
- Enrolment type
- Device category
- Microsoft Entra device information
- Management status

Reviewing these properties is an important administrative task because many deployment and troubleshooting decisions depend upon the enrolment method used by the device.

During my laboratory, I confirmed that the device had been enrolled as an **Android Enterprise Personally-Owned Work Profile** device.

I also verified that Microsoft Intune correctly identified the ownership as **Personal**, matching the enrolment method configured during Chapter 04.

Confirming these values helps ensure that the expected management capabilities are available. This is particularly important because Android Enterprise provides different administrative features depending on whether the device is Personally-Owned, Corporate-Owned Work Profile or Fully Managed.

![Android Device Properties](screenshots/android-device-properties.png)

---

# Verifying Configuration Profile Assignments

One of the final verification tasks performed during this laboratory was confirming that the Configuration Profile created in the previous chapter had been assigned successfully.

Rather than assuming that policies are targeting the correct devices, Microsoft Intune allows administrators to review Configuration Profile assignments directly from within the managed device.

This provides an additional level of confidence before investigating any configuration or compliance issues.

The assignment information confirmed that the **Android Work Profile Device Restrictions** profile had been successfully assigned to the **Android Test Users** Microsoft Entra Security Group.

Reviewing assignments in this way is considered good administrative practice because it allows administrators to verify that the intended deployment groups are being targeted correctly.

In larger environments where multiple Configuration Profiles may apply to the same endpoint, this page also assists with troubleshooting by helping administrators identify missing or conflicting assignments.

The successful assignment confirmed that the device was eligible to receive the Configuration Profile created in Chapter 07.

![Configuration Profile Assignments](screenshots/configuration-profile-assignments.png)

---

# Device Management Best Practices

Throughout this laboratory, I observed several administrative practices that contribute to effective endpoint management within Microsoft Intune.

Although Microsoft Intune provides numerous management capabilities, effective administration depends on understanding how and when these features should be used rather than simply performing remote actions.

One of the first checks administrators should perform when investigating a managed device is reviewing the **Last check-in** time. Devices that have not communicated with Microsoft Intune recently may not have received newly deployed applications, Configuration Profiles or Compliance Policies.

Similarly, confirming the device ownership and enrolment method helps administrators understand which management capabilities are available. Android Enterprise Personally-Owned Work Profile devices intentionally expose fewer management functions than Corporate-Owned or Fully Managed devices in order to protect user privacy.

Configuration Profile assignments should also be verified whenever newly deployed policies do not appear to be reaching managed devices. Confirming that the correct Microsoft Entra Security Groups have been targeted often identifies deployment issues before more advanced troubleshooting becomes necessary.

Finally, administrators should avoid making assumptions based solely on the device overview. Reviewing hardware information, device properties and assigned policies provides a much more complete understanding of the endpoint and often reduces the time required to resolve support incidents.

Applying these practices contributes to a more structured troubleshooting process whilst improving the overall management of enterprise devices.

---

# Key Learnings

Throughout this chapter, I learned that:

- Microsoft Intune provides a centralised interface for managing enrolled Android Enterprise devices.
- The **All devices** page acts as the primary inventory for managed endpoints.
- The Device Overview page provides a consolidated summary of the health and management status of an enrolled device.
- Hardware inventory is collected automatically and provides valuable information for troubleshooting and asset management.
- Device Properties contain important administrative information relating to enrolment, ownership and device management.
- Configuration Profile assignments can be verified directly from within the managed device.
- Android Enterprise Personally-Owned Work Profile devices provide a different management experience compared with Corporate-Owned and Fully Managed devices.
- Reviewing multiple areas of the Device Management workspace provides administrators with a complete understanding of an endpoint before performing troubleshooting activities.

---

# Skills Demonstrated

Throughout this chapter, I demonstrated the following Microsoft Intune administration skills:

- Android Enterprise device administration.
- Endpoint inventory management.
- Hardware inventory analysis.
- Device property verification.
- Configuration Profile validation.
- Device lifecycle administration.
- Microsoft Intune device monitoring.
- Endpoint management best practices.
- Technical documentation using GitHub and Markdown.

---

# Interview Tip

A common interview question for IT Support Engineers, Service Desk Analysts and Junior Endpoint Administrators is:

> **"What information would you review first when troubleshooting a managed device in Microsoft Intune?"**

A well-structured answer demonstrates both technical knowledge and a logical troubleshooting methodology.

A good response would include:

- Verify the **Last check-in** time to confirm that the device is communicating with Microsoft Intune.
- Review the **Compliance** status to determine whether the device satisfies organisational security requirements.
- Confirm the **Ownership** and **Enrolment type**, as these determine the management capabilities available.
- Verify that the required **Configuration Profiles** and **Compliance Policies** have been assigned.
- Review the **Hardware** information to confirm that the device meets any operating system or hardware requirements.
- Examine the **Device Properties** to validate that the device has been enrolled correctly.

Rather than immediately changing policies or repeating synchronisation requests, experienced administrators first collect information from the Device Management workspace before deciding upon the appropriate troubleshooting approach.

---

# Chapter Summary

In this chapter, I explored the Device Management capabilities available within Microsoft Intune for an Android Enterprise Personally-Owned Work Profile device.

I reviewed the managed device inventory, examined the Device Overview page, inspected the hardware inventory collected by Microsoft Intune and verified the administrative properties associated with the enrolled device.

I also confirmed that the Configuration Profile created in the previous chapter had been successfully assigned to the Android Test Users Security Group, providing assurance that policy deployment had been configured correctly.

This exercise demonstrated the day-to-day management activities performed by Microsoft Intune administrators and reinforced the importance of monitoring enrolled devices, validating policy assignments and understanding the operational lifecycle of Android Enterprise endpoints within a modern cloud-managed environment.
