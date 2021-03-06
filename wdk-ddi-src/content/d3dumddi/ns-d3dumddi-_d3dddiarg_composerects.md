---
UID: NS:d3dumddi._D3DDDIARG_COMPOSERECTS
title: _D3DDDIARG_COMPOSERECTS
author: windows-driver-content
description: The D3DDDIARG_COMPOSERECTS structure describes the parameters that are used to compose rectangular areas.
old-location: display\d3dddiarg_composerects.htm
old-project: display
ms.assetid: 9360f9c4-e30e-4fc0-ade7-1d98ff8b1d1b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_COMPOSERECTS, D3DDDIARG_COMPOSERECTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_COMPOSERECTS
req.alt-loc: d3dumddi.h
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
req.typenames: D3DDDIARG_COMPOSERECTS
---

# _D3DDDIARG_COMPOSERECTS structure



## -description
The D3DDDIARG_COMPOSERECTS structure describes the parameters that are used to compose rectangular areas. 



## -syntax

````
typedef struct _D3DDDIARG_COMPOSERECTS {
  HANDLE                hSrcResource;
  UINT                  SrcSubResourceIndex;
  HANDLE                hDstResource;
  UINT                  DstSubResourceIndex;
  HANDLE                hSrcRectDescsVB;
  UINT                  NumRects;
  HANDLE                hDstRectDescsVB;
  D3DDDI_COMPOSERECTSOP Operation;
  INT                   XOffset;
  INT                   YOffset;
} D3DDDIARG_COMPOSERECTS;
````


## -struct-fields

### -field hSrcResource

[in] A handle to the source resource that contains the source surface. When the surface is created, the user-mode display driver receives the D3DDDIFMT_A1 (one bit per pixel) value in the <b>Format</b> member and the <b>TextApi</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function. The surface must be created as part of a texture.


### -field SrcSubResourceIndex

[in] The index to the source surface within the source resource. 


### -field hDstResource

[in] A handle to the destination resource that contains the destination surface. When the surface is created, the user-mode display driver receives the D3DDDIFMT_A1 (one bit per pixel) value in the <b>Format</b> member of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>. The surface must be created as part of a texture. The surface might have been created with the <b>TextApi</b> bit-field flag. 


### -field DstSubResourceIndex

[in] The index to the destination surface within the destination resource. 


### -field hSrcRectDescsVB

[in] A handle to a vertex buffer that contains an array of D3DCOMPOSERECTSRCDESC structures. Each element in the array defines a rectangle on the source surface. When the vertex buffer is created, the user-mode display driver receives the <b>TextApi</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function. 


### -field NumRects

[in] The number of rectangular areas to copy, which is the number of D3DCOMPOSERECTDSTDESC structures in the vertex buffer that is identified by the <b>hDstRectDescsVB</b> member. Drivers should ignore calls to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_composerects.md">ComposeRects</a> with <b>NumRects</b> set to greater than 0xFFFF.


### -field hDstRectDescsVB

[in] A handle to a vertex buffer that contains an array of D3DCOMPOSERECTDSTDESC structures. Each element in the array defines where to copy a source rectangle on the destination surface. For more information, see the following Remarks section. When the vertex buffer is created, the user-mode display driver receives the <b>TextApi</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function. 


### -field Operation

[in] A D3DDDI_COMPOSERECTSOP value that describes how to compose the rectangular areas. This member can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DDDICOMPOSERECTS_COPY

</td>
<td>
Copy each source bit to the destination.

</td>
</tr>
<tr>
<td>
D3DDDICOMPOSERECTS_OR

</td>
<td>
Combine source and destination bits in an OR operation and copy to the destination. 

</td>
</tr>
<tr>
<td>
D3DDDICOMPOSERECTS_AND

</td>
<td>
Combine source and destination bits in an AND operation and copy to the destination. 

</td>
</tr>
<tr>
<td>
D3DDDICOMPOSERECTS_NEG

</td>
<td>
Combine the negative of the source bits with the destination bits and copy to the destination. [Dest bit &amp; (~ Src bit)]

</td>
</tr>
</table>
 


### -field XOffset

[in] An offset to add to the <i>x</i>-coordinates of all of the destination rectangular areas. The offset can be negative, which might cause the resultant rectangles to be rejected or clipped. 


### -field YOffset

[in] An offset to add to the <i>y</i>-coordinates of all of the destination rectangular areas. The offset can be negative, which might cause the resultant rectangles to be rejected or clipped. 


## -remarks
The vertex buffers that contain the composing instructions are created with D3DUSAGE_TEXTAPI usage. The following code defines the structures that are contained in the vertex buffer arrays. For more information about these structures, see the DirectX SDK documentation.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_composerects.md">ComposeRects</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_COMPOSERECTS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

