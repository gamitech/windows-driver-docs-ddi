---
UID: NF:fltkernel.FltInsertExtraCreateParameter
title: FltInsertExtraCreateParameter function
author: windows-driver-content
description: The FltInsertExtraCreateParameter routine inserts an extra create parameter (ECP) context structure into an ECP list.
old-location: ifsk\fltinsertextracreateparameter.htm
old-project: ifsk
ms.assetid: b4cc03e9-225f-491f-97df-064fdedc8182
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltInsertExtraCreateParameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltInsertExtraCreateParameter
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
req.typenames: EXpsFontRestriction
---

# FltInsertExtraCreateParameter function



## -description
The <b>FltInsertExtraCreateParameter</b> routine inserts an extra create parameter (ECP) context structure into an ECP list.



## -syntax

````
NTSTATUS FltInsertExtraCreateParameter(
  _In_    PFLT_FILTER Filter,
  _Inout_ PECP_LIST   EcpList,
  _Inout_ PVOID       EcpContext
);
````


## -parameters

### -param Filter [in]

Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpList [in, out]

Pointer to the ECP list structure to which the ECP context structure, provided by the <i>EcpContext</i> parameter, should be added.


### -param EcpContext [in, out]

Pointer to the ECP context structure to be added to the ECP list, provided by the <i>EcpList</i> parameter.


## -returns
<b>FltInsertExtraCreateParameter</b> returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The given ECP context structure was successfully inserted into the given ECP list.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The given ECP context structure already exists in the given ECP list.  In the context of ECP list insertion, two ECP context structures are considered to be identical if they contain equal GUID values.

 


## -remarks
The <b>FltInsertExtraCreateParameter</b> routine assumes that the given ECP context structure to be inserted into the given ECP list was previously allocated by the <a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a> routine.

Each ECP context structure inserted into the ECP list must have a unique GUID value. This unique value is set when the ECP context structure is allocated by the <a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a> routine. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltInsertExtraCreateParameter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

