---
Description: auditUser
MS-HAID: 'p\_adk\_online.audituser'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: auditUser
---

# auditUser


The **auditUser** configuration pass processes unattended Windows® Setup settings in user context in audit mode. The **auditUser** configuration pass always runs after the [auditSystem](auditsystem.md) pass, which is used to apply settings in system context. Typically, the **auditUser** configuration pass is used to execute **RunSynchronous** or **RunAsynchronous** commands. These commands are used to run scripts, applications, or other executables during audit mode. When Windows boots to audit mode, the auditSystem and **auditUser** settings for unattended Windows Setup are processed.

Audit mode enables OEMs and corporations to install additional device drivers, applications, and other updates to a master Windows® image. By using audit mode, you can maintain fewer images because you can create a reference image with a minimal set of drivers and applications. The reference image can then be updated with additional drivers during audit mode. Additionally, you can test and resolve any issues related to malfunctioning or incorrectly installed devices on the Windows image before shipping the computer to a customer. Audit mode is optional.

The following diagram illustrates when the **auditUser** configuration pass is processed in audit mode.

![auditmode configuration pass](images/dep-win8-l-auditmode.jpg)

The **auditUser** configuration pass runs only when you configure Windows Setup to boot into audit mode. You can boot to audit mode by using the **sysprep /audit** or **sysprep /generalize /audit** commands, or you can specify the **Reseal** setting in the Microsoft-Windows-Deployment component. For more information about audit mode, see [Audit Mode Overview](audit_mode_overview.md) and [Boot Windows to Audit Mode or OOBE](boot-windows-to-audit-mode-or-oobe.md).

## <span id="related_topics"></span>Related topics


[How Configuration Passes Work](how-configuration-passes-work.md)

[auditSystem](auditsystem.md)

[generalize](generalize.md)

[offlineServicing](offlineservicing.md)

[oobeSystem](oobesystem.md)

[specialize](specialize.md)

[windowsPE](windowspe.md)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_adk_online\p_adk_online%5D:%20auditUser%20%20RELEASE:%20%284/11/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



