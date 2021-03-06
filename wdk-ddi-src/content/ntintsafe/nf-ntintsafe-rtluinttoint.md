---
UID: NF:ntintsafe.RtlUIntToInt
title: RtlUIntToInt function
author: windows-driver-content
description: Converts a value of type UINT to a value of type INT.
old-location: kernel\rtluinttoint.htm
old-project: kernel
ms.assetid: 5C595F39-3F47-4B4D-B6C6-6CBC5848AA4B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUIntToInt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlUIntToInt
req.alt-loc: Ntintsafe.h
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
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntToInt function



## -description
Converts a value of type <b>UINT</b> to a value of type <b>INT</b>.



## -syntax

````
NTSTATUS RtlUIntToInt(
  _In_  UINT uOperand,
  _Out_ INT  *piResult
);
````


## -parameters

### -param uOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>