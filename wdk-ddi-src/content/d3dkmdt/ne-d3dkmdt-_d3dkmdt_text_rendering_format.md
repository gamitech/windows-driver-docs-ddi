---
UID: NE:d3dkmdt._D3DKMDT_TEXT_RENDERING_FORMAT
title: _D3DKMDT_TEXT_RENDERING_FORMAT
author: windows-driver-content
description: The D3DKMDT_TEXT_RENDERING_FORMAT enumeration is currently not used.
old-location: display\d3dkmdt_text_rendering_format.htm
old-project: display
ms.assetid: 73ec5d3c-d8f6-4db9-b55f-317eab3b4a39
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMDT_TEXT_RENDERING_FORMAT, D3DKMDT_TEXT_RENDERING_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_TEXT_RENDERING_FORMAT
req.alt-loc: d3dkmdt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: D3DKMDT_TEXT_RENDERING_FORMAT
---

# _D3DKMDT_TEXT_RENDERING_FORMAT enumeration



## -description
The D3DKMDT_TEXT_RENDERING_FORMAT enumeration is currently not used.



## -syntax

````
typedef enum _D3DKMDT_TEXT_RENDERING_FORMAT { 
  D3DKMDT_TRF_UNINITIALIZED  = 0
} D3DKMDT_TEXT_RENDERING_FORMAT;
````


## -enum-fields

### -field D3DKMDT_TRF_UNINITIALIZED

Indicates that a variable of type D3DKMDT_TEXT_RENDERING_FORMAT has not yet been assigned a meaningful value.


## -remarks
The <b>Format.Text</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure is a D3DKMDT_TEXT_RENDERING_FORMAT value.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570558">VidPn Source Mode Set Interface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_TEXT_RENDERING_FORMAT enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

