---
title: Metodo SetStrValue (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 4ff80124-6e2e-4d96-a692-57c17b53c55e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f3c23eebdbe948e1b77c47ef56a04691fa391938
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724443"
---
# <a name="setstrvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="4e919-102">Metodo SetStrValue (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="4e919-102">SetStrValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="4e919-103">Imposta il valore string della proprietà corrente a cui fa riferimento il valore della [proprietà PropertyIdx (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="4e919-103">Sets the string value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e919-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e919-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="4e919-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4e919-105">Parts</span></span>  
 <span data-ttu-id="4e919-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4e919-106">*object*</span></span>  
 <span data-ttu-id="4e919-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) che rappresenta un attributo del protocollo di rete utilizzato dal client di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e919-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="4e919-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e919-108">Parameters</span></span>  
  
|<span data-ttu-id="4e919-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="4e919-109">Parameter</span></span>|<span data-ttu-id="4e919-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e919-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e919-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="4e919-111">*StrValue*</span></span>|<span data-ttu-id="4e919-112">Valore string che specifica il nuovo valore della proprietà corrente.</span><span class="sxs-lookup"><span data-stu-id="4e919-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4e919-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4e919-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="4e919-114">Valore uint32 che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="4e919-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e919-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4e919-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e919-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e919-116">See Also</span></span>  
 [<span data-ttu-id="4e919-117">Configurazione di protocolli client</span><span class="sxs-lookup"><span data-stu-id="4e919-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
