---
UID: NF:wdm.READ_REGISTER_UCHAR
title: READ_REGISTER_UCHAR function
author: windows-driver-content
description: The READ_REGISTER_UCHAR routine reads a byte from the specified register address.
old-location: kernel\read_register_uchar.htm
old-project: kernel
ms.assetid: 49f9d7d7-c774-4ba5-a9f3-6d605a3de674
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: READ_REGISTER_UCHAR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: READ_REGISTER_UCHAR
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# READ_REGISTER_UCHAR function



## -description
The <b>READ_REGISTER_UCHAR</b> routine reads a byte from the specified register address.



## -syntax

````
UCHAR READ_REGISTER_UCHAR(
  _In_ PUCHAR Register
);
````


## -parameters

### -param Register [in]

Pointer to the register address, which must be a mapped range in memory space. 


## -returns
<b>READ_REGISTER_UCHAR</b> returns the byte read from the specified register address.


## -remarks
Callers of <b>READ_REGISTER_UCHAR</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.</p>