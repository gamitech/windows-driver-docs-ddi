---
UID: NE:wiautil.SKIP_AMOUNT
title: SKIP_AMOUNT
author: windows-driver-content
description: The SKIP_AMOUNT enumeration is used to indicate whether the file and informational headers of an image should be skipped over.
old-location: image\skip_amount.htm
old-project: image
ms.assetid: 4e21b3e9-0383-4464-b87e-beea88123124
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: SKIP_AMOUNT, SKIP_AMOUNT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SKIP_AMOUNT
req.alt-loc: wiautil.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# SKIP_AMOUNT enumeration



## -description
The SKIP_AMOUNT enumeration is used to indicate whether the file and informational headers of an image should be skipped over.



## -syntax

````
typedef enum  { 
  SKIP_OFF      = 0,
  SKIP_FILEHDR  = 1,
  SKIP_BOTHHDR  = 2
} SKIP_AMOUNT;
````


## -enum-fields

### -field SKIP_OFF

Do not skip over either header.


### -field SKIP_FILEHDR

Skip over the file header.


### -field SKIP_BOTHHDR

Skip over both the file and info headers.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540369">CWiauFormatConverter::ConvertToBmp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20SKIP_AMOUNT enumeration%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

