---
title: Metodo sedisable (classe ServerNetworkProtocolIPAddress) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 7a7cc8cc-9fb8-4bf5-b483-2150d633ee10
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 9fbe928de1144c3065ddabb07bfd48606fdcea51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712951"
---
# <a name="setdisable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="77cc5-102">Metodo SetDisable (classe ServerNetworkProtocolIPAddress)</span><span class="sxs-lookup"><span data-stu-id="77cc5-102">SetDisable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="77cc5-103">Disabilita l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="77cc5-103">Disables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77cc5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77cc5-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="77cc5-105">Parti</span><span class="sxs-lookup"><span data-stu-id="77cc5-105">Parts</span></span>  
 <span data-ttu-id="77cc5-106">*object*</span><span class="sxs-lookup"><span data-stu-id="77cc5-106">*object*</span></span>  
 <span data-ttu-id="77cc5-107">Oggetto [ServerNetworkProtocolIPAdress Class] ServerNetworkProtocolIPAddress-class.md) che rappresenta un indirizzo IP per il protocollo di rete in un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77cc5-107">A [ServerNetworkProtocolIPAdress Class]servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="77cc5-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="77cc5-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="77cc5-109">Valore uint32 che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="77cc5-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77cc5-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="77cc5-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77cc5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77cc5-111">See Also</span></span>  
 <span data-ttu-id="77cc5-112">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="77cc5-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
