---
UID: NS:ntddndis._NDIS_IPSEC_OFFLOAD_V2
title: _NDIS_IPSEC_OFFLOAD_V2
author: windows-driver-content
description: The NDIS_IPSEC_OFFLOAD_V2 structure provides information about Internet protocol security (IPsec) version 2 task offload capabilities in the NDIS_OFFLOAD structure.
old-location: netvista\ndis_ipsec_offload_v2.htm
old-project: netvista
ms.assetid: 2319fe88-8f32-415c-bea1-4b7e723f6dbb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_IPSEC_OFFLOAD_V2, *PNDIS_IPSEC_OFFLOAD_V2, NDIS_IPSEC_OFFLOAD_V2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_IPSEC_OFFLOAD_V2
req.alt-loc: ntddndis.h
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
req.typenames: *PNDIS_IPSEC_OFFLOAD_V2, NDIS_IPSEC_OFFLOAD_V2
---

# _NDIS_IPSEC_OFFLOAD_V2 structure



## -description
<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The NDIS_IPSEC_OFFLOAD_V2 structure provides information about Internet protocol security (IPsec)
  version 2 task offload capabilities in the 
  <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure.



## -syntax

````
typedef struct _NDIS_IPSEC_OFFLOAD_V2 {
  ULONG   Encapsulation;
  BOOLEAN IPv6Supported;
  BOOLEAN IPv4Options;
  BOOLEAN IPv6NonIPsecExtensionHeaders;
  BOOLEAN Ah;
  BOOLEAN Esp;
  BOOLEAN AhEspCombined;
  BOOLEAN Transport;
  BOOLEAN Tunnel;
  BOOLEAN TransportTunnelCombined;
  BOOLEAN LsoSupported;
  BOOLEAN ExtendedSequenceNumbers;
  ULONG   UdpEsp;
  ULONG   AuthenticationAlgorithms;
  ULONG   EncryptionAlgorithms;
  ULONG   SaOffloadCapacity;
} NDIS_IPSEC_OFFLOAD_V2, *PNDIS_IPSEC_OFFLOAD_V2;
````


## -struct-fields

### -field Encapsulation

The MAC encapsulation types that are supported for IPsec offload. For more information about this
     member, see the following Remarks section.


### -field IPv6Supported

A BOOLEAN value that is set to <b>TRUE</b> if IPsec offload processing on IPv6 traffic is supported.
     Otherwise, this member is <b>FALSE</b>.


### -field IPv4Options

A BOOLEAN value that is set to <b>TRUE</b> if the NIC supports IPsec offload of packets with IPv4
     options. Otherwise, this member is <b>FALSE</b>.


### -field IPv6NonIPsecExtensionHeaders

A BOOLEAN value that is set to <b>TRUE</b> if the NIC supports IPsec offload processing for packets with
     non-IPsec IPv6 extension headers in addition to IPsec headers. Otherwise, this member is <b>FALSE</b>.


### -field Ah

A BOOLEAN value that is set to <b>TRUE</b> if the NIC can perform IPsec offload operations on send and
     receive packets that contain an authentication header (AH) security payload. Otherwise, this member is
     <b>FALSE</b>.


### -field Esp

A BOOLEAN value that is set to <b>TRUE</b> if the NIC can perform IPsec offload operations on send and
     receive packets that contain an encapsulating security payload (ESP). Otherwise, this member is
     <b>FALSE</b>.


### -field AhEspCombined

A BOOLEAN value that is set to <b>TRUE</b> if the NIC can perform IPsec offload operations on send and
     receive packets that contain both an AH payload and an ESP payload. Otherwise, this member is
     <b>FALSE</b>.


### -field Transport

A BOOLEAN value that is set to <b>TRUE</b> if the NIC can process security payloads for the
     transport-mode portion of send and receive packets. (The transport-mode portion of a packet pertains to
     an end-to-end connection.) Otherwise, this member is <b>FALSE</b>.


### -field Tunnel

A BOOLEAN value that is set to <b>TRUE</b> if the NIC can process security payloads for the tunnel-mode
     portion of send and receive packets. (The tunnel-mode portion of a packet pertains to a tunnel
     connection.) Otherwise, this member is <b>FALSE</b>.
     

