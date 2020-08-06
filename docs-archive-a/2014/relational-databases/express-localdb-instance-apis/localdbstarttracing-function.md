---
title: Funzione LocalDBStartTracing | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: c7b83833-6d2a-4a06-9cb7-42767bed52c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1b10482e9839d43e29da72dbe2c194a01d8248eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726947"
---
# <a name="localdbstarttracing-function"></a><span data-ttu-id="5c742-102">Funzione LocalDBStartTracing</span><span class="sxs-lookup"><span data-stu-id="5c742-102">LocalDBStartTracing Function</span></span>
  <span data-ttu-id="5c742-103">Viene abilitata la traccia delle chiamate API per tutte le istanze del database locale di SQL Server Express di proprietà dell'utente di Windows corrente.</span><span class="sxs-lookup"><span data-stu-id="5c742-103">Enables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="5c742-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="5c742-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c742-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c742-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="5c742-106">Restituisce</span><span class="sxs-lookup"><span data-stu-id="5c742-106">Returns</span></span>  
 <span data-ttu-id="5c742-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c742-107">S_OK</span></span>  
 <span data-ttu-id="5c742-108">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="5c742-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="5c742-109">LOCALDB_ERROR_XEVENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="5c742-109">LOCALDB_ERROR_XEVENT_FAILED</span></span>](../express-localdb-error-messages/localdb-error-xevent-failed.md)  
 <span data-ttu-id="5c742-110">Impossibile avviare il motore XEvent all'interno dell'API dell'istanza del database locale.</span><span class="sxs-lookup"><span data-stu-id="5c742-110">Failed to start XEvent engine within the LocalDB Instance API.</span></span>  
  
 [<span data-ttu-id="5c742-111">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="5c742-111">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="5c742-112">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="5c742-112">An unexpected error occurred.</span></span> <span data-ttu-id="5c742-113">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="5c742-113">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c742-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5c742-114">Remarks</span></span>  
 <span data-ttu-id="5c742-115">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5c742-115">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c742-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c742-116">See Also</span></span>  
 [<span data-ttu-id="5c742-117">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="5c742-117">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
