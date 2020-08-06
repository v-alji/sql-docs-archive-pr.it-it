---
title: Metodo SetProtocolsOrder (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetProtocolsOrder Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetProtocolsOrder method
ms.assetid: b86d98b9-aae4-4e74-b4da-1ec984d5c8b4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: aaa1d43c8a2f7f210f61761b28313a93ac6c7a90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637701"
---
# <a name="setprotocolsorder-method-clientnetworkprotocol-class"></a><span data-ttu-id="b406d-102">Metodo SetProtocolsOrder (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="b406d-102">SetProtocolsOrder Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="b406d-103">Modifica l'ordine dell'elenco di protocolli.</span><span class="sxs-lookup"><span data-stu-id="b406d-103">Changes the order of the protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b406d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b406d-104">Syntax</span></span>  
  
```  
  
object  
.SetProtocolsOrder(  
ProtocolOrderList  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="b406d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b406d-105">Parts</span></span>  
 <span data-ttu-id="b406d-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b406d-106">*object*</span></span>  
 <span data-ttu-id="b406d-107">Oggetto della [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) che rappresenta il protocollo di rete utilizzato dal [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span><span class="sxs-lookup"><span data-stu-id="b406d-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="b406d-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="b406d-108">Parameters</span></span>  
  
|<span data-ttu-id="b406d-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="b406d-109">Parameter</span></span>|<span data-ttu-id="b406d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b406d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b406d-111">*ProtocolOrderList*</span><span class="sxs-lookup"><span data-stu-id="b406d-111">*ProtocolOrderList*</span></span>|<span data-ttu-id="b406d-112">Matrice string[] che elenca i protocolli di rete del client nel nuovo ordine.</span><span class="sxs-lookup"><span data-stu-id="b406d-112">A string[] array that lists the client network protocols in the new order.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b406d-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b406d-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="b406d-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="b406d-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b406d-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b406d-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b406d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b406d-116">See Also</span></span>  
 <span data-ttu-id="b406d-117">[Configurare i protocolli client](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="b406d-117">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="b406d-118">Configurazione di protocolli di rete client e di librerie di rete</span><span class="sxs-lookup"><span data-stu-id="b406d-118">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
