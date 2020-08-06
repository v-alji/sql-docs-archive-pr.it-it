---
title: Metodo seenable (classe ServerNetworkProtocolIPAddress) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: baa86deb-95dd-416f-b2c7-cec1dfb91ab4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5be9c30acacaedba320fd68363e531b178918271
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629735"
---
# <a name="setenable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="f605e-102">Metodo SetEnable (classe ServerNetworkProtocolIPAddress)</span><span class="sxs-lookup"><span data-stu-id="f605e-102">SetEnable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="f605e-103">Abilita l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="f605e-103">Enables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f605e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f605e-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f605e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f605e-105">Parts</span></span>  
 <span data-ttu-id="f605e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f605e-106">*object*</span></span>  
 <span data-ttu-id="f605e-107">A [classe ServerNetworkProtocolIPAdress](servernetworkprotocolipaddress-class.md) che rappresenta un indirizzo IP del protocollo di rete nell'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f605e-107">A [ServerNetworkProtocolIPAdress Class](servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f605e-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f605e-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f605e-109">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="f605e-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f605e-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f605e-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f605e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f605e-111">See Also</span></span>  
 <span data-ttu-id="f605e-112">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f605e-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
