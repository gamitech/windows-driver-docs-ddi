---
UID: NS:ntddstor._STORAGE_ZONE_GROUP
title: _STORAGE_ZONE_GROUP
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\storage_zone_group.htm
old-project: storage
ms.assetid: 71CEEE58-22CC-4FB4-83E1-5FCC6563D1D2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_ZONE_GROUP, *PSTORAGE_ZONE_GROUP, STORAGE_ZONE_GROUP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_ZONE_GROUP
req.alt-loc: Ntddstor.h
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
req.typenames: *PSTORAGE_ZONE_GROUP, STORAGE_ZONE_GROUP
---

# _STORAGE_ZONE_GROUP structure



## -description

<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>




## -syntax

````
typedef struct _STORAGE_ZONE_GROUP {
  ULONG               ZoneCount;
   STORAGE_ZONE_TYPES ZoneType;
  ULONGLONG           ZoneSize;
} STORAGE_ZONE_GROUP, *PSTORAGE_ZONE_GROUP;
````


## -struct-fields

### -field ZoneCount

N/A


### -field ZoneType

N/A


### -field ZoneSize

N/A


## -remarks
