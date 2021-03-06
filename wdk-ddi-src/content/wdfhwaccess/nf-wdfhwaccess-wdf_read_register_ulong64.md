---
UID: NF:wdfhwaccess.WDF_READ_REGISTER_ULONG64
title: WDF_READ_REGISTER_ULONG64 function
author: windows-driver-content
description: The WDF_READ_REGISTER_ULONG64 function reads a ULONG64 value from the specified register address.
old-location: wdf\wdf_read_register_ulong64.htm
old-project: wdf
ms.assetid: A47BEA59-CBDD-41B5-9CEB-DC354D2BCC72
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_READ_REGISTER_ULONG64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfhwaccess.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: WDF_READ_REGISTER_ULONG64
req.alt-loc: Wdfhwaccess.h
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
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_READ_REGISTER_ULONG64 function



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_REGISTER_ULONG64</b> function reads a ULONG64 value from the specified register address.



## -syntax

````
ULONG64 WDF_READ_REGISTER_ULONG64(
  _In_ WDFDEVICE Device,
  _In_ PULONG64  Register
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register address, which must be a mapped range in memory space.


## -returns
<b>WDF_READ_REGISTER_ULONG64</b> returns the ULONG64 value that is read from the specified port address.


## -remarks
