---
UID: NF:printerextension.IPrinterPropertyBag.SetBytes
title: IPrinterPropertyBag::SetBytes method
author: windows-driver-content
description: Writes a byte array property.
old-location: print\iprinterpropertybag_setbytes.htm
old-project: print
ms.assetid: 0138F4F4-658F-4465-8647-17BE488E2FED
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag::SetBytes, SetBytes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: Printerextension.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterPropertyBag.SetBytes
req.alt-loc: Printerextension.h
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
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterPropertyBag::SetBytes method



## -description
Writes a byte array property.



## -syntax

````
HRESULT SetBytes(
  [in]                   BSTR   bstrName,
  [in]                   DWORD  cbValue,
  [in, size_is(cbValue)] BYTE * *rgbValue
);
````


## -parameters

### -param bstrName [in]

The array to write to.


### -param cbValue [in]

The number of bytes to write.


### -param rgbValue [in]

The values to write.


## -returns
This method returns an <b>HRESULT</b> value.


## -remarks
In Windows 8.1 a new flag, PRINTER_ACCESS_MANAGE_LIMITED, has been introduced to grant print queue permissions that are more limited than PRINTER_ACCESS_ADMINISTER, but more powerful than 
PRINTER_ACCESS_USE.

The permissions are a subset of those associated with PRINTER_ACCESS_ADMINISTER. This means that if the currently logged-on user has PRINTER_ACCESS_ADMINISTER permission, the user can gain 
PRINTER_ACCESS_MANAGE_LIMITED access to the queue.

A call to set a property on a queue property bag will fail with ERROR_ACCESS_DENIED, if the user does not have the appropriate permission. This behavior was true before PRINTER_ACCESS_MANAGE_LIMITED was introduced, and it's still the current behavior.


## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterPropertyBag::SetBytes method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

