---
UID: NF:dbgeng.IDebugClient5.GetNumberInputCallbacks
title: IDebugClient5::GetNumberInputCallbacks method
author: windows-driver-content
description: The GetNumberInputCallbacks method returns the number of input callbacks registered over all clients.
old-location: debugger\getnumberinputcallbacks.htm
old-project: debugger
ms.assetid: 25188616-ac1a-4699-9343-0fa88e27d9b8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient5, IDebugClient5::GetNumberInputCallbacks, GetNumberInputCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugClient5.GetNumberInputCallbacks
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugClient5::GetNumberInputCallbacks method



## -description
The <b>GetNumberInputCallbacks</b> method returns the number of <a href="debugger.using_input_and_output#input_callbacks#input_callbacks">input callbacks</a> registered over all clients.



## -syntax

````
HRESULT GetNumberInputCallbacks(
  [out] PULONG Count
);
````


## -parameters

### -param Count [out]

Receives the number of input callbacks that have been registered.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
Each client can have at most one input callback registered with it.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546892">GetInputCallbacks</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556721">SetInputCallbacks</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547931">GetNumberOutputCallbacks</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547896">GetNumberEventCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::GetNumberInputCallbacks method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

