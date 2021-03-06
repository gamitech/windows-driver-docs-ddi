---
UID: NF:ufxclient.UfxDeviceNotifySuspend
title: UfxDeviceNotifySuspend function
author: windows-driver-content
description: Notifies UFX about a USB bus suspend event.
old-location: buses\ufxdevicenotifysuspend.htm
old-project: usbref
ms.assetid: 80786A5A-E585-4092-814F-B940DD6967C6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UfxDeviceNotifySuspend
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UfxDeviceNotifySuspend
req.alt-loc: ufxclient.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxDeviceNotifySuspend function



## -description
Notifies UFX about a USB bus suspend event.



## -syntax

````
VOID UfxDeviceNotifySuspend(
  [in] UFXDEVICE UfxDevice
);
````


## -parameters

### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


## -returns
This method does not return a value.


## -remarks
The client driver calls <b>UfxDeviceNotifySuspend</b> when it receives a bus suspend event. The default endpoint should be reset on a bus suspend.  The device should move to a low power mode.

The client driver typically calls <b>UfxDeviceNotifySuspend</b> from its <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function.  The following example shows how to handle a suspend event.</p>