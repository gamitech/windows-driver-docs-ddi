---
UID: NS:ehstorioctl._SILO_DRIVER_CAPABILITIES
title: _SILO_DRIVER_CAPABILITIES
author: windows-driver-content
description: This structure is used to specify the capabilities and support for IOCTL redirection of a storage silo driver. SILO_DRIVER_CAPABILITIES is included in the system buffer of an IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES request.
old-location: storage\silo_driver_capabilities.htm
old-project: storage
ms.assetid: E2CD35A6-0FF2-4ABA-850E-12683C5F0D8D
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SILO_DRIVER_CAPABILITIES
req.alt-loc: EhStorIoctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES
---

# _SILO_DRIVER_CAPABILITIES structure



## -description
This structure is used to specify the capabilities and support for IOCTL redirection of a storage silo driver. <b>SILO_DRIVER_CAPABILITIES</b> is included in the system buffer of an <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities.md">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a> request.



## -syntax

````
typedef struct _SILO_DRIVER_CAPABILITIES {
  ULONG StructSize;
  ULONG Capabilities;
  ULONG MaxLbaFilterCount;
  ULONG RedirectedIoctlListCount;
  ULONG RedirectedIoctlListOffset;
} SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES;
````


## -struct-fields

### -field StructSize

The size of this structure. This is set to <b>sizeof</b>(SILO_DRIVER_CAPABILITIES).


### -field Capabilities

Capability flags for the silo driver. This is a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field CAP_ON_DEMAND_AUTHENTICATION

</td>
<td width="60%">
The silo driver supports on-demand authentication and unauthentication.

</td>
</tr>
<tr>

### -field CAP_BANDING_SUPPORT

</td>
<td width="60%">
The silo driver supports banding of LBA ranges.

</td>
</tr>
</table>
 


### -field MaxLbaFilterCount

Maximum number of LBA filter entries the silo driver can provide in a <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table.md">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a> request.


### -field RedirectedIoctlListCount

The number of redirected IOCTLs in the list following this structure.


### -field RedirectedIoctlListOffset

The offset of the redirected IOCTL list from the beginning of this structure. This will typically be <b>sizeof</b>(SILO_DRIVER_CAPABILITIES).


## -remarks
To support receiving <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_perform_authz.md">IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ</a> from the enhanced storage class driver, a silo driver must set <b>CAP_ON_DEMAND_AUTHENTICATION</b> in <b>Capabilities</b>. Also, to support sending <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table.md">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a>, a silo driver must set <b>CAP_BANDING_SUPPORT</b> in <b>Capabilities</b>.

To receive band management requests from the enhanced storage class driver, a silo driver must register a list of IOCTL codes it wants to receive. The redirected IOCTL list is an array of <b>ULONG</b> IOCTL codes with a length of <b>RedirectedIoctlListCount</b>. This list is included with the <b>SILO_DRIVER_CAPABILITIES</b> structure in the system buffer. The list is located in the system buffer following  <b>SILO_DRIVER_CAPABILITIES</b> at the offset indicated by <b>RedirectedIoctlListOffset</b>.


## -see-also
<dl>
<dt>
<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_perform_authz.md">IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ</a>
</dt>
<dt>
<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities.md">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table.md">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SILO_DRIVER_CAPABILITIES structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

