---
title: Metodo seflag (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 95288931-8eb1-4477-ad80-619cf7073e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1a90b4fca194f20cc0a2d70c947577594155f051
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713952"
---
# <a name="setflag-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="de62c-102">Metodo SetFlag (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="de62c-102">SetFlag Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="de62c-103">Imposta il flag della proprietà a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="de62c-103">Sets the flag of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de62c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de62c-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="de62c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="de62c-105">Parts</span></span>  
 <span data-ttu-id="de62c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="de62c-106">*object*</span></span>  
 <span data-ttu-id="de62c-107">Oggetto [ServerNetworkProtocolProperty Class] ServerNetworkProtocolProperty-class.md) che rappresenta un attributo del protocollo di rete nell'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de62c-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="de62c-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="de62c-108">Parameters</span></span>  
  
|<span data-ttu-id="de62c-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="de62c-109">Parameter</span></span>|<span data-ttu-id="de62c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de62c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de62c-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="de62c-111">*BoolValue*</span></span>|<span data-ttu-id="de62c-112">Valore booleano che specifica il nuovo valore del flag.</span><span class="sxs-lookup"><span data-stu-id="de62c-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="de62c-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="de62c-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="de62c-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="de62c-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de62c-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="de62c-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de62c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de62c-116">See Also</span></span>  
 <span data-ttu-id="de62c-117">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="de62c-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
