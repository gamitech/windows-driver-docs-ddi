---
UID: NF:wdfdevice.WdfDeviceAssignMofResourceName
title: WdfDeviceAssignMofResourceName function
author: windows-driver-content
description: The WdfDeviceAssignMofResourceName method registers a MOF resource name for a specified device.
old-location: wdf\wdfdeviceassignmofresourcename.htm
old-project: wdf
ms.assetid: b4ab0a7b-9c5a-4295-94fc-35310ca8e05b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceAssignMofResourceName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDeviceAssignMofResourceName
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceAssignMofResourceName function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceAssignMofResourceName</b> method registers a MOF resource name for a specified device.



## -syntax

````
NTSTATUS WdfDeviceAssignMofResourceName(
  _In_ WDFDEVICE        Device,
  _In_ PCUNICODE_STRING MofResourceName
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param MofResourceName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that specifies the name of a MOF resource. 


## -returns
If the operation succeeds, <b>WdfDeviceAssignMofResourceName</b> returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The driver has already called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassignmofresourcename.md">WdfDeviceAssignMofResourceName</a>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl> Insufficient memory is available.

 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
A driver that provides a MOF file to support WMI must call <b>WdfDeviceAssignMofResourceName</b>, typically from within its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function. The MOF resource name is the file name that the driver specifies in a <b>MofResource</b> statement in its resource script (RC) file. For more information about specifying a MOF resource name, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542012">Compiling a Driver's MOF File</a>.

A driver that <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">enumerates the devices on a bus</a> can call <b>WdfDeviceAssignMofResourceName</b> for the parent device, and the framework will use the parent's MOF resource name for child devices.

For more information about WMI, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.

The following code example declares a Unicode string that represents a MOF resource name and then registers the name.</p>