---
UID: NS:usbscan._CHANNEL_INFO
title: _CHANNEL_INFO
author: windows-driver-content
description: The CHANNEL_INFO structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_CHANNEL_ALIGN_RQST.
old-location: image\channel_info.htm
old-project: image
ms.assetid: 1f1cb952-9a63-461f-b70f-4cc41b8d88f8
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: _CHANNEL_INFO, CHANNEL_INFO, *PCHANNEL_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CHANNEL_INFO
req.alt-loc: usbscan.h
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
req.typenames: CHANNEL_INFO, *PCHANNEL_INFO
req.product: Windows 10 or later.
---

# _CHANNEL_INFO structure



## -description
The CHANNEL_INFO structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_get_channel_align_rqst.md">IOCTL_GET_CHANNEL_ALIGN_RQST</a>.



## -syntax

````
typedef struct _CHANNEL_INFO {
  unsigned EventChannelSize;
  unsigned uReadDataAlignment;
  unsigned uWriteDataAlignment;
} CHANNEL_INFO, *PCHANNEL_INFO;
````


## -struct-fields

### -field EventChannelSize

Maximum packet size for the interrupt transfer pipe.


### -field uReadDataAlignment

Maximum packet size for the bulk IN transfer pipe.


### -field uWriteDataAlignment

Maximum packet size for the bulk OUT transfer pipe.


## -remarks
