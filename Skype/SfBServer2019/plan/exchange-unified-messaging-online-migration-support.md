---
title: "Exchange Unified Messaging Online migration support" 
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: "Microsoft is retiring the Exchange Unified Messaging Online (ExchUMO) service by February 28, 2020. This article summarizes what affected customers should know and do to plan for their business continuity."
---

# Exchange Unified Messaging Online migration support

> [!IMPORTANT]
> **The Unified Messaging service in Exchange Online is out of support as of February 28, 2020, 5 PM Pacific Time. All voicemail accounts have been migrated to Cloud Voicemail service by Microsoft. Any remaining auto attendant traffic won't be monitored and might be disrupted at any time.**

In reference to the [announcement](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) on February 8, 2019, Microsoft is retiring the Exchange Unified Messaging Online (ExchUMO) service by February 28, 2020. This article offers a summary of what affected customers should know and do to plan for their business continuity.
 
ExchUMO is deployed by customers for voicemail, auto attendant, Call Queue, and fax integration services. Microsoft plans to help customers migrate to Phone System services that already support thousands of customers on Skype for Business Online and Microsoft Teams.

Voicemail is primarily a Microsoft-driven migration; admin involvement and/or investment might be required for a subset of customers. Auto attendant is an admin-driven migration; you will need to re-create the existing ExchUMO auto attendant trees in the Cloud Auto Attendant cloud service. Customers who consume any of the ExchUMO features with a third-party PBX will not be migrated to Skype cloud services because they do not support third-party PBX systems. A retirement plan for third-party support was announced in [this blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853), and customers in this deployment model can migrate their users to one of Microsoft’s Unified Communications platforms/services or acquire a third-party voicemail and/or auto attendant solution for these users. Fax integration is not supported in the cloud-based services; customers will need to migrate to a third-party solution.

### Who is affected?

Customers who are consuming any of the following features from Exchange Unified Messaging Online service are affected:

- Voicemail service
- Auto Attendant service
- Call Queue service
- Fax integration

> [!Note]
> Customers who are using any of the Exchange Server on-premises with Unified Messaging are not affected. 

