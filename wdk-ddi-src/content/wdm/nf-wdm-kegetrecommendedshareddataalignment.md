---
UID: NF:wdm.KeGetRecommendedSharedDataAlignment
title: KeGetRecommendedSharedDataAlignment function
author: windows-driver-content
description: The KeGetRecommendedSharedDataAlignment routine returns the preferred alignment for memory structures that can be accessed by more than one processor.
old-location: kernel\kegetrecommendedshareddataalignment.htm
old-project: kernel
ms.assetid: 2faf5e30-bfbb-4b23-9cb9-bf9dd81a56c2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeGetRecommendedSharedDataAlignment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeGetRecommendedSharedDataAlignment
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
req.irql: Any level
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeGetRecommendedSharedDataAlignment function



## -description
The <b>KeGetRecommendedSharedDataAlignment</b> routine returns the preferred alignment for memory structures that can be accessed by more than one processor.



## -syntax

````
ULONG KeGetRecommendedSharedDataAlignment(void);
````


## -parameters


## -returns
<b>KeGetRecommendedSharedDataAlignment</b> returns the preferred alignment, in bytes, for memory structures that can be shared by more than one processor.

<b>KeGetRecommendedSharedDataAlignment</b> returns the preferred alignment, in bytes, for memory structures that can be shared by more than one processor.

<b>KeGetRecommendedSharedDataAlignment</b> returns the preferred alignment, in bytes, for memory structures that can be shared by more than one processor.


## -remarks
Use <b>KeGetRecommendedSharedDataAlignment</b> to determine the best alignment for data structures that will be shared between processors. The value returned minimizes cache effects that negatively impact performance on multiprocessor systems.</p>