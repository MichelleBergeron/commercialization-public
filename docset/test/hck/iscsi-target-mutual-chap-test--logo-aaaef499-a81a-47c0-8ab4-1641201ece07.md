---
author: joshbax-msft
title: iSCSI Target Mutual CHAP Test (LOGO)
description: iSCSI Target Mutual CHAP Test (LOGO)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 40f450b2-32a5-4138-80f4-b8b141a54a99
---

# iSCSI Target Mutual CHAP Test (LOGO)


This test verifies that the target device (disk, tape, or optical storage device) can use the Challenge Handshake Authentication Protocol (CHAP) authentication mechanism.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Storage.Hd.Iscsi.BasicFunction</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows 7 (x64) Windows 7 (x86) Windows 8 (x64) Windows 8 (x86) Windows Server 2012 (x64) Windows Server 2008 R2 (x64) Windows Server 2008 x64 Windows Server 2008 x86Windows 8.1 x64Windows 8.1 x86Windows Server 2012 R2</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~5 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification Functional</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Manual</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [iSCSI Boot Component Testing Prerequisites](iscsi-boot-component-testing-prerequisites.md).

If this is the first time you are running an iSCSI HBA test, iSCSI Target test, or MPIO test over iSCSI bus type on the HCK client, or if there is no iscsihctconfig.ini under \[HCK Path\]\\JobsWorkingDir\\ on the HCK client, you will receive a pop-up dialog box to input iSCSI configuration information and/or HBA information. For more information about this dialog box, see “Running the test” in [iSCSI HBA Boot Test (LOGO)](iscsi-hba-boot-test--logo-ca7ad4d0-6950-4e2d-bdfe-b80c7873ba90.md).

## Troubleshooting


For troubleshooting information, see [Troubleshooting Device.Storage Testing](troubleshooting-devicestorage-testing.md).

In addition:

1.  Look at the job results log file for test failures.

2.  Enter the required data in the configuration dialog box that appears when this job is scheduled. For more information, go to [iSCSI HBA Boot Test (LOGO)](iscsi-hba-boot-test--logo-ca7ad4d0-6950-4e2d-bdfe-b80c7873ba90.md).

This test always return Pass or Fail. To review test details, review the test log from the Windows HCK Manager.

## More information


The test uses multiple variations to verify that a target properly supports mutual CHAP. The first variation performs a logon similar to the user logging on through iSCSI Initiator Control Panel Applet. The rest of the variations perform logon outside of the Microsoft initiator by using the iSCSI protocol. Each variation challenges the target by using different challenge sizes with different encodings. The target is expected to calculate the proper response.

There are four different variations:

1.  Challenge size of 1 byte using hexadecimal encoding

2.  Challenge size of 1 byte using Base64 encoding

3.  Challenge size of 1024 bytes using hexadecimal encoding

4.  Challenge size of 1024 bytes using Base64 encoding

To run this test:

1.  Set up the initiator and the target with CHAP secrets.

2.  Run the test as a Driver Test Manager (DTM) job.

3.  Enter the required data in the configuration dialog box that appears when this job is scheduled.

### Parameters

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LogVerbosity</p></td>
<td><p>The verbosity of logging. There are three levels of output: 0, 1, and 2. 2 is the most verbose.</p>
<p>Default value: 1</p></td>
</tr>
</tbody>
</table>

 

### Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Command option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>iscsi_targetchap -mutual -hct</strong></p></td>
<td><p>Runs the test.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
For command-line help for this test binary, type **/h**.

 

### File list

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>File</th>
<th>Location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Iscsi_targetchap.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\driverstest\storage\wdk\iscsi</p></td>
</tr>
</tbody>
</table>

 

 

 





