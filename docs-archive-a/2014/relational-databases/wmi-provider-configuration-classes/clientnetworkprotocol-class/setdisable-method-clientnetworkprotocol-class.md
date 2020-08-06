---
title: Metodo sedisable (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: bce69ab9-ea5b-43fd-8114-08b1b5890755
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bad312f1f7c7e9540acdaf3dd46df78b953d4ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638310"
---
# <a name="setdisable-method-clientnetworkprotocol-class"></a><span data-ttu-id="0c59c-102">Metodo SetDisable (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="0c59c-102">SetDisable Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="0c59c-103">Disabilita il protocollo di rete client specificato dalla [configurazione dei protocolli client](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c59c-103">Disables the client network protocol that is specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c59c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c59c-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="0c59c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0c59c-105">Parts</span></span>  
 <span data-ttu-id="0c59c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="0c59c-106">*object*</span></span>  
 <span data-ttu-id="0c59c-107">Oggetto della [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) che rappresenta il protocollo di rete utilizzato dal [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span><span class="sxs-lookup"><span data-stu-id="0c59c-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0c59c-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c59c-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="0c59c-109">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="0c59c-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c59c-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0c59c-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c59c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c59c-111">See Also</span></span>  
 [<span data-ttu-id="0c59c-112">Configurazione di protocolli di rete client e di librerie di rete</span><span class="sxs-lookup"><span data-stu-id="0c59c-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
