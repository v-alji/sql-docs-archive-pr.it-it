---
title: Metodo SetStringValue (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: 88d67b22-0eea-48c9-ab73-e0b4907953df
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ba2350b798f1d7092a37a28ca35c17d6f4536a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724447"
---
# <a name="setstringvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="39665-102">Metodo SetStringValue (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="39665-102">SetStringValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="39665-103">Imposta il valore string della proprietà corrente a cui fa riferimento il valore della [proprietà PropertyIdx (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="39665-103">Sets the string value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39665-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39665-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="39665-105">Parti</span><span class="sxs-lookup"><span data-stu-id="39665-105">Parts</span></span>  
 <span data-ttu-id="39665-106">*object*</span><span class="sxs-lookup"><span data-stu-id="39665-106">*object*</span></span>  
 <span data-ttu-id="39665-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) che rappresenta un attributo del protocollo di rete utilizzato dal client di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39665-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="39665-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="39665-108">Parameters</span></span>  
  
|<span data-ttu-id="39665-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="39665-109">Parameter</span></span>|<span data-ttu-id="39665-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39665-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39665-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="39665-111">*StrValue*</span></span>|<span data-ttu-id="39665-112">Valore string che specifica il nuovo valore della proprietà corrente.</span><span class="sxs-lookup"><span data-stu-id="39665-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="39665-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="39665-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="39665-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="39665-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39665-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="39665-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39665-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39665-116">See Also</span></span>  
 [<span data-ttu-id="39665-117">Configurazione di protocolli client</span><span class="sxs-lookup"><span data-stu-id="39665-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
