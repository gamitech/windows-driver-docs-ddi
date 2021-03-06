---
UID: NF:wudfddi.IWDFDevice.GetPnpState
title: IWDFDevice::GetPnpState method
author: windows-driver-content
description: The GetPnpState method determines whether the given Plug and Play (PnP) property of a device is on or off (or set to the default state).
old-location: wdf\iwdfdevice_getpnpstate.htm
old-project: wdf
ms.assetid: 7214a0e9-5519-4daa-bd2f-cc3c697dd867
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDevice, IWDFDevice::GetPnpState, GetPnpState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFDevice.GetPnpState
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice::GetPnpState method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetPnpState</b> method determines whether the given Plug and Play (PnP) property of a device is on or off (or set to the default state).



## -syntax

````
WDF_TRI_STATE GetPnpState(
  [in] WDF_PNP_STATE State
);
````


## -parameters

### -param State [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_state.md">WDF_PNP_STATE</a>-typed value that identifies the PnP property to retrieve status about. 


## -returns
<b>GetPnpState</b> returns one of the following WDF_TRI_STATE-typed values that identifies the state of the PnP property that is specified in the <i>State</i> parameter.
<dl>
<dt><b>WdfUseDefault (0)</b></dt>
</dl>The PnP property is set to the default state.
<dl>
<dt><b>WdfFalse (1)</b></dt>
</dl>The PnP property is turned off.
<dl>
<dt><b>WdfTrue (2)</b></dt>
</dl>The PnP property is turned on.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>
</dt>
<dt>
<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_state.md">WDF_PNP_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::GetPnpState method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

