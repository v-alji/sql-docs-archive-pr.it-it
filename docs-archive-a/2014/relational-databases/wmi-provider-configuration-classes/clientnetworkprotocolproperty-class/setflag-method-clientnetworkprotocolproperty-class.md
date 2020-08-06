---
title: Metodo seflag (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 0407520f-2f84-4f68-b2b7-429697286c1b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1c83a1d647b62f0e5c5acf0659d54bf787bf0c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722655"
---
# <a name="setflag-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="8db0b-102">Metodo SetFlag (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="8db0b-102">SetFlag Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="8db0b-103">Imposta il flag della proprietà corrente a cui fa riferimento il valore della [proprietà PropertyIdx (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="8db0b-103">Sets the flag of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db0b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8db0b-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
) [=]  
```  
  
## <a name="parts"></a><span data-ttu-id="8db0b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8db0b-105">Parts</span></span>  
 <span data-ttu-id="8db0b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="8db0b-106">*object*</span></span>  
 <span data-ttu-id="8db0b-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) che rappresenta un attributo del protocollo di rete utilizzato dal client di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8db0b-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="8db0b-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="8db0b-108">Parameters</span></span>  
  
|<span data-ttu-id="8db0b-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="8db0b-109">Parameter</span></span>|<span data-ttu-id="8db0b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8db0b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8db0b-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="8db0b-111">*BoolValue*</span></span>|<span data-ttu-id="8db0b-112">Valore booleano che specifica il nuovo valore del flag.</span><span class="sxs-lookup"><span data-stu-id="8db0b-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8db0b-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8db0b-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="8db0b-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="8db0b-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8db0b-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8db0b-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db0b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8db0b-116">See Also</span></span>  
 [<span data-ttu-id="8db0b-117">Configurazione di protocolli client</span><span class="sxs-lookup"><span data-stu-id="8db0b-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