<div class="alert"><b>Note</b>  When the IPsec layer sends tunnel packets over an IPsec task offload interface,
     the IPsec layer ensures that large send offload (LSO) is not used for those packets.</div>
<div> </div>

### -field TransportTunnelCombined

A BOOLEAN value that is set to <b>TRUE</b> if the NIC can process security payloads for both the
     transport-mode portion and the tunnel-mode portion of send and receive packets. Otherwise, this member
     is <b>FALSE</b>. The transport-mode portion of a packet pertains to an end-to-end connection. The tunnel-mode
     portion of a packet pertains to a tunnel connection.


### -field LsoSupported

A BOOLEAN value that is set to <b>TRUE</b> if the NIC supports large send offload (LSO). Otherwise, this
     member is <b>FALSE</b>. Note that the LSO capabilities of the NIC are specified in the 
     <b>LsoV1</b> or 
     <b>LsoV2</b> members of the 
     <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure. The 
     <b>LsoSupported</b> flag indicates that the capabilities that are specified in those members are also
     valid if the connection is secured with IPsec.


### -field ExtendedSequenceNumbers

A BOOLEAN value that is set to <b>TRUE</b> if the NIC supports IPsec extended sequence numbers.
     Otherwise, this member is <b>FALSE</b>.


### -field UdpEsp

The types of UDP-encapsulated ESP data packets that the NIC can parse. For a description of the
     UDP-encapsulation types, see 
     <a href="https://msdn.microsoft.com/126d2fd5-778e-43ff-87f6-5b0b54a83bac">UDP-ESP Encapsulation Types</a>. This
     member can be one or more of the following flags:
     




### -field IPSEC_OFFLOAD_V2_UDP_ESP_ENCAPSULATION_NONE

IPsec offload processing is not available for any UDP encapsulation type.


### -field IPSEC_OFFLOAD_V2_UDP_ESP_ENCAPSULATION_TRANSPORT

IPsec offload is supported for an ESP-encapsulated transport-mode packet that is encapsulated by
       UDP.


### -field IPSEC_OFFLOAD_V2_UDP_ESP_ENCAPSULATION_TUNNEL

IPsec offload is supported for the tunnel-mode portion of a packet that is UDP-encapsulated. The
       transport-mode portion of the packet is not UDP-encapsulated and is not ESP-protected.


### -field IPSEC_OFFLOAD_V2_TRANSPORT_OVER_UDP_ESP_ENCAPSULATION_TUNNEL

IPsec offload is supported for the tunnel-mode portion of a packet that is UDP-encapsulated. The
       transport-mode portion of a packet is not UDP-encapsulated but is ESP-protected.

</dd>
</dl>



### -field IPSEC_OFFLOAD_V2_UDP_ESP_ENCAPSULATION_TRANSPORT_OVER_TUNNEL

IPsec offload is supported for the tunnel-mode portion of a packet that is not UDP-encapsulated.
       The transport-mode portion of a packet is UDP-encapsulated and ESP-protected.

</dd>
</dl>

### -field AuthenticationAlgorithms

A bit mask that identifies the IPsec authentication algorithms that the NIC supports. Miniport
     drivers specify a bitwise OR of the following values:
     




### -field IPSEC_OFFLOAD_V2_AUTHENTICATION_MD5

The NIC can use the keyed message digest 5 (MD5) algorithm for computing or validating a
       cryptographic checksum.


### -field IPSEC_OFFLOAD_V2_AUTHENTICATION_SHA_1

The NIC can use the secure hash algorithm (SHA) 1 algorithm for computing or validating a
       cryptographic checksum.


### -field IPSEC_OFFLOAD_V2_AUTHENTICATION_SHA_256

The NIC can use the SHA 256 algorithm for computing or validating a cryptographic
       checksum.


### -field IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_128

The NIC can use the Advanced Encryption Standard - Galois/Counter Mode (AES-GMAC) 128 algorithm
       for computing or validating a cryptographic checksum.


### -field IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_192

The NIC can use the AES-GMAC 192 algorithm for computing or validating a cryptographic
       checksum.


### -field IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_256

The NIC can use the AES-GMAC 256 algorithm for computing or validating a cryptographic
       checksum.

</dd>
</dl>

### -field EncryptionAlgorithms

A bit mask that identifies the IPsec encryption algorithms that the NIC supports. This bit mask is
     a bitwise OR of the following values:
     




