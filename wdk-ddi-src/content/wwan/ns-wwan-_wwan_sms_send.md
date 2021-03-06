---
UID: NS:wwan._WWAN_SMS_SEND
title: _WWAN_SMS_SEND
author: windows-driver-content
description: The WWAN_SMS_SEND structure represents an SMS text message to send.
old-location: netvista\wwan_sms_send.htm
old-project: netvista
ms.assetid: 2d2e5d13-56ca-452c-86fd-4a48b11d53ab
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WWAN_SMS_SEND, *PWWAN_SMS_SEND, WWAN_SMS_SEND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_SMS_SEND
req.alt-loc: wwan.h
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
req.typenames: *PWWAN_SMS_SEND, WWAN_SMS_SEND
req.product: Windows 10 or later.
---

# _WWAN_SMS_SEND structure



## -description
The WWAN_SMS_SEND structure represents an SMS text message to send.



## -syntax

````
typedef struct _WWAN_SMS_SEND {
  WWAN_SMS_FORMAT SmsFormat;
  union {
    WWAN_SMS_SEND_PDU  Pdu;
    WWAN_SMS_SEND_CDMA Cdma;
  } u;
} WWAN_SMS_SEND, *PWWAN_SMS_SEND;
````


## -struct-fields

### -field SmsFormat

The format of the SMS text message.


### -field u

Container union for the different SMS formats.


### -field Pdu

Short message data types to be used depending on the value of 
      <b>SmsFormat</b> as shown in the following table.
      

<table>
<tr>
<th>SmsFormat</th>
<th>Member to use</th>
</tr>
<tr>
<td>
WwanSmsFormatPdu

</td>
<td>
Pdu

</td>
</tr>
<tr>
<td>
WwanSmsFormatCdma

</td>
<td>
Cdma

</td>
</tr>
</table>
 


### -field Cdma

Short message data types to be used depending on the value of 
      <b>SmsFormat</b> as shown in the following table.
      

<table>
<tr>
<th>SmsFormat</th>
<th>Member to use</th>
</tr>
<tr>
<td>
WwanSmsFormatPdu

</td>
<td>
Pdu

</td>
</tr>
<tr>
<td>
WwanSmsFormatCdma

</td>
<td>
Cdma

</td>
</tr>
</table>
 

</dd>
</dl>

## -remarks


## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan-_wwan_sms_send_pdu.md">WWAN_SMS_SEND_PDU</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_sms_send_cdma.md">WWAN_SMS_SEND_CDMA</a>
</dt>
<dt>
<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_sms_send.md">NDIS_WWAN_SMS_SEND</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_SEND structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

