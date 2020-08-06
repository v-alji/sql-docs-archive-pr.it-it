---
title: Classe ProcessId (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProcessId Class (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProcessId property
ms.assetid: 99b5a2e9-b44a-48a0-993e-04bd15c7fef4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7c4c40eea826b5009e52d26b1d930eaf5febbcdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628547"
---
# <a name="processid-class-sqlservice-class"></a><span data-ttu-id="6ce5d-102">Classe ProcessId (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="6ce5d-102">ProcessId Class (SqlService Class)</span></span>
  <span data-ttu-id="6ce5d-103">Ottiene l'ID di processo di sistema che identifica in modo univoco un servizio.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-103">Gets the system process ID that uniquely identifies a service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ce5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ce5d-104">Syntax</span></span>  
  
```  
  
object  
.ProcessId [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="6ce5d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6ce5d-105">Parts</span></span>  
 <span data-ttu-id="6ce5d-106">*object*</span><span class="sxs-lookup"><span data-stu-id="6ce5d-106">*object*</span></span>  
 <span data-ttu-id="6ce5d-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6ce5d-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6ce5d-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="6ce5d-109">Valore `uint32` che specifica l'ID che identifica in modo univoco il processo.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-109">A `uint32` value that specifies the ID that uniquely identifies the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ce5d-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6ce5d-110">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ce5d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ce5d-111">Example</span></span>  
  
```  
mysqlservice.ProcessId = 324  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ce5d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ce5d-112">See Also</span></span>  
 <span data-ttu-id="6ce5d-113">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="6ce5d-113">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
