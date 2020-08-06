---
title: Funzione LocalDBGetVersions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersions
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 033a9c6b-0d7f-4f8a-ab60-33cd6fee0d33
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 37d2a927346252f1b126f5e3a4ec78ea03cde0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724736"
---
# <a name="localdbgetversions-function"></a><span data-ttu-id="523c6-102">Funzione LocalDBGetVersions</span><span class="sxs-lookup"><span data-stu-id="523c6-102">LocalDBGetVersions Function</span></span>
  <span data-ttu-id="523c6-103">Vengono restituite tutte le versioni del database locale di SQL Server Express disponibili nel computer.</span><span class="sxs-lookup"><span data-stu-id="523c6-103">Returns all SQL Server Express LocalDB versions available on the computer.</span></span>  
  
 <span data-ttu-id="523c6-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="523c6-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="523c6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="523c6-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_VERSION_LENGTH 43typedef WCHAR TLocalDBVersion[MAX_LOCALDB_VERSION_LENGTH + 1];typedef TLocalDBVersion* PTLocalDBVersion;HRESULT LocalDBGetVersions(           PTLocalDBVersion pVersion,           LPDWORD lpdwNumberOfVersions);  
```  
  
## <a name="parameters"></a><span data-ttu-id="523c6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="523c6-106">Parameters</span></span>  
 <span data-ttu-id="523c6-107">*pVersionNames*</span><span class="sxs-lookup"><span data-stu-id="523c6-107">*pVersionNames*</span></span>  
 <span data-ttu-id="523c6-108">Output Contiene i nomi delle versioni del database locale disponibili nella workstation dell'utente.</span><span class="sxs-lookup"><span data-stu-id="523c6-108">[Output] Contains names of the LocalDB versions that are available on the user's workstation.</span></span>  
  
 <span data-ttu-id="523c6-109">*lpdwNumberOfVersions*</span><span class="sxs-lookup"><span data-stu-id="523c6-109">*lpdwNumberOfVersions*</span></span>  
 <span data-ttu-id="523c6-110">[Input/output] In input include il numero di slot per le versioni nel buffer di *pVersionNames* .</span><span class="sxs-lookup"><span data-stu-id="523c6-110">[Input/Output] On input holds the number of slots for versions in the *pVersionNames* buffer.</span></span>   
<span data-ttu-id="523c6-111">In fase di output, è contenuto il numero di versioni del database locale esistenti.</span><span class="sxs-lookup"><span data-stu-id="523c6-111">On output, holds the number of existing LocalDB versions.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="523c6-112">Restituisce</span><span class="sxs-lookup"><span data-stu-id="523c6-112">Returns</span></span>  
 <span data-ttu-id="523c6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="523c6-113">S_OK</span></span>  
 <span data-ttu-id="523c6-114">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="523c6-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="523c6-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="523c6-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="523c6-116">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="523c6-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="523c6-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="523c6-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="523c6-118">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="523c6-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="523c6-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="523c6-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="523c6-120">Buffer di input troppo corto. Troncamento non necessario.</span><span class="sxs-lookup"><span data-stu-id="523c6-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="523c6-121">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="523c6-121">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="523c6-122">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="523c6-122">An unexpected error occurred.</span></span> <span data-ttu-id="523c6-123">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="523c6-123">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="523c6-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="523c6-124">Remarks</span></span>  
 <span data-ttu-id="523c6-125">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="523c6-125">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="523c6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="523c6-126">See Also</span></span>  
 [<span data-ttu-id="523c6-127">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="523c6-127">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
