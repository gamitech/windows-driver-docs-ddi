---
UID: NS:ndis._NDIS_RECEIVE_QUEUE_STATE
title: _NDIS_RECEIVE_QUEUE_STATE
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_STATE structure contains information about the operational state of a receive queue.
old-location: netvista\ndis_receive_queue_state.htm
old-project: netvista
ms.assetid: e997fce6-ee3a-433f-b9b7-3e2932093a1a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_RECEIVE_QUEUE_STATE, NDIS_RECEIVE_QUEUE_STATE, *PNDIS_RECEIVE_QUEUE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_RECEIVE_QUEUE_STATE
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.typenames: NDIS_RECEIVE_QUEUE_STATE, *PNDIS_RECEIVE_QUEUE_STATE
---

# _NDIS_RECEIVE_QUEUE_STATE structure



## -description
The <b>NDIS_RECEIVE_QUEUE_STATE</b> structure contains information about the operational state of a receive
  queue.



## -syntax

````
typedef struct _NDIS_RECEIVE_QUEUE_STATE {
  NDIS_OBJECT_HEADER                   Header;
  ULONG                                Flags;
  NDIS_RECEIVE_QUEUE_ID                QueueId;
  NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE QueueState;
} NDIS_RECEIVE_QUEUE_STATE, *PNDIS_RECEIVE_QUEUE_STATE;
````


## -struct-fields

### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_QUEUE_STATE</b>  structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_QUEUE_STATE_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_RECEIVE_QUEUE_STATE_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field QueueId

An <b>NDIS_RECEIVE_QUEUE_ID</b> type value that contains a queue identifier. The queue identifier is an
     integer value between zero and the number of queues that the network adapter supports. A value of <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b> specifies
     the default receive queue.


### -field QueueState

An 
     <a href="..\ntddndis\ne-ntddndis-_ndis_receive_queue_operational_state.md">NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</a> enumeration value that specifies the operational state of the
     receive queue.


## -remarks
The <b>NDIS_RECEIVE_QUEUE_STATE</b> structure is used in the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567214">
    NDIS_STATUS_RECEIVE_QUEUE_STATE</a> status indication.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ntddndis\ne-ntddndis-_ndis_receive_queue_operational_state.md">
   NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567214">
   NDIS_STATUS_RECEIVE_QUEUE_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_QUEUE_STATE structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

