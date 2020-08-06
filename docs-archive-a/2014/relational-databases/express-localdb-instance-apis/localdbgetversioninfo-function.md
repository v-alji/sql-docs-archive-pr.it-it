---
title: Funzione LocalDBGetVersionInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersionInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: d4aaea30-1d0d-4436-bcdc-5c101d27b1c1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e30bb4dcd4c258db899883f650dbfe7100171ef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725828"
---
# <a name="localdbgetversioninfo-function"></a><span data-ttu-id="866f6-102">Funzione LocalDBGetVersionInfo</span><span class="sxs-lookup"><span data-stu-id="866f6-102">LocalDBGetVersionInfo Function</span></span>
  <span data-ttu-id="866f6-103">Vengono restituite le informazioni per la versione del database locale di SQL Server Express specificata, se esistente, e il numero completo della versione del database locale, ovvero con i numeri di compilazione e della versione inclusi.</span><span class="sxs-lookup"><span data-stu-id="866f6-103">Returns information for the specified SQL Server Express LocalDB version, such as whether it exists and the full LocalDB version number (including build and release numbers).</span></span>  
  
 <span data-ttu-id="866f6-104">Le informazioni vengono restituite sotto forma di un oggetto `struct` denominato **LocalDBVersionInfostruct**, che presenta la definizione seguente.</span><span class="sxs-lookup"><span data-stu-id="866f6-104">The information is returned in the form of a `struct` named **LocalDBVersionInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBVersionInfo  
{  
      // Contains the size of the LocalDBVersionInfo struct  
      DWORD  cbLocalDBVersionInfoSize;  
  
      // Holds the version name  
      TLocalDBVersionwszVersion;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
} LocalDBVersionInfo;  
  
```  
  
 <span data-ttu-id="866f6-105">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="866f6-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="866f6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="866f6-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetVersionInfo(  
           PCWSTR wszVersionName,           PLocalDBVersionInfo pVersionInfo,           DWORD dwVersionInfoSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="866f6-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="866f6-107">Parameters</span></span>  
 <span data-ttu-id="866f6-108">*wszVersionName*</span><span class="sxs-lookup"><span data-stu-id="866f6-108">*wszVersionName*</span></span>  
 <span data-ttu-id="866f6-109">[Input] Nome della versione del database locale.</span><span class="sxs-lookup"><span data-stu-id="866f6-109">[Input] The LocalDB version name.</span></span>  
  
 <span data-ttu-id="866f6-110">*pVersionInfo*</span><span class="sxs-lookup"><span data-stu-id="866f6-110">*pVersionInfo*</span></span>  
 <span data-ttu-id="866f6-111">[Output] Buffer per archiviare le informazioni sulla versione del database locale.</span><span class="sxs-lookup"><span data-stu-id="866f6-111">[Output] The buffer to store the information about the LocalDB version.</span></span>  
  
 <span data-ttu-id="866f6-112">*dwVersionInfoSize*</span><span class="sxs-lookup"><span data-stu-id="866f6-112">*dwVersionInfoSize*</span></span>  
 <span data-ttu-id="866f6-113">Input Include le dimensioni del buffer *VERSIONINFO* .</span><span class="sxs-lookup"><span data-stu-id="866f6-113">[Input] Holds the size of the *VersionInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="866f6-114">Restituisce</span><span class="sxs-lookup"><span data-stu-id="866f6-114">Returns</span></span>  
 <span data-ttu-id="866f6-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="866f6-115">S_OK</span></span>  
 <span data-ttu-id="866f6-116">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="866f6-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="866f6-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="866f6-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="866f6-118">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="866f6-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="866f6-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="866f6-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="866f6-120">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="866f6-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="866f6-121">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="866f6-121">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="866f6-122">La versione del database locale specificata non esiste.</span><span class="sxs-lookup"><span data-stu-id="866f6-122">The specified LocalDB version does not exist.</span></span>  
  
 [<span data-ttu-id="866f6-123">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="866f6-123">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="866f6-124">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="866f6-124">An unexpected error occurred.</span></span> <span data-ttu-id="866f6-125">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="866f6-125">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="866f6-126">Dettagli</span><span class="sxs-lookup"><span data-stu-id="866f6-126">Details</span></span>  
 <span data-ttu-id="866f6-127">La logica alla base dell'introduzione dell' `struct` argomento size (*lpVersionInfoSize*) consiste nell'abilitare l'API per la restituzione di versioni diverse di **LocalDBVersionInfostruct**, abilitando in modo efficace la compatibilità con le versioni precedenti e precedenti.</span><span class="sxs-lookup"><span data-stu-id="866f6-127">The rationale behind the introduction of the `struct` size argument (*lpVersionInfoSize*) is to enable the API to return different versions of the **LocalDBVersionInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="866f6-128">Se l' `struct` argomento size (*lpVersionInfoSize*) corrisponde alle dimensioni di una versione nota di **LocalDBVersionInfostruct**, `struct` viene restituita tale versione di.</span><span class="sxs-lookup"><span data-stu-id="866f6-128">If the `struct` size argument (*lpVersionInfoSize*) matches the size of a known version of the **LocalDBVersionInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="866f6-129">In caso contrario, viene restituito LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="866f6-129">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="866f6-130">Un esempio tipico di utilizzo dell'API **LocalDBGetVersionInfo** è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="866f6-130">A typical example of **LocalDBGetVersionInfo** API usage looks like this:</span></span>  
  
```  
LocalDBVersionInfo vi;  
LocalDBVersionInfo(L"11.0", &vi, sizeof(LocalDBVersionInfo));  
  
```  
  
## <a name="remarks"></a><span data-ttu-id="866f6-131">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="866f6-131">Remarks</span></span>  
 <span data-ttu-id="866f6-132">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="866f6-132">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="866f6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="866f6-133">See Also</span></span>  
 [<span data-ttu-id="866f6-134">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="866f6-134">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
