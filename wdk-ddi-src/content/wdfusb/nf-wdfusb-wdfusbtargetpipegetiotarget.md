---
UID: NF:wdfusb.WdfUsbTargetPipeGetIoTarget
title: WdfUsbTargetPipeGetIoTarget function
author: windows-driver-content
description: The WdfUsbTargetPipeGetIoTarget method returns a handle to the I/O target object that is associated with a specified USB pipe.
old-location: wdf\wdfusbtargetpipegetiotarget.htm
old-project: wdf
ms.assetid: 73835623-fa35-46f0-90a2-62d6d596dc64
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfUsbTargetPipeGetIoTarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfUsbTargetPipeGetIoTarget
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, FailD0EntryIoTargetState
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetPipeGetIoTarget function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeGetIoTarget</b> method returns a handle to the I/O target object that is associated with a specified USB pipe.



## -syntax

````
WDFIOTARGET WdfUsbTargetPipeGetIoTarget(
  _In_ WDFUSBPIPE Pipe
);
````


## -parameters

### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>.


## -returns
<b>WdfUsbTargetPipeGetIoTarget</b> returns a handle to the I/O target object that is associated with the specified pipe object.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
For more information about the <b>WdfUsbTargetPipeGetIoTarget</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

The following code example shows how an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function can start a continuous reader for a USB pipe. 


## -see-also
<dl>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetiotarget.md">WdfUsbTargetDeviceGetIoTarget</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetPipeGetIoTarget method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

