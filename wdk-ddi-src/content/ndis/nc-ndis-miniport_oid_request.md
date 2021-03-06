---
UID: NC:ndis.MINIPORT_OID_REQUEST
title: MINIPORT_OID_REQUEST
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportOidRequest function to handle an OID request to query or set information in the driver.
old-location: netvista\miniportoidrequest.htm
old-project: netvista
ms.assetid: 733d84f5-c1d4-42a0-a59b-4ba50247f165
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportOidRequest
req.alt-loc: Ndis.h
req.ddi-compliance: NdisOidComplete, NdisOidDoubleComplete, NdisOidDoubleRequest, NdisTimedOidComplete, WlanAssociation, WlanDisassociation, WlanTimedAssociation, WlanTimedConnectionRoaming, WlanTimedConnectRequest, WlanTimedLinkQuality, WlanTimedScan
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_OID_REQUEST callback



## -description
NDIS calls a miniport driver's 
   <i>MiniportOidRequest</i> function to handle an OID request to query or set information in the driver.



## -prototype

````
MINIPORT_OID_REQUEST MiniportOidRequest;

NDIS_STATUS MiniportOidRequest(
  _In_ NDIS_HANDLE       MiniportAdapterContext,
  _In_ PNDIS_OID_REQUEST OidRequest
)
{ ... }
````


## -parameters

### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


### -param OidRequest [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that contains
     both the buffer and the request packet for the miniport driver to handle. Depending on the request, the
     driver returns requested information in the structure provided.


## -returns
<i>MiniportOidRequest</i> can return one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The miniport driver has either set or obtained the data as requested.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>The miniport driver will complete the request asynchronously. After the miniport driver has
       completed all processing, it must call the 
       <a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">
       NdisMOidRequestComplete</a> function to inform NDIS that the request is complete.
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>The request, specified at 
       <i>OidRequest</i>, is invalid or not recognized.
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>The request, specified at 
       <i>OidRequest</i>, is recognized, but not supported by the miniport driver.
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>The buffer, supplied at 
       <i>OidRequest</i>, is too small to hold the requested data.
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH</b></dt>
</dl>The value specified in the 
       <b>InformationBufferLength</b> member of the NDIS_OID_REQUEST-structure at 
       <i>OidRequest</i> is incorrect for the specified OID_
       <i>XXX</i> code.
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>One or more of the parameters specified for the request at 
       <i>OidRequest</i> is invalid.
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>After calling the 
       <a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
       MiniportDevicePnPEventNotify</a> function to indicate a surprise removal, NDIS calls the driver's 
       <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function. If the
       driver receives any OID requests before NDIS calls 
       <i>MiniportHaltEx</i>, it should immediately complete such requests with a status value of
       NDIS_STATUS_NOT_ACCEPTED.
<dl>
<dt><b>NDIS_STATUS_REQUEST_ABORTED</b></dt>
</dl>The miniport driver stopped processing the request. For example, NDIS called the 
       <a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> function.
<dl>
<dt><b>NDIS_STATUS_INDICATION_REQUIRED</b></dt>
</dl>The miniport driver will provide an OID completion status with a subsequent status indication. A
       miniport driver cannot return NDIS_STATUS_INDICATION_REQUIRED unless the particular OID allows it. To
       determine if this status is allowed, see the OID reference page.. For more information about
       NDIS_STATUS_INDICATION_REQUIRED, see 
       <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> and 
       <a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a>.

 


## -remarks
A driver specifies the 
    <i>MiniportOidRequest</i> entry point when it calls the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function.

NDIS calls the 
    <i>MiniportOidRequest</i> function either on its own behalf or on behalf of a bound protocol driver that
    called the 
    <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a> function. Miniport drivers
    should examine the request supplied at 
    <i>OidRequest</i> and take the action requested. For more information about the OIDs that miniport drivers
    handle, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566707">NDIS OIDs</a>.

Note that NDIS does not validate the OID-specific contents at 
    <i>OidRequest</i> . Therefore, the driver itself must validate these contents. If the driver determines
    that the value to be set is out of bounds, it should fail the request and return
    NDIS_STATUS_INVALID_DATA.

If 
    <i>MiniportOidRequest</i> returns NDIS_STATUS_PENDING, NDIS will not call 
    <i>MiniportOidRequest</i> with another request, for the miniport adapter specified at 
    MiniportAdapterContext, until the pending request is completed.

NDIS calls
    <i>MiniportOidRequest</i> at IRQL == PASSIVE_LEVEL .

To define a <i>MiniportOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportOidRequest</i> function that is named "MyOidRequest", use the <b>MINIPORT_OID_REQUEST</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
   MiniportDevicePnPEventNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">NdisMOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_OID_REQUEST callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

