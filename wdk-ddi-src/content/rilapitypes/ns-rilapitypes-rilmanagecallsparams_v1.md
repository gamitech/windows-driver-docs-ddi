---
UID: NS:rilapitypes.RILMANAGECALLSPARAMS_V1
title: RILMANAGECALLSPARAMS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmanagecallsparams_v1_2.htm
old-project: netvista
ms.assetid: 5c5113d2-30a5-4ec3-9566-d7d116cfa135
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMANAGECALLSPARAMS_V1, *LPRILMANAGECALLSPARAMS_V1, RILMANAGECALLSPARAMS_V1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMANAGECALLSPARAMS_V1
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILMANAGECALLSPARAMS_V1, RILMANAGECALLSPARAMS_V1
req.product: Windows 10 or later.
---

# RILMANAGECALLSPARAMS_V1 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILMANAGECALLSPARAMS_V1 {
  DWORD                       dwExecutor;
  RILMANAGECALLPARAMSCOMMAND  dwCommand;
  DWORD                       dwID;
} RILMANAGECALLSPARAMS_V1, RILMANAGECALLSPARAMS_V1;
````


## -struct-fields

### -field dwExecutor


### -field dwCommand


### -field dwID


## -remarks
