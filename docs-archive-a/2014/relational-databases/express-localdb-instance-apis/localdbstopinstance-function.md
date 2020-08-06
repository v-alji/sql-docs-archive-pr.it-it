---
title: Funzione LocalDBStopInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 4bd73187-0aac-4f03-ac54-2b78e41917e5
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 48b014e65e0a02a5f866e5301b12dae3cd255b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711935"
---
# <a name="localdbstopinstance-function"></a><span data-ttu-id="20c71-102">Funzione LocalDBStopInstance</span><span class="sxs-lookup"><span data-stu-id="20c71-102">LocalDBStopInstance Function</span></span>
  <span data-ttu-id="20c71-103">Viene arrestata l'esecuzione dell'istanza del database locale di SQL Server Express specificata.</span><span class="sxs-lookup"><span data-stu-id="20c71-103">Stops the specified SQL Server Express LocalDB instance from running.</span></span>  
  
 <span data-ttu-id="20c71-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="20c71-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c71-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20c71-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           ULONG ulTimeout   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20c71-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="20c71-106">Parameters</span></span>  
 <span data-ttu-id="20c71-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="20c71-107">*pInstanceName*</span></span>  
 <span data-ttu-id="20c71-108">[Input] Nome dell'istanza del database locale da arrestare.</span><span class="sxs-lookup"><span data-stu-id="20c71-108">[Input] The name of the LocalDB instance to stop.</span></span>  
  
 <span data-ttu-id="20c71-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="20c71-109">*dwFlags*</span></span>  
 <span data-ttu-id="20c71-110">[Input] Uno o una combinazione di valori per i flag che specificano la modalità di arresto dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="20c71-110">[Input] One or a combination of the flag values specifying the way to stop the instance.</span></span>  
  
 <span data-ttu-id="20c71-111">Flag disponibili:</span><span class="sxs-lookup"><span data-stu-id="20c71-111">Available flags:</span></span>  
  
 <span data-ttu-id="20c71-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="20c71-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span></span>  
 <span data-ttu-id="20c71-113">Arrestare immediatamente l'utilizzo del comando del sistema operativo relativo al processo di terminazione.</span><span class="sxs-lookup"><span data-stu-id="20c71-113">Shut down immediately using the kill process operating system command.</span></span>  
  
 <span data-ttu-id="20c71-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span><span class="sxs-lookup"><span data-stu-id="20c71-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span></span>  
 <span data-ttu-id="20c71-115">Arrestare l'utilizzo del comando Transact-SQL dell'opzione NOWAIT.</span><span class="sxs-lookup"><span data-stu-id="20c71-115">Shut down using the WITH NOWAIT option Transact-SQL command.</span></span>  
  
 <span data-ttu-id="20c71-116">Se non è impostato nessuno dei flag, l'istanza del database verrà arrestata tramite il comando Transact-SQL SHUTDOWN.</span><span class="sxs-lookup"><span data-stu-id="20c71-116">If none of the flags is set, the LocalDB instance will be shut down using the SHUTDOWN Transact-SQL command.</span></span> <span data-ttu-id="20c71-117">Se sono impostati entrambi i flag, ha la precedenza il flag LOCALDB_SHUTDOWN_KILL_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="20c71-117">If both flags are set, the LOCALDB_SHUTDOWN_KILL_PROCESS flag takes precedence.</span></span>  
  
 <span data-ttu-id="20c71-118">*ulTimeout*</span><span class="sxs-lookup"><span data-stu-id="20c71-118">*ulTimeout*</span></span>  
 <span data-ttu-id="20c71-119">[Input] Ora in secondi di attesa per il completamento di questa operazione.</span><span class="sxs-lookup"><span data-stu-id="20c71-119">[Input] The time in seconds to wait for this operation to complete.</span></span> <span data-ttu-id="20c71-120">Se questo valore è 0, verrà restituito immediatamente un valore senza attendere l'arresto dell'istanza del database locale.</span><span class="sxs-lookup"><span data-stu-id="20c71-120">If this value is 0, this function will return immediately without waiting for the LocalDB instance to stop.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="20c71-121">Restituisce</span><span class="sxs-lookup"><span data-stu-id="20c71-121">Returns</span></span>  
 <span data-ttu-id="20c71-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="20c71-122">S_OK</span></span>  
 <span data-ttu-id="20c71-123">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="20c71-123">The function succeeded.</span></span>  
  
 [<span data-ttu-id="20c71-124">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="20c71-124">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="20c71-125">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="20c71-125">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="20c71-126">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="20c71-126">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="20c71-127">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="20c71-127">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="20c71-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="20c71-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="20c71-129">Nome dell'stanza specificata non valido.</span><span class="sxs-lookup"><span data-stu-id="20c71-129">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="20c71-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="20c71-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="20c71-131">Istanza inesistente.</span><span class="sxs-lookup"><span data-stu-id="20c71-131">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="20c71-132">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20c71-132">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="20c71-133">Timeout durante il tentativo di acquisizione dei blocchi di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="20c71-133">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="20c71-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span><span class="sxs-lookup"><span data-stu-id="20c71-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-instance-stop-failed.md)  
 <span data-ttu-id="20c71-135">Errore durante il completamento dell'operazione di arresto entro l'ora specificata.</span><span class="sxs-lookup"><span data-stu-id="20c71-135">The stop operation failed to complete within the given time.</span></span>  
  
 [<span data-ttu-id="20c71-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="20c71-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="20c71-137">Percorso di archiviazione richiesto per l'istanza più lungo di MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="20c71-137">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="20c71-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="20c71-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="20c71-139">Impossibile recuperare una cartella del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="20c71-139">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="20c71-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="20c71-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="20c71-141">Impossibile accedere alla cartella di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="20c71-141">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="20c71-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="20c71-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="20c71-143">Impossibile accedere al Registro di sistema di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="20c71-143">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="20c71-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="20c71-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="20c71-145">Configurazione di un'istanza danneggiata.</span><span class="sxs-lookup"><span data-stu-id="20c71-145">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="20c71-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20c71-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="20c71-147">Il chiamante API non è il proprietario dell'istanza del database locale.</span><span class="sxs-lookup"><span data-stu-id="20c71-147">API caller is not LocalDB instance owner.</span></span>  
  
 [<span data-ttu-id="20c71-148">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="20c71-148">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="20c71-149">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="20c71-149">An unexpected error occurred.</span></span> <span data-ttu-id="20c71-150">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="20c71-150">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20c71-151">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="20c71-151">Remarks</span></span>  
 <span data-ttu-id="20c71-152">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="20c71-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c71-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20c71-153">See Also</span></span>  
 [<span data-ttu-id="20c71-154">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="20c71-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
