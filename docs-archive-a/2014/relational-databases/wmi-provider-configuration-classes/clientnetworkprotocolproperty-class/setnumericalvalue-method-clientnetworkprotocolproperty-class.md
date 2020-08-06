---
title: Metodo SetNumericalValue (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: d4d6df52-9e68-4003-9e28-ece6716ba7f1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ba963bb14e46aaa3f098ae74cd7aca92019256e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627663"
---
# <a name="setnumericalvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="ae4a8-102">Metodo SetNumericalValue (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="ae4a8-102">SetNumericalValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="ae4a8-103">Imposta il valore numerico della proprietà corrente a cui fa riferimento il valore della [proprietà PropertyIdx (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="ae4a8-103">Sets the numeric value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae4a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae4a8-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="ae4a8-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ae4a8-105">Parts</span></span>  
 <span data-ttu-id="ae4a8-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ae4a8-106">*object*</span></span>  
 <span data-ttu-id="ae4a8-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) che rappresenta un attributo del protocollo di rete utilizzato dal client di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae4a8-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ae4a8-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae4a8-108">Parameters</span></span>  
  
|<span data-ttu-id="ae4a8-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="ae4a8-109">Parameter</span></span>|<span data-ttu-id="ae4a8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae4a8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae4a8-111">*value*</span><span class="sxs-lookup"><span data-stu-id="ae4a8-111">*value*</span></span>|<span data-ttu-id="ae4a8-112">Valore `uint32` che specifica il valore numerico della proprietà a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="ae4a8-112">A `uint32` value that specifies the numeric value of the referenced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ae4a8-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ae4a8-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="ae4a8-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="ae4a8-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae4a8-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ae4a8-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4a8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae4a8-116">See Also</span></span>  
 [<span data-ttu-id="ae4a8-117">Configurazione di protocolli client</span><span class="sxs-lookup"><span data-stu-id="ae4a8-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
