---
title: Proprietà Properties (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Properties Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Properties property
ms.assetid: 7e0a4e38-4555-4750-8fd3-4425b29e6aa1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 09836db1f510ac77635924c51e5341686627d54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638313"
---
# <a name="properties-property-clientnetworkprotocol-class"></a><span data-ttu-id="79b57-102">Proprietà Properties (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="79b57-102">Properties Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="79b57-103">Ottiene le proprietà associate al protocollo di rete client corrente specificato dalla [configurazione di protocolli client](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="79b57-103">Gets the properties associated with the current client network protocol specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b57-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79b57-104">Syntax</span></span>  
  
```  
  
object  
.Properties [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="79b57-105">Parti</span><span class="sxs-lookup"><span data-stu-id="79b57-105">Parts</span></span>  
 <span data-ttu-id="79b57-106">*object*</span><span class="sxs-lookup"><span data-stu-id="79b57-106">*object*</span></span>  
 <span data-ttu-id="79b57-107">Oggetto della [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) che rappresenta il protocollo di rete utilizzato dal client di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79b57-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="79b57-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="79b57-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="79b57-109">Matrice di oggetti della [classe ClientNetworkProtocolProperty](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) che rappresentano le proprietà supportate dal protocollo di rete del client corrente a cui fa riferimento la `OrderValue` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="79b57-109">An array of [ClientNetworkProtocolProperty Class](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) objects that represent the properties supported by the current client network protocol that is referenced by the `OrderValue` property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79b57-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="79b57-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b57-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79b57-111">See Also</span></span>  
 [<span data-ttu-id="79b57-112">Configurazione di protocolli di rete client e di librerie di rete</span><span class="sxs-lookup"><span data-stu-id="79b57-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
