---
UID: NS:ntddrilapitypes.RILUICCSLOTINFO
title: RILUICCSLOTINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccslotinfo.htm
old-project: netvista
ms.assetid: 4f8ed150-b378-49c3-955c-a1e69ab8c1a9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCSLOTINFO, *LPRILUICCSLOTINFO, RILUICCSLOTINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUICCSLOTINFO
req.alt-loc: ntddrilapitypes.h
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
req.typenames: *LPRILUICCSLOTINFO, RILUICCSLOTINFO
---

# RILUICCSLOTINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILUICCSLOTINFO {
  DWORD                cbSize;
  DWORD                dwParams;
  DWORD                dwNumOfUiccSlots;
  RILUICCSLOTSTATE [1] dwSlotState;
} RILUICCSLOTINFO, RILUICCSLOTINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwNumOfUiccSlots


### -field dwSlotState


## -remarks