### -field IPSEC_OFFLOAD_V2_ENCRYPTION_NONE

The NIC can use null encryption--that is, the ESP payload without encryption but with
       authentication information.


### -field IPSEC_OFFLOAD_V2_ENCRYPTION_DES_CBC

The NIC can use the DES algorithm for encrypting and decrypting ESP payloads.


### -field IPSEC_OFFLOAD_V2_ENCRYPTION_3_DES_CBC

The NIC can use the triple-DES algorithm for encrypting and decrypting ESP payloads.


### -field IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_128

The NIC can use the AES-GCM 128 algorithm for encrypting and computing a cryptographic checksum
       or decrypting and validating a cryptographic checksum for an ESP payload. Note that this algorithm is
       a combined mode algorithm.


### -field IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_192

The NIC can use the AES-GCM 192 algorithm for encrypting and computing a cryptographic checksum
       or decrypting and validating a cryptographic checksum for an ESP payload. Note that this algorithm is
       a combined mode algorithm.


### -field IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_256

The NIC can use the AES-GCM 256 algorithm for encrypting and computing a cryptographic checksum
       or decrypting and validating a cryptographic checksum for an ESP payload. Note that this algorithm is
       a combined mode algorithm.


### -field IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_128

The NIC can use the Advanced Encryption Standard - cipher-block chaining mode (AES-CBC) 128
       algorithm for encrypting and decrypting ESP payloads.


### -field IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_192

The NIC can use the AES-CBC 192 algorithm for encrypting and decrypting ESP payloads.


### -field IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_256

The NIC can use the AES-CBC 256 algorithm for encrypting and decrypting ESP payloads.

</dd>
</dl>

### -field SaOffloadCapacity

The number of SA bundles, which might include ESP or AH or both, that can be offloaded to the NIC.
     The TCP/IP maintains a count of the number of offloaded SA bundles and should not add more than the
     maximum number of SA bundles that the miniport driver reported.


## -remarks
In NDIS 6.1 and later versions, the NDIS_IPSEC_OFFLOAD_V2 structure is used in the 
    <b>IPsecV2</b> member of the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure. The
    NDIS_IPSEC_OFFLOAD_V2 structure specifies the current or supported capabilities that a miniport adapter
    provides for IPsec offload processing.

NDIS_OFFLOAD is used in the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure, 
    <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure, 
    <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">
    NDIS_FILTER_ATTACH_PARAMETERS</a> structure, 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID, and the 
    <a href="netvista.ndis_status_task_offload_current_config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

For 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>,
    the NDIS_OFFLOAD structure specifies the task offload capabilities that a miniport adapter supports. If
    the current offload capabilities change, a miniport driver reports the new capabilities in an 
    <a href="netvista.ndis_status_task_offload_current_config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

The 
    <b>Encapsulation</b> member of NDIS_IPSEC_OFFLOAD_V2 defines the MAC encapsulations that a miniport
    adapter supports for IPsec offload.

In response to an 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> query request, NDIS provides a bitwise OR of the encapsulation
    flags, which indicate the supported encapsulation settings, in the 
    <b>Encapsulation</b> member. Miniport drivers must provide Ethernet encapsulation
    (NDIS_ENCAPSULATION_IEEE_802_3). The other types of encapsulation are optional.

For an 
    <a href="netvista.ndis_status_task_offload_current_config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication, the miniport driver provides a bitwise
    OR of the encapsulation flags, which indicate the current capabilities, in the 
    <b>Encapsulation</b> member.

The following flags are defined for the 
    <b>Encapsulation</b> member:



Specifies that no encapsulation offload is supported.

Specifies NULL encapsulation.

Specifies IEEE 802.3 encapsulation.

Specifies IEEE 802.3p and IEEE 802.3q encapsulation.

Specifies that IEEE 802.3p and IEEE 802.3q encapsulation settings are specified in the 
      <b>NetBufferListInfo</b> member of each 
      <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

Specifies logical link control (LLC) encapsulation for routed protocols, as described in RFC
      1483. This flag is also used to indicate Ethernet LLC/SNAP encapsulation.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_ipsec_offload_v1.md">NDIS_IPSEC_OFFLOAD_V1</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="netvista.ndis_status_task_offload_current_config">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IPSEC_OFFLOAD_V2 structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

