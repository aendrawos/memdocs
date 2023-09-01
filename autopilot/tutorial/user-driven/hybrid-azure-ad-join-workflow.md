---
title: Overview for Windows Autopilot user-driven hybrid Azure AD join in Intune
description: Overview for Windows Autopilot user-driven hybrid Azure AD join in Intune.
ms.prod: windows-client
ms.localizationpriority: medium
author: frankroj
ms.author: frankroj
ms.reviewer: jubaptis
manager: aaroncz
ms.date: 06/26/2023
ms.topic: tutorial
ms.collection: 
  - tier1
  - highpri
ms.technology: itpro-deploy
appliesto:
  - ✅ <a href="https://learn.microsoft.com/windows/release-health/supported-versions-windows-client" target="_blank">Windows 11</a>
  - ✅ <a href="https://learn.microsoft.com/windows/release-health/supported-versions-windows-client" target="_blank">Windows 10</a>
---

# Step by step tutorial for Windows Autopilot user-driven hybrid Azure AD join in Intune

This step by step tutorial guides you through using Intune to perform a Windows Autopilot user-driven scenario when the devices are also joined to an on-premises domain, also known as hybrid Azure AD join.

The purpose of this tutorial is a step by step guide for all the configuration steps required for a successful Autopilot user-driven hybrid Azure AD join deployment using Intune. The tutorial is also designed as a walkthrough in a lab or testing scenario, but can be expanded for use in a production environment.

Before beginning, refer to the [Plan your hybrid Azure Active Directory join implementation](/azure/active-directory/devices/hybrid-azuread-join-plan) to make sure all prerequisites are met for joining on-premises AD devices to Azure AD.

## Windows Autopilot user-driven hybrid Azure AD join overview

Windows Autopilot user-driven hybrid Azure AD join is an Autopilot solution that automates the configuration of Windows on a new device delivered directly from an OEM or reseller to the end-user without the need for IT intervention. Windows Autopilot user-driven deployments use the existing Windows installation installed by the OEM at the factory. The end-user only needs to perform a minimal number of actions during the deployment process such as:

- Powering on the device.
- In certain scenarios, selecting the language, locale, and keyboard layout.
- Connecting to a wireless network if the device isn't connected to a wired network.
- Signing into the device with the end-user's on-premises domain credentials.
- In certain scenarios, signing into Azure AD with the end-user's Azure AD credentials.

Windows Autopilot user-driven deployments can perform the following tasks during the deployment:

- Joins the device to an on-premises domain.
- Registers the device with Azure AD.
- Enrolls the device in Intune.
- Installs applications.
- Applies device configuration policies such as BitLocker and Windows Hello for Business.
- Checks for compliance.
- Enrollment Status Page (ESP) can be used to prevent an end-user from using the device until it's fully configured.

Windows Autopilot user-driven deployments consist of two phases:

- Device ESP phase: Windows is configured and applications and policies assigned to the device are applied.
- User ESP phase: End-user signs into the device for the first time using on-premises domain credentials and applications and policies assigned to the user are applied.

Once the Windows Autopilot user-driven deployment is complete, it prompts the end-user to sign out of the device. Once the end-user is signed out of the device, it's ready for use. The end-user can then sign in with their on-premises domain credentials and begin to use the device.

## Workflow

The following steps are needed to configure and then perform a Windows Autopilot user-driven hybrid Azure AD join in Intune:

> [!div class="checklist"]
> - Step 1: [Set up Windows automatic Intune enrollment](hybrid-azure-ad-join-automatic-enrollment.md)
> - Step 2: [Install the Intune Connector](hybrid-azure-ad-join-intune-connector.md)
> - Step 3: [Increase the computer account limit in the Organizational Unit (OU)](hybrid-azure-ad-join-computer-account-limit.md)
> - Step 4: [Register devices as Autopilot devices](hybrid-azure-ad-join-register-device.md)
> - Step 5: [Create a device group](hybrid-azure-ad-join-device-group.md)
> - Step 6: [Configure and assign Autopilot Enrollment Status Page (ESP)](hybrid-azure-ad-join-esp.md)
> - Step 7: [Create and assign hybrid Azure AD join Autopilot profile](hybrid-azure-ad-join-autopilot-profile.md)
> - Step 8: [Configure and assign domain join profile](hybrid-azure-ad-join-domain-join-profile.md)
> - Step 9: [Assign Autopilot device to a user (optional)](hybrid-azure-ad-join-assign-device-to-user.md)
> - Step 10: [Deploy the device](hybrid-azure-ad-join-deploy-device.md)

> [!NOTE]
>
> Although the workflow is designed for lab or testing scenarios, it can also be used in a production environment. Some of the steps in the workflow are interchangeable and interchanging some of the steps may make more sense in a production environment. For example, the **Create a device group** step followed by the **Register devices as Autopilot devices** step may make more sense in a production environment.

## Walkthrough

> [!div class="nextstepaction"]
> [Step 1: Set up Windows automatic Intune enrollment](hybrid-azure-ad-join-automatic-enrollment.md)

## More information

For more information on Windows Autopilot user-driven hybrid Azure AD join, see the following article(s):

- [Deploy hybrid Azure AD-joined devices by using Intune and Windows Autopilot](/mem/autopilot/windows-autopilot-hybrid)