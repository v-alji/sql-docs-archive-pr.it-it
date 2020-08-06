---
title: Metodo SetNumValue (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumValue method
ms.assetid: c292e2ae-6d0a-44ad-ba54-5b0bd705ef37
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 82a5474c2330d0d5bc0ed8766614773ceb899bf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628566"
---
# <a name="setnumvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="a6369-102">Metodo SetNumValue (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="a6369-102">SetNumValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="a6369-103">Imposta il valore numerico della proprietà corrente a cui fa riferimento il valore della [proprietà PropertyIdx (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="a6369-103">Sets the numeric value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6369-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6369-104">Syntax</span></span>  
  
```  
  
object  
.SetNumValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="a6369-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a6369-105">Parts</span></span>  
 <span data-ttu-id="a6369-106">*object*</span><span class="sxs-lookup"><span data-stu-id="a6369-106">*object*</span></span>  
 <span data-ttu-id="a6369-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) che rappresenta un attributo del protocollo di rete utilizzato dal client di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6369-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a6369-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6369-108">Parameters</span></span>  
  
|<span data-ttu-id="a6369-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="a6369-109">Parameter</span></span>|<span data-ttu-id="a6369-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6369-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6369-111">*value*</span><span class="sxs-lookup"><span data-stu-id="a6369-111">*value*</span></span>|<span data-ttu-id="a6369-112">Valore `uint32` che specifica il valore numerico della proprietà a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a6369-112">A `uint32` value that specifies the numeric value of the referenced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a6369-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a6369-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="a6369-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="a6369-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6369-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a6369-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6369-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6369-116">See Also</span></span>  
 [<span data-ttu-id="a6369-117">Configurazione di protocolli client</span><span class="sxs-lookup"><span data-stu-id="a6369-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
