---
title: Metodo ResumeService (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ResumeService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ResumeService method
ms.assetid: 0b0a5f08-b95e-4626-bf81-309da7a0aacd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 53d07c8697c6303bc371f442745e2d1864682e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627665"
---
# <a name="resumeservice-method-sqlservice-class"></a><span data-ttu-id="384cc-102">Metodo ResumeService (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="384cc-102">ResumeService Method (SqlService Class)</span></span>
  <span data-ttu-id="384cc-103">Esegue un tentativo di ripresa del servizio.</span><span class="sxs-lookup"><span data-stu-id="384cc-103">Attempts to place the service in the resumed state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="384cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="384cc-104">Syntax</span></span>  
  
```  
  
object  
.ResumeService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="384cc-105">Parti</span><span class="sxs-lookup"><span data-stu-id="384cc-105">Parts</span></span>  
 <span data-ttu-id="384cc-106">*object*</span><span class="sxs-lookup"><span data-stu-id="384cc-106">*object*</span></span>  
 <span data-ttu-id="384cc-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="384cc-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="384cc-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="384cc-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="384cc-109">Valore uint32 che è 0 se la richiesta `ResumeService` è stata accettata, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="384cc-109">A uint32 value, which is 0 if the `ResumeService` request was accepted, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="384cc-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="384cc-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384cc-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="384cc-111">See Also</span></span>  
 <span data-ttu-id="384cc-112">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="384cc-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
