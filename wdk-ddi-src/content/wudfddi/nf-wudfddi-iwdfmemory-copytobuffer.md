---
UID: NF:wudfddi.IWDFMemory.CopyToBuffer
title: IWDFMemory::CopyToBuffer method
author: windows-driver-content
description: The CopyToBuffer method safely copies data from a memory object to the specified target buffer.
old-location: wdf\iwdfmemory_copytobuffer.htm
old-project: wdf
ms.assetid: c5b34168-b3b8-4559-8b41-982f0a66f01d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFMemory, IWDFMemory::CopyToBuffer, CopyToBuffer
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
req.alt-api: IWDFMemory.CopyToBuffer
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

# IWDFMemory::CopyToBuffer method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CopyToBuffer</b> method safely copies data from a memory object to the specified target buffer.



## -syntax

````
HRESULT CopyToBuffer(
  [in]  ULONG_PTR SourceOffset,
  [out] void      *pTargetBuffer,
  [in]  SIZE_T    NumOfBytesToCopyTo
);
````


## -parameters

### -param SourceOffset [in]

The offset, in bytes, into the memory object to start to copy data from. 


### -param pTargetBuffer [out]

A pointer to the target buffer that data is copied to.


### -param NumOfBytesToCopyTo [in]

The number of bytes to copy to the buffer that <i>pTargetBuffer</i> points to.


## -returns
<b>CopyToBuffer</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

The following code example obtains a memory object from a request object and then copies a specific amount of data from the memory object to a buffer.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFMemory::CopyToBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

