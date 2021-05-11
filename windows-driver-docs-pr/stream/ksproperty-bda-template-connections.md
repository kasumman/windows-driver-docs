---
title: KSPROPERTY\_BDA\_TEMPLATE\_CONNECTIONS
description: Clients use KSPROPERTY\_BDA\_TEMPLATE\_CONNECTIONS to retrieve a list of connections between pins and nodes in a template topology.
keywords: ["KSPROPERTY_BDA_TEMPLATE_CONNECTIONS Streaming Media Devices"]
topic_type:
- apiref
api_name:
- KSPROPERTY_BDA_TEMPLATE_CONNECTIONS
api_location:
- Bdamedia.h
api_type:
- HeaderDef
ms.date: 11/28/2017
ms.localizationpriority: medium
---

# KSPROPERTY\_BDA\_TEMPLATE\_CONNECTIONS


Clients use KSPROPERTY\_BDA\_TEMPLATE\_CONNECTIONS to retrieve a list of connections between pins and nodes in a template topology.

## <span id="ddk_ksproperty_bda_template_connections_ks"></span><span id="DDK_KSPROPERTY_BDA_TEMPLATE_CONNECTIONS_KS"></span>


### Usage Summary Table

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th>Get</th>
<th>Set</th>
<th>Target</th>
<th>Property descriptor type</th>
<th>Property value type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Yes</p></td>
<td><p>No</p></td>
<td><p>Filter</p></td>
<td><p>KSPROPERTY</p></td>
<td><p>BDA_TEMPLATE_CONNECTION</p></td>
</tr>
</tbody>
</table>

 

## Remarks

The returned BDA\_TEMPLATE\_CONNECTION structure describes a connection in a template topology.

The list of connections between pins and nodes in a template topology is an array of BDA\_TEMPLATE\_CONNECTION structures.

## Requirements

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Header</p></td>
<td>Bdamedia.h (include Bdamedia.h)</td>
</tr>
</tbody>
</table>

## See also


[**BdaPropertyTemplateConnections**](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdapropertytemplateconnections)

[**BDA\_TEMPLATE\_CONNECTION**](/windows-hardware/drivers/ddi/bdatypes/ns-bdatypes-_bda_template_connection)

[**KSPIN\_DESCRIPTOR\_EX**](/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex)

[**KSPROPERTY**](/windows-hardware/drivers/ddi/ks/ns-ks-ksidentifier)

 

