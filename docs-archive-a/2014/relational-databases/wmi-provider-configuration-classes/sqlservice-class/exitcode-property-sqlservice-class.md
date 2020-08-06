---
title: Proprietà ExitCode (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ExitCode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ExitCode property
ms.assetid: e6b8bff2-946f-4abe-bd50-1f7bb11fdddf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f7f5414afd8507a1fc9c592d6b8226692e9683a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626585"
---
# <a name="exitcode-property-sqlservice-class"></a><span data-ttu-id="ccf99-102">Proprietà ExitCode (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="ccf99-102">ExitCode Property (SqlService Class)</span></span>
  <span data-ttu-id="ccf99-103">Ottiene o imposta il codice di errore [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win 32 che definisce i problemi verificatisi durante l'avvio e l'arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="ccf99-103">Gets or sets the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 error code that defines problems encountered when starting and stopping the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccf99-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccf99-104">Syntax</span></span>  
  
```  
  
object  
.ExitCode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="ccf99-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ccf99-105">Parts</span></span>  
 <span data-ttu-id="ccf99-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ccf99-106">*object*</span></span>  
 <span data-ttu-id="ccf99-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="ccf99-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ccf99-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ccf99-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="ccf99-109">Valore `uint32` che specifica il codice di uscita.</span><span class="sxs-lookup"><span data-stu-id="ccf99-109">A `uint32` value that specifies the exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccf99-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ccf99-110">Remarks</span></span>  
 <span data-ttu-id="ccf99-111">Questa proprietà è impostata su ERROR_SERVICE_SPECIFIC_ERROR (1066) quando l'errore è univoco al servizio rappresentato da questa classe.</span><span class="sxs-lookup"><span data-stu-id="ccf99-111">This property is set to ERROR_SERVICE_SPECIFIC_ERROR (1066) when the error is unique to the service represented by this class.</span></span> <span data-ttu-id="ccf99-112">Tramite il servizio questo valore viene impostato su NO_ERROR in fase di esecuzione e di nuovo al termine.</span><span class="sxs-lookup"><span data-stu-id="ccf99-112">The service sets this value to NO_ERROR when running, and again upon normal termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf99-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccf99-113">See Also</span></span>  
 <span data-ttu-id="ccf99-114">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ccf99-114">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
