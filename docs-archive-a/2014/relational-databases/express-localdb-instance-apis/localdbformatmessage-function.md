---
title: Funzione LocalDBFormatMessage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBFormatMessage
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 31b3152a-94cf-4f75-a31b-296d7dd16dbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ece28f19e3488fae248bf26c3a54a018ba6efd0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726943"
---
# <a name="localdbformatmessage-function"></a><span data-ttu-id="9c2ec-102">Funzione LocalDBFormatMessage</span><span class="sxs-lookup"><span data-stu-id="9c2ec-102">LocalDBFormatMessage Function</span></span>
  <span data-ttu-id="9c2ec-103">Viene restituita la descrizione testuale localizzata per l'errore del database locale di SQL Server Express specificato.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-103">Returns the localized textual description for the specified SQL Server Express LocalDB error.</span></span>  
  
 <span data-ttu-id="9c2ec-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="9c2ec-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c2ec-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c2ec-105">Syntax</span></span>  
  
```  
HRESULT LocalDBFormatMessage(  
           HRESULT hrLocalDB,  
           DWORD dwFlags,   
           DWORD dwLanguageId,   
           LPWSTR wszMessage,   
           LPDWORD lpcchMessage   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c2ec-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c2ec-106">Parameters</span></span>  
 <span data-ttu-id="9c2ec-107">*hrLocalDB*</span><span class="sxs-lookup"><span data-stu-id="9c2ec-107">*hrLocalDB*</span></span>  
 <span data-ttu-id="9c2ec-108">[Input] Codice di errore del database locale.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-108">[Input] The LocalDB error code.</span></span>  
  
 <span data-ttu-id="9c2ec-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="9c2ec-109">*dwFlags*</span></span>  
 <span data-ttu-id="9c2ec-110">[Input] Flag che specificano il comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-110">[Input] The flags specifying the behavior of this function.</span></span>  
  
 <span data-ttu-id="9c2ec-111">Flag disponibili:</span><span class="sxs-lookup"><span data-stu-id="9c2ec-111">Available flags:</span></span>  
  
 <span data-ttu-id="9c2ec-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="9c2ec-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span></span>  
 <span data-ttu-id="9c2ec-113">Se il buffer di input è troppo corto, il messaggio di errore sarà troncato in base al buffer.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-113">If the input buffer is too short, the error message will be truncated to fit the buffer.</span></span>  
  
 <span data-ttu-id="9c2ec-114">*dwLanguageId*</span><span class="sxs-lookup"><span data-stu-id="9c2ec-114">*dwLanguageId*</span></span>  
 <span data-ttu-id="9c2ec-115">[Input] Lingua desiderata (LANGID) o 0. In tal caso viene utilizzato l'ordine della lingua FormatMessage di Win32.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-115">[Input] The language desired (LANGID) or 0, in which case the Win32 FormatMessage language order is used.</span></span>  
  
 <span data-ttu-id="9c2ec-116">*wszMessage*</span><span class="sxs-lookup"><span data-stu-id="9c2ec-116">*wszMessage*</span></span>  
 <span data-ttu-id="9c2ec-117">[Output] Buffer per archiviare il messaggio di errore del database locale.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-117">[Output] The buffer to store the LocalDB error message.</span></span>  
  
 <span data-ttu-id="9c2ec-118">*lpcchMessage*</span><span class="sxs-lookup"><span data-stu-id="9c2ec-118">*lpcchMessage*</span></span>  
 <span data-ttu-id="9c2ec-119">[Input/output] In input contiene la dimensione del buffer *wszMessage* in caratteri.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-119">[Input/Output] On input contains the size of the *wszMessage* buffer in characters.</span></span> <span data-ttu-id="9c2ec-120">In fase di output, se le dimensioni del buffer specificate sono troppo piccole, nel parametro sono contenute le dimensioni del buffer richieste in caratteri, inclusi gli spazi vuoti finali.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-120">On output, if the given buffer size is too small, contains the buffer size required in characters, including any trailing nulls.</span></span> <span data-ttu-id="9c2ec-121">Se la funzione viene completata, in essa è contenuto il numero di caratteri nel messaggio, esclusi gli spazi vuoti finali.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-121">If the function succeeds, contains the number of characters in the message, excluding any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="9c2ec-122">Restituisce</span><span class="sxs-lookup"><span data-stu-id="9c2ec-122">Returns</span></span>  
 <span data-ttu-id="9c2ec-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c2ec-123">S_OK</span></span>  
 <span data-ttu-id="9c2ec-124">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-124">The function succeeded.</span></span>  
  
 [<span data-ttu-id="9c2ec-125">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="9c2ec-125">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="9c2ec-126">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-126">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="9c2ec-127">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="9c2ec-127">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="9c2ec-128">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-128">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="9c2ec-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span><span class="sxs-lookup"><span data-stu-id="9c2ec-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span></span>](../express-localdb-error-messages/localdb-error-unknown-error-code.md)  
 <span data-ttu-id="9c2ec-130">Messaggio richiesto inesistente.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-130">The requested message does not exist.</span></span>  
  
 [<span data-ttu-id="9c2ec-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="9c2ec-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>](../express-localdb-error-messages/localdb-error-unknown-language-id.md)  
 <span data-ttu-id="9c2ec-132">Messaggio non disponibile nella lingua richiesta.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-132">The message is not available in the requested language.</span></span>  
  
 [<span data-ttu-id="9c2ec-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9c2ec-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="9c2ec-134">Il buffer di input *wszMessage* è troppo breve e il troncamento non è richiesto.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-134">The input buffer *wszMessage* is too short, and truncation is not requested.</span></span>  
  
 [<span data-ttu-id="9c2ec-135">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="9c2ec-135">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="9c2ec-136">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-136">An unexpected error occurred.</span></span> <span data-ttu-id="9c2ec-137">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="9c2ec-137">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c2ec-138">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9c2ec-138">Remarks</span></span>  
 <span data-ttu-id="9c2ec-139">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9c2ec-139">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2ec-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c2ec-140">See Also</span></span>  
 [<span data-ttu-id="9c2ec-141">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="9c2ec-141">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
