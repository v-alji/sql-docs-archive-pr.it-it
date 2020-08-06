---
title: Funzione LocalDBStopTracing | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 1d50e040-8602-4ffa-be8f-b8633fdfa7ff
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bf6051fe8c86728c2ebf0a0b2bc34fabb98edb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624731"
---
# <a name="localdbstoptracing-function"></a><span data-ttu-id="cc717-102">Funzione LocalDBStopTracing</span><span class="sxs-lookup"><span data-stu-id="cc717-102">LocalDBStopTracing Function</span></span>
  <span data-ttu-id="cc717-103">Viene disabilitata la traccia delle chiamate API per tutte le istanze del database locale SQL Server Express di proprietà dell'utente di Windows corrente.</span><span class="sxs-lookup"><span data-stu-id="cc717-103">Disables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="cc717-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="cc717-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc717-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc717-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="cc717-106">Restituisce</span><span class="sxs-lookup"><span data-stu-id="cc717-106">Returns</span></span>  
 <span data-ttu-id="cc717-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc717-107">S_OK</span></span>  
 <span data-ttu-id="cc717-108">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="cc717-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="cc717-109">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="cc717-109">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="cc717-110">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="cc717-110">An unexpected error occurred.</span></span> <span data-ttu-id="cc717-111">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="cc717-111">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc717-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cc717-112">Remarks</span></span>  
 <span data-ttu-id="cc717-113">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="cc717-113">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc717-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc717-114">See Also</span></span>  
 [<span data-ttu-id="cc717-115">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="cc717-115">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
