---
UID: NF:video.VideoPortReadStateEvent
title: VideoPortReadStateEvent function
author: windows-driver-content
description: The VideoPortReadStateEvent function returns the current state of a given event object: signaled or nonsignaled.
old-location: display\videoportreadstateevent.htm
old-project: display
ms.assetid: b09787b3-aede-4e53-9e22-0e81cf2dadb1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortReadStateEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortReadStateEvent
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: <= DISPATCH_LEVEL
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortReadStateEvent function



## -description
The <b>VideoPortReadStateEvent</b> function returns the current state of a given event object: signaled or nonsignaled.



## -syntax

````
LONG VideoPortReadStateEvent(
  _In_ PVOID  HwDeviceExtension,
  _In_ PEVENT pEvent
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pEvent [in]

Pointer to the event object whose state is to be read.


## -returns
<b>VideoPortReadStateEvent</b> returns a nonzero value if the event object is currently in the signaled state. If the event object is in the nonsignaled state, this function returns zero.


## -remarks
This function is available in Windows XP and later. </p>