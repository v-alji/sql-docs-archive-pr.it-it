---
title: Metodo PauseService (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PauseService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PauseService method
ms.assetid: 5c3a8feb-58b8-4385-b4c8-bf33cf4d276d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8286e123bbbc279ba461336c5716eeb208c5b238
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628548"
---
# <a name="pauseservice-method-sqlservice-class"></a><span data-ttu-id="3f6e2-102">Metodo PauseService (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="3f6e2-102">PauseService Method (SqlService Class)</span></span>
  <span data-ttu-id="3f6e2-103">Esegue un tentativo di sospensione del servizio.</span><span class="sxs-lookup"><span data-stu-id="3f6e2-103">Attempts to place the service in the paused state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f6e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f6e2-104">Syntax</span></span>  
  
```  
  
object  
.PauseService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="3f6e2-105">Parti</span><span class="sxs-lookup"><span data-stu-id="3f6e2-105">Parts</span></span>  
 <span data-ttu-id="3f6e2-106">*object*</span><span class="sxs-lookup"><span data-stu-id="3f6e2-106">*object*</span></span>  
 <span data-ttu-id="3f6e2-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="3f6e2-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3f6e2-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3f6e2-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="3f6e2-109">Valore uint32 che è 0 se il servizio è stato arrestato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="3f6e2-109">A uint32 value, which is 0 if the service was successfully stopped, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f6e2-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3f6e2-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6e2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f6e2-111">See Also</span></span>  
 <span data-ttu-id="3f6e2-112">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3f6e2-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
