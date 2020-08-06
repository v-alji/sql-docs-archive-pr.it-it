---
title: Metodo seenable (classe ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a287950b-086f-4b6d-a2d8-4d3973bd1b21
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8f77b7a92fe226e349a03ffba03cfe8d67c280e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626599"
---
# <a name="setenable-method-servernetworkprotocol-class"></a><span data-ttu-id="aeb12-102">Metodo SetEnable (classe ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="aeb12-102">SetEnable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="aeb12-103">Abilita il protocollo di rete del server.</span><span class="sxs-lookup"><span data-stu-id="aeb12-103">Enables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeb12-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aeb12-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="aeb12-105">Parti</span><span class="sxs-lookup"><span data-stu-id="aeb12-105">Parts</span></span>  
 <span data-ttu-id="aeb12-106">*object*</span><span class="sxs-lookup"><span data-stu-id="aeb12-106">*object*</span></span>  
 <span data-ttu-id="aeb12-107">Oggetto della [classe ServerNetworkProtocol](servernetworkprotocol-class.md) che rappresenta il protocollo di rete utilizzato dall'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aeb12-107">A [ServerNetworkProtocol Class](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="aeb12-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aeb12-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="aeb12-109">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="aeb12-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aeb12-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="aeb12-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeb12-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aeb12-111">See Also</span></span>  
 <span data-ttu-id="aeb12-112">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="aeb12-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
