---
title: Metodo SetOrderValue (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetOrderValue method
ms.assetid: 15f693fd-37f6-41d9-9dab-d2c93db19895
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6839e85b6131c54e233d980c84a8727eeda2202a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637705"
---
# <a name="setordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="e502c-102">Metodo SetOrderValue (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="e502c-102">SetOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="e502c-103">Seleziona il protocollo con il valore dell'ordine specificato dall'elenco di protocolli del client.</span><span class="sxs-lookup"><span data-stu-id="e502c-103">Selects the protocol with the specified order value from the client protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e502c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e502c-104">Syntax</span></span>  
  
```  
  
object  
.SetOrderValue(  
OrderValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e502c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e502c-105">Parts</span></span>  
 <span data-ttu-id="e502c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e502c-106">*object*</span></span>  
 <span data-ttu-id="e502c-107">Oggetto della [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) che rappresenta il protocollo di rete utilizzato dal client di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e502c-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e502c-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="e502c-108">Parameters</span></span>  
  
|<span data-ttu-id="e502c-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="e502c-109">Parameter</span></span>|<span data-ttu-id="e502c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e502c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e502c-111">*OrderValue*</span><span class="sxs-lookup"><span data-stu-id="e502c-111">*OrderValue*</span></span>|<span data-ttu-id="e502c-112">Valore u`int32` che imposta il valore dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="e502c-112">A u`int32` value that sets the order value.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e502c-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e502c-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e502c-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="e502c-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e502c-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e502c-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e502c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e502c-116">See Also</span></span>  
 [<span data-ttu-id="e502c-117">Proprietà - Protocolli client (scheda Ordine)</span><span class="sxs-lookup"><span data-stu-id="e502c-117">Client Protocols Properties (Order Tab)</span></span>](https://technet.microsoft.com/library/ms187884.aspx)  
  
  
