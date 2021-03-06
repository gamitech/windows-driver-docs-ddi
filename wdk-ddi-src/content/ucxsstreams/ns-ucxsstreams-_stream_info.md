---
UID: NS:ucxsstreams._STREAM_INFO
title: _STREAM_INFO
author: windows-driver-content
description: This structure stores information about a stream associated with a bulk endpoint.
old-location: buses\_stream_info.htm
old-project: usbref
ms.assetid: B8AE8866-AC13-4E7B-8815-70846DEECA12
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _STREAM_INFO, STREAM_INFO, *PSTREAM_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxsstreams.h
req.include-header: Ucxclass.h, Ucxstreams.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STREAM_INFO
req.alt-loc: ucxsstreams.h
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
req.typenames: STREAM_INFO, *PSTREAM_INFO
req.product: Windows 10 or later.
---

# _STREAM_INFO structure



## -description
This structure stores information about a stream associated with a bulk endpoint.



## -syntax

````
typedef struct _STREAM_INFO {
  ULONG    Size;
  WDFQUEUE WdfQueue;
  ULONG    StreamId;
} STREAM_INFO, *P_STREAM_INFO;
````


## -struct-fields

### -field Size

The size in bytes of this structure.


### -field WdfQueue

A handle to the framework queue object that contains streams.


### -field StreamId

The stream identifier. The open-static streams request obtains stream identifiers that are assigned by the USB driver stack.


## -remarks
