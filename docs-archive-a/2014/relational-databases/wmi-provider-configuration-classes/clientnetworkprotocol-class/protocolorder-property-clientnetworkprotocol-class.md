---
title: Proprietà ProtocolOrder (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProtocolOrder Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProtocolOrder property
ms.assetid: aa09b8ab-37db-4406-8973-acf503855fd2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8bccb7109972dea4697e9e289081cbf47d2f9492
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637706"
---
# <a name="protocolorder-property-clientnetworkprotocol-class"></a><span data-ttu-id="68acf-102">Proprietà ProtocolOrder (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="68acf-102">ProtocolOrder Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="68acf-103">Ottiene il numero di ordine del protocollo di rete del client a cui si fa attualmente riferimento come specificato dal [metodo SetOrderValue (classe ClientNetworkProtocol)](clientnetworkprotocol-class.md) .</span><span class="sxs-lookup"><span data-stu-id="68acf-103">Gets the order number of the currently referenced client network protocol as specified by the [SetOrderValue Method (ClientNetworkProtocol Class)](clientnetworkprotocol-class.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68acf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68acf-104">Syntax</span></span>  
  
```  
  
object  
.ProtocolOrder [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="68acf-105">Parti</span><span class="sxs-lookup"><span data-stu-id="68acf-105">Parts</span></span>  
 <span data-ttu-id="68acf-106">*object*</span><span class="sxs-lookup"><span data-stu-id="68acf-106">*object*</span></span>  
 <span data-ttu-id="68acf-107">Oggetto della [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) che rappresenta il protocollo di rete utilizzato dal [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span><span class="sxs-lookup"><span data-stu-id="68acf-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="68acf-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="68acf-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="68acf-109">Valore `uint32` che specifica il numero di ordine del protocollo di rete del client a cui si fa attualmente riferimento come impostato dal metodo `OrderValue`.</span><span class="sxs-lookup"><span data-stu-id="68acf-109">A `uint32` value that specifies the order number of the currently referenced client network protocol as set by the `OrderValue` method.</span></span> <span data-ttu-id="68acf-110">Se il protocollo di rete client è disabilitato, questo valore sarà zero.</span><span class="sxs-lookup"><span data-stu-id="68acf-110">If the client network protocol is disabled, this value will be zero.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68acf-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="68acf-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68acf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68acf-112">See Also</span></span>  
 <span data-ttu-id="68acf-113">[Configurare i protocolli client](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="68acf-113">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="68acf-114">Configurazione di protocolli di rete client e di librerie di rete</span><span class="sxs-lookup"><span data-stu-id="68acf-114">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
