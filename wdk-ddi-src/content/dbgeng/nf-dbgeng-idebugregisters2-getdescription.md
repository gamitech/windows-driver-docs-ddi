---
UID: NF:dbgeng.IDebugRegisters2.GetDescription
title: IDebugRegisters2::GetDescription method
author: windows-driver-content
description: The GetDescription method returns the description of a register.
old-location: debugger\getdescription.htm
old-project: debugger
ms.assetid: 895d18e7-673e-41bb-a3be-eb5b4a778880
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugRegisters2, IDebugRegisters2::GetDescription, GetDescription
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugRegisters.GetDescription,IDebugRegisters2.GetDescription
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

# IDebugRegisters2::GetDescription method



## -description
The <b>GetDescription</b>  method returns the description of a register.



## -syntax

````
HRESULT GetDescription(
  [in]            ULONG                       Register,
  [out, optional] PSTR                        NameBuffer,
  [in]            ULONG                       NameBufferSize,
  [out, optional] PULONG                      NameSize,
  [out, optional] PDEBUG_REGISTER_DESCRIPTION Desc
);
````


## -parameters

### -param Register [in]

Specifies the index of the register for which the description is requested.


### -param NameBuffer [out, optional]

Specifies the buffer in which to store the name of the register.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size, in characters, of the buffer that  <i>NameBuffer</i> specifies.


### -param NameSize [out, optional]

Receives the size, in characters, of the register's name in <i>NameBuffer</i> buffer.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


### -param Desc [out, optional]

Receives the description of the register.  See <a href="..\dbgeng\ns-dbgeng-_debug_register_description.md">DEBUG_REGISTER_DESCRIPTION</a> for more details.


## -returns
This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful. However, the buffer was not large enough to hold the register's name, so it was truncated.
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>No target machine has been specified, or a description of the register could not be found.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The index of the register requested is greater than the total number of registers on the target's machine.

 


## -remarks
For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.</p>