---
title: Metodo GetNextOrderValue (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetNextOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetNextOrderValue method
ms.assetid: d741dc5c-c225-43d9-a730-7ad664ac525f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bdc3eecd9e151d7da32a5fd65a90552c0743b3d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638315"
---
# <a name="getnextordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="2b344-102">Metodo GetNextOrderValue (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="2b344-102">GetNextOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="2b344-103">Seleziona il protocollo che si trova nella posizione successiva nell'elenco di protocolli.</span><span class="sxs-lookup"><span data-stu-id="2b344-103">Selects the protocol that is in the next position in the list of protocols.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b344-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b344-104">Syntax</span></span>  
  
```  
  
object  
.GetNextOrderValue()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="2b344-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2b344-105">Parts</span></span>  
 <span data-ttu-id="2b344-106">*object*</span><span class="sxs-lookup"><span data-stu-id="2b344-106">*object*</span></span>  
 <span data-ttu-id="2b344-107">Oggetto della [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) che rappresenta il protocollo di rete utilizzato dal [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span><span class="sxs-lookup"><span data-stu-id="2b344-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2b344-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2b344-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="2b344-109">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="2b344-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b344-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2b344-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b344-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b344-111">See Also</span></span>  
 <span data-ttu-id="2b344-112">[Configurare i protocolli client](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="2b344-112">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="2b344-113">Configurazione di protocolli di rete client e di librerie di rete</span><span class="sxs-lookup"><span data-stu-id="2b344-113">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
