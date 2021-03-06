---
UID: NF:wiautil.wiauDbgInit
title: wiauDbgInit function
author: windows-driver-content
description: The wiauDbgInit function initializes WIA debugging.
old-location: image\wiaudbginit.htm
old-project: image
ms.assetid: a9308d66-c8b0-4e0e-8203-e2b3f91b7e27
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: wiauDbgInit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiauDbgInit
req.alt-loc: wiautil.h
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
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauDbgInit function



## -description
The <b>wiauDbgInit</b> function initializes WIA debugging.



## -syntax

````
void __stdcall wiauDbgInit(
  _In_opt_ HINSTANCE hInstance
);
````


## -parameters

### -param hInstance [in, optional]

Is the handle to the DLL instance.


## -returns
None


## -remarks
If the <b>wiauDbgInit</b> function not called, all DLLs loaded by a process inherit the debug flags of that process. </p>