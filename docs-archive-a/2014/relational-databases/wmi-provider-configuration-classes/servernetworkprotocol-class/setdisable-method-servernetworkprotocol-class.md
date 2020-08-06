---
title: Metodo sedisable (classe ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 0ebbe0c5-07ad-4a76-a918-e379930adf71
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3176227aba4de1e5aca1be35ec1f071a15caa49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626601"
---
# <a name="setdisable-method-servernetworkprotocol-class"></a><span data-ttu-id="cc0a1-102">Metodo SetDisable (classe ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="cc0a1-102">SetDisable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="cc0a1-103">Disabilita il protocollo di rete del server.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-103">Disables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc0a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc0a1-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="cc0a1-105">Parti</span><span class="sxs-lookup"><span data-stu-id="cc0a1-105">Parts</span></span>  
 <span data-ttu-id="cc0a1-106">*object*</span><span class="sxs-lookup"><span data-stu-id="cc0a1-106">*object*</span></span>  
 <span data-ttu-id="cc0a1-107">Oggetto [ServerNetworkProtocol Class] ServerNetworkProtocol-class.md) che rappresenta il protocollo di rete utilizzato dall'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc0a1-107">A [ServerNetworkProtocol Class]servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="cc0a1-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cc0a1-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="cc0a1-109">Valore uint32 che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc0a1-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cc0a1-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0a1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc0a1-111">See Also</span></span>  
 <span data-ttu-id="cc0a1-112">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="cc0a1-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
