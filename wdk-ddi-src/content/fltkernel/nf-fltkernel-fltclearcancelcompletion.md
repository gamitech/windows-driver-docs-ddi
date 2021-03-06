---
UID: NF:fltkernel.FltClearCancelCompletion
title: FltClearCancelCompletion function
author: windows-driver-content
description: FltClearCancelCompletion clears a cancel routine that was specified for an I/O operation.
old-location: ifsk\fltclearcancelcompletion.htm
old-project: ifsk
ms.assetid: 75c66cb7-3378-4951-9180-d1bd9f201a42
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltClearCancelCompletion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltClearCancelCompletion
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: Any level
req.typenames: EXpsFontRestriction
---

# FltClearCancelCompletion function



## -description
<b>FltClearCancelCompletion</b> clears a cancel routine that was specified for an I/O operation. 



## -syntax

````
NTSTATUS FltClearCancelCompletion(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters

### -param CallbackData [in]

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. 


## -returns
If no cancel routine was previously set or if IRP cancellation is already in progress, <b>FltClearCancelCompletion</b> returns STATUS_CANCELLED. Otherwise, it returns STATUS_SUCCESS. 


## -remarks
A minifilter driver calls <b>FltClearCancelCompletion</b> to clear a cancel routine that was specified for an I/O operation by a previous call to <a href="..\fltkernel\nf-fltkernel-fltsetcancelcompletion.md">FltSetCancelCompletion</a>. The operation must be an IRP-based I/O operation. To determine whether a given callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

To cancel an I/O operation, call <a href="..\fltkernel\nf-fltkernel-fltcancelio.md">FltCancelIo</a>. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcancelio.md">FltCancelIo</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetcancelcompletion.md">FltSetCancelCompletion</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltClearCancelCompletion routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

