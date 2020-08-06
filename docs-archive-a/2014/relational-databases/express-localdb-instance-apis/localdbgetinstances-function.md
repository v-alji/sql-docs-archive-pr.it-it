---
title: Funzione LocalDBGetInstances | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstances
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: f95a9980-8bc0-426c-8aa1-e2660b6784cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4a6f758bd647fd69a14f72a0651bb3e2e33a7c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711936"
---
# <a name="localdbgetinstances-function"></a><span data-ttu-id="0a8c1-102">Funzione LocalDBGetInstances</span><span class="sxs-lookup"><span data-stu-id="0a8c1-102">LocalDBGetInstances Function</span></span>
  <span data-ttu-id="0a8c1-103">Vengono restituite tutte le istanze del database locale di SQL Server Express con la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-103">Returns all SQL Server Express LocalDB instances with the given version.</span></span>  
  
 <span data-ttu-id="0a8c1-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="0a8c1-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8c1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a8c1-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_INSTANCE_NAME_LENGTH 128typedef WCHAR TLocalDBInstanceName[MAX_LOCALDB_INSTANCE_NAME_LENGTH + 1];typedef TLocalDBInstanceName* PTLocalDBInstanceName;  
HRESULT LocalDBGetInstances(  
           PTLocalDBInstanceName pInstanceNames,  
           LPDWORD lpdwNumberOfInstances  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a8c1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a8c1-106">Parameters</span></span>  
 <span data-ttu-id="0a8c1-107">*pInstanceNames*</span><span class="sxs-lookup"><span data-stu-id="0a8c1-107">*pInstanceNames*</span></span>  
 <span data-ttu-id="0a8c1-108">Output Quando questa funzione viene restituita, contiene i nomi delle istanze del database locale denominate e predefinite nella workstation dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-108">[Output] When this function returns, contains the names of both named and default LocalDB instances on the user's workstation.</span></span>  
  
 <span data-ttu-id="0a8c1-109">*lpdwNumberOfInstances*</span><span class="sxs-lookup"><span data-stu-id="0a8c1-109">*lpdwNumberOfInstances*</span></span>  
 <span data-ttu-id="0a8c1-110">[Input/output] In input, contiene il numero di slot per i nomi di istanza nel buffer *pInstanceNames* .</span><span class="sxs-lookup"><span data-stu-id="0a8c1-110">[Input/Output] On input, contains the number of slots for instance names in the *pInstanceNames* buffer.</span></span> <span data-ttu-id="0a8c1-111">Nell'output, contiene il numero di istanze del database locale trovate nella workstation dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-111">On output, contains the number of LocalDB instances found on the user's workstation.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0a8c1-112">Restituisce</span><span class="sxs-lookup"><span data-stu-id="0a8c1-112">Returns</span></span>  
 <span data-ttu-id="0a8c1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a8c1-113">S_OK</span></span>  
 <span data-ttu-id="0a8c1-114">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="0a8c1-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="0a8c1-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="0a8c1-116">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="0a8c1-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="0a8c1-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="0a8c1-118">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="0a8c1-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="0a8c1-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="0a8c1-120">Buffer di input troppo corto. Troncamento non necessario.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="0a8c1-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="0a8c1-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="0a8c1-122">Percorso di archiviazione richiesto per l'istanza più lungo di MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-122">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="0a8c1-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="0a8c1-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="0a8c1-124">Impossibile accedere al Registro di sistema di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-124">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="0a8c1-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="0a8c1-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="0a8c1-126">Configurazione di un'istanza danneggiata.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-126">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="0a8c1-127">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="0a8c1-127">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="0a8c1-128">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-128">An unexpected error occurred.</span></span> <span data-ttu-id="0a8c1-129">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="0a8c1-129">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a8c1-130">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0a8c1-130">Remarks</span></span>  
 <span data-ttu-id="0a8c1-131">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0a8c1-131">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8c1-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a8c1-132">See Also</span></span>  
 [<span data-ttu-id="0a8c1-133">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="0a8c1-133">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