Learn more about the user and admin experience impact in [User experience impact](#user-experience-impact).

## Migration plan overview

Microsoft has identified various customer deployments that are consuming features from ExchUMO and will be helping customers migrate based on the following plan. 

|Customer group |Timeline  |Details  |
|---------|---------|---------|
|Customers who are ready to migrate<br><br>Features to migrate:<br><ul><li>Voicemail</ul>   |   March — May 2019  |Examples:<ul><li>	Customers with simple voicemail deployment and usage<li>Customers that have all requirements established for Microsoft to execute the migration<ul>|
|Customers with prerequisites<br><br>Features to migrate:<br><ul><li>Voicemail<li>Auto attendant<li>Call Queue</ul> |  May — December 2019 |Examples: <br><ul><li>Hybrid configuration is not  complete<li>Hybrid PSTN numbers are not set up</ul>|
|Customers who require admin involvement & customer investment<br><br>Features to migrate:<ul><li>voicemail<li>Auto attendant<li>Call Queues<li>Fax integration</ul>| By February 2020  | Examples: <br><ul><li>ExchUMO service is consumed by third party PBX<li>Customers with PSTN Subscriber Access requirements<li>Customers on SFB 2010 (not-supported)<li>Fax integration</ul> |

## Voicemail migration steps

1.	**Get informed**
 
    Familiarize yourself with the [blog announcement](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) and this article to plan a smooth migration for your users. See [Check Skype for Business voicemail and options](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) for details on the Phone System Voicemail capabilities.  
 
2.	**Establish a Skype for Business hybrid topology**

    If you do not have a Skype for Business hybrid topology established, you need to do that to enable a smooth migration of your voicemail users. See [Configure Skype for Business hybrid](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) for more details. 

    > [!Note]
    > You do not need to migrate your users to online for the voicemail service migration. However, for on-premises users to leverage Phone System voicemail service, a hybrid topology is must be established.

3. **Plan your auto attendant migration**
    
    Admins can start migrating their auto attendants from ExchUMO to the Cloud auto attendant at any time. See [Set up a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) for more details. Microsoft continues to deliver additional auto attendant capabilities that customers may consider required for their migration, admins should evaluate the feature set and migrate their auto attendant instances accordingly. For feature-list comparison, see the [ExchUMO and Azure cloud-based services feature matrix](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Plan for your voicemail post-migration validation and testing**

    Voicemail migration is Microsoft driven. Admins are not required to do anything, given that the pre-requisite hybrid topology is established. Microsoft performs the required validation and testing to make sure users’ voicemail migration is not disrupted. Admins are encouraged to perform testing and validation on their side. See [Suggested test plan and post-migration validation for admins](#suggested-test-plan-and-post-migration-validation-for-admins) for a recommended test plan. 

    > [!Note]
    > Lync Server 2010 is not supported. If you are in a 2010 server deployment, you should plan a server upgrade or consider migrating your users to Microsoft Teams or Skype for Business Online.  

5. **Monitor the Admin Notification Center**

    Look out for a notice in the Admin Notification Center with further details and timeline regarding your users' migration. Notifications are sent at least 30 days before your migration period. 

    > [!Note]
    > If you received a notification with your users’ migration timeline and would like to postpone your migration for a business-critical reason, you can do so by contacting Microsoft Support. Note that you cannot postpone your migration beyond the retirement date, February 28, 2020. For customers who may have more questions, please contact your account team or Microsoft Support. Customers already using Microsoft 365 or Office 365 can submit a support case through the Microsoft 365 admin center. 

6. **Consider opting in for a planned migration**

    You can opt in for a planned Voicemail service migration to CVM. Before opting in, review the details of this article, especially the following sections:

    - Migration steps (this section)
    - ExchUMO and Azure cloud-based services feature matrix
    - User experience impact

    When you choose a managed migration you will not receive a pre-migration 30-days notification in the Microsoft 365 admin portal message center.
 
    To opt in for a planned migration, send an email request from your administrator's email address to [cvm@microsoft.com](mailto:cvm@microsoft.com) with the following information:

    - Preferred date (Tuesdays): migration waves are executed every Tuesday. Please select a date on a Tuesday that is not beyond 12/3/2019.
 
    - Tenant ID: 32 characters number in this format 0046728c-688a-4472-a38f-098fec60ac6x. You can find your tenant ID in the Microsoft 365 admin portal under Azure AD, or using the following PowerShell cmdlet: `Get-CsTenant | Select ObjectId`
 
    You receive an email confirmation once your tenant is successfully migrated.

## Auto attendant migration guidelines

Microsoft 365 and Office 365 organization administrators are required to re-create their Exchange UM Online auto attendants in the Microsoft Cloud Auto Attendant service and switch their on-premises phone numbers to them before February 28, 2020, which is when Exchange UMO service will be retired. This is the recommended guideline to successfully migrate and test new Cloud auto attendants. If you have a large number of auto attendants, you can use the [Exchange UM Auto Attendant to Cloud Auto Attendant Migration scripts](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) to simplify the bulk migration of auto attendants.

### Setup

We strongly advise that you start the setup of your new auto attendants early to avoid last minute issues and to get familiar with the functionality and experience of the Cloud Auto Attendant service. For auto attendants that require one or more gap features, you can create and test the auto attendants when the gap features are available to prepare for deployment. For more information about gap features, see the [Appendix](#appendix).

1. Use the Exchange UMO cmdlets to export the configuration of existing auto attendants by using [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Use the [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) cmdlet in Exchange Online PowerShell to export the greeting media files (if used) and convert them to .mp3 format.
3. Follow the instructions in [Plan Cloud auto attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) and [Set up a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) to create auto attendants by using the Microsoft Teams admin center or Powershell.
4. Review your greetings if the menu options changed.
5. Configure transfers to your response groups by using the "Auto Attendant Call Transfer to PSTN" workaround in the [Known issues](#known-issues) section of this article.  
6. Test the new auto attendants. To test, call them internally or assign a test phone number.  

### Cutover

1. Switch your phone numbers from Exchange UMO auto attendants to the new auto attendants.
2. Move the SIP URI from the contact object to the resource account.
3. Test and validate your auto attendants by using the newly-assigned phone numbers. 

## Appendix

### ExchUMO and Azure cloud-based services feature matrix

| Service | Feature level | Feature | Notes  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Service Features| Support 3rd-party PBX    | Including all features provided to third party PBX such as MWI (Message Waiting Indicator) using SIP notify messages from Exchange UM Online | N   | Y    |
| VM | Service Features  | Support Skype for Business Server   |  | Y | Y    |
| VM | Service Features | Support Microsoft Teams|  | Y | N    |
| VM | Service Features | eDiscovery and Hold  | For security and compliance  | Y | Y    |
| VM | Service Features | Exchange Rules support | For security and compliance  | Y | Y    |
| VM | User Features | PSTN Dial-in Access  | Subscriber access  | N | Y    |
| VM | User Features | Delegate  | missed call email  | N | Y    |
| VM | User Features | PSTN Outlook Voice Access   | Subscriber access  | N | Y    |
| VM | User Features | Dial-in using an authenticated endpoint | Calling the voicemail service to listen to voice messages and change voicemail settings| Y | Y    |
| VM | User Features | User setting to disable voicemail   |  | Y | Y    |
| VM | User Features | User setting to change the personal greeting  |  | Y | Y    |
| VM | User Features | User setting to create an OOF greeting  |  | Y | Y    |
| VM | User Features | User setting to change the default language  |  | Y | Y    |
| VM | User Features | User setting to overwrite default greeting with TTS  |  | Y | N    |
| VM | User Features | Record personal greetings (authenticated device) |  | Y | Y    |
| VM | User Features | Record personal greetings (PSTN) — play on phone |  | N | Y    |
| VM | User Features | User setting to disable transcription |  | N | Y    |
| VM | User Features | Transcription  |  | Y | Y    |
| VM | User Features | Visual voicemail on all endpoints   | With user control to play, delete, message waiting indicator, and status-toggle, on all supported endpoints  | N | Y    |
| VM | User Features | MP3 audio file format in Outlook    |  | Y | Y    |
| VM | User Features | Variable speed play control |  | Y | Y    |
| VM | User Features | Forward a voicemail  | Forward a received voicemail to other users | Y | Y    |
| VM | User Features | Sending a voice message to a group of users  |Voicemail broadcast   | N | Y   |
| VM | User Features | Voicemail notification using SMS    | Users can receive an SMS when they have a new voicemail    | N | Y    |
| VM | User Features | Supported greeting languages | Details here: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| VM | User Features | Call answering rules |  | Y | Y    |
| VM | User Features | Play on phone (PSTN)- to play message | Call me on my cell to listen to the voice message  | N | Y    |
| VM | User Features | Play on phone (Auth)- to play message | Call me on my authenticated device  | Y | Y    |
| VM | User Features | Shared mailbox between multiple users |  | Y | Y    |
| VM | Caller Features  | Caller experience — protected voicemail | The caller can choose an option to mark a recorded message as protected| N | Y    |
| VM | Caller Features  | Caller experience — private voicemail | The caller can choose an option to mark a recorded message as private  | N | Y    |
| VM | Caller Features  | Silence detection   |  | N | Y    |
| VM | Tenant-Admin Features | Server-level protected voicemail    | Tenant-admin can configure a service-level rule to mark incoming voicemail as protected | Y | Y    |
| VM | Tenant-Admin Features | Change recording duration time limit  |     | Y | Y    |
| VM | Tenant-Admin Features | Change silence detection timeout    |  | N/A    | Y    |
| VM | Tenant-Admin Features | Change number of input failure | CVM: hard coded to 3 | N | Y    |
| VM | Tenant-Admin Features | Change the default language |  | Y | Y    |
| VM | Tenant-Admin Features | Disable/enable transcription |  | Y | Y    |
| VM | Tenant-Admin Features | Disable/enable missed call notification |  | N | Y    |
| VM | Tenant-Admin Features | Help Microsoft improve voice mail preview    |  | Y | Y    |
| VM | Tenant-Admin Features | Customize text message for enabled users|  | N/A    | Y    |
| VM | Tenant-Admin Features | Transcription profanity masking|  | Y | N    |
| VM | Tenant-Admin Features | Voicemail policy    |   | Y | Y    |
| VM | Tenant-Admin Features | Web portal administration   |  | CY19   | Y    |
| VM | Tenant-Admin Features | PowerShell   |  | Y | Y    |
| AA | Service Features | AA support 3rd-party PBX    |  | N | Y    |
| AA | Service Features | Support Skype for Business Server   |  | Y | Y    |
| AA | Service Features | Support Microsoft Teams|  | Y | N    |
| AA | Service Features | Dial by name, DTMF input    |  | Y | Y    |
| AA | Service Features | Dial by name, speech input  |  | Y | Y    |
| AA | Service Features | Multi-language support | Language details here: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | Service Features | Transfer to operator, CQ, or a user |  | Y | Y    |
| AA | Service Features | Transfer to PSTN number internally (DID RNL)  |  | Y | Y    |
| AA | Service Features | Transfer to PSTN number externally  |  | Check out Known Issues section below | Y    |
| AA | Service Features | Business hours |  | Y | Y    |
| AA | Service Features | Menu options | IVR menu options  | Y | Y    |
| AA | Service Features | Assigning a cloud PSTN number to AA |  | Y | N    |
| AA | Service Features | Assigning an on-prem PSTN number to AA  |  | Y | Y    |
| AA | Service Features | Custom user selection  | Enabling callers to reach customized list of organization users| Y | Y    |
| AA | Service Features | After-hours and holidays treatment  |  | Y | Y    |
| AA | Service Features | Custom greeting using text to speech  |  | Y | Y    |
| AA | Service Features | Extension dialing   | Reaching a user by dialing their extension  | Y   | Y    |
| AA | Service Features | Mailbox for AA callers to leave a message    |  | Y   | Y    |
| AA | Service Features | Multiple PSTN number assignments to an AA|  | Y | Y    |
| AA | Tenant-Admin Features | Web portal administration   |  | Y | N    |
| AA | Tenant-Admin Features | PowerShell cmdlets  |  | Y | Y    |
| Fax| Service Features | Fax integration|  | N | Y    |

### Suggested test plan and post-migration validation for admins

To validate that your users have been migrated to Cloud Voicemail,   leave a voicemail to a user and check the message body in Outlook.  Cloud Voicemail messages have a footer that reads:

**Thank you for using Transcription! If you don't see a transcript above, it's because the audio quality was not clear enough to transcribe.**

When testing voicemail functionality after your users have been migrated, make sure to consider the following scenarios:

- Validate voicemail access across all endpoint types in your organization: apps and IP phones. 
- Validate with sample users that the configured personalized greetings are played to callers.   
- If your organization has a legal or compliance requirement to disable transcription for users, make sure it is disabled post migration. For more details, see [Set up Cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- If you have previously configured Exchange VM policies and rules, make sure they are effective.
- Familiarize yourself with the Cloud Voicemail service PowerShell cmdlets for changing user settings.  

### User experience impact

The following is an overview of end-user voicemail migration experience.


|Experience  |Change in user experience|
|---------|---------|
|Email notification | No change<br>No email is sent to users notifying them about voicemail account activation/migration. |
|Access to previous messages | No change<br>Users have access to their previous voicemail messages in all supported endpoints. |
|Receiving VM in outlook, SFB Apps| No change<br>Users continue to receive their voicemail messages in all supported endpoints. |
|Transcription | Enhanced<br>CVM transcription has a much higher accuracy rate and supported languages than ExchUMO. |
|User setting | New experience<br>Users are able to change their preferences from a User Setting Portal (USP). Users can access their USP from a hyperlink in their voicemail email, or the User-Settings button on their SFB client; https://aka.ms/vmsettings.   
 |Features| Please see the feature-set comparison for details. |
|Outlook rules for VM messages | No change<br>Previously created rules will apply to CVM messages after migration.
 |

#### User management and provisioning in CVM

New Skype for Business users will be automatically provisioned for Cloud voicemail when created. No additional admin work or license is required to provision new voicemail users. See [Set up Cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail) to learn about policy management for existing and new users.

#### Admin Auto Attendant management experience

To learn more about auto attendants, see [Set up a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).

#### Known issues

**Disable Subscriber Access after migration to avoid greeting inconsistency**
Subscriber access might continue to work for your tenant until the service is completely retired, even after all of your users has been migrated to Cloud Voicemail. To avoid user confusion and inconsistent experience, please disable subscriber access since greetings changed after migration from there will not take affect. To do that, remove the EXUM contact for each subscriber access line using Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact 

**Auto Attendant Call Transfer to PSTN**
Customers are encouraged to configure a temporarily workaround to fulfill the requirements of transferring an auto attendant call to an external PSTN number, or to an RGS instance. 
 
An issue was identified during quality assurance with the Transfer out to PSTN number feature, which is not going to be fixed in-time for customers to start migrating off Exchange UMO service before its scheduled retirement date of Feb 28th, 2020. As a workaround, administrators can transfer auto attendant callers to an on-premise virtual user with an active Call Forward setting to the desired PSTN phone number or RGS phone number. 
 
Expected Experience
- Administrators do not need to license the virtual user, since this is a workaround solution 
- Administrators can manipulate the caller ID that the PSTN receiver will see by assigning the desired number to the virtual user, or using the SBC digit manipulation capabilities
- PSTN Callers will not experience any delay during the call transfer, and they will continue to see the caller ID of the auto attendant after the transfer is successful  

**Shared mailbox:**
A shared mailbox that is configured using Exchange UM Online will continue to receive messages after being migrated to CVM, and will continue to be accessible to users via Outlook. However, access to change the greeting messages of these mailboxes will not be available once migrated to CVM. Customers with shared mailboxes that are used to capture auto attendant callers should leverage the Auto Attendants and Call Queues Shared Mailbox capabilities once released (ETA October 2019).
  
**Upgrade to Teams banner on SFB client:**
The CVM service is based on Microsoft Teams infrastructure; calls to it from Skype for Business client may cause an information banner to be displayed on the client that reads:
"Username is not using Skype for Business. For a richer experience, switch to Teams or start a Skype meeting."
Make sure to update your users' Skype for Business client to the latest C2R client update to prevent this banner from appearing.
  
**Setup your voicemail will take you to OWA:**
Clicking on "Set Up Voice Mail" from the client will continue to take Skype for Business Server 2015/2013 customers to the Office Web Access (OWA) portal page after migration to CVM. All settings have been removed from the Voicemail tab in OWA, and a banner will be displayed with a redirect link to take users to the CVM user settings portal.
 
**Change greeting mobile access:**
PSTN subscriber access is not supported in CVM. For users that need to change their greeting remotely, a "Change your greeting" menu option is added to the voicemail IVR service for mobile clients. Users can call this service by pressing and holding the "1" key on the mobile client dial-pad.
