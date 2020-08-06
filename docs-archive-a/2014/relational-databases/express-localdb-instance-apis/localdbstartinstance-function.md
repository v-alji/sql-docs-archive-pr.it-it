---
title: Funzione LocalDBStartInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: cb325f5d-10ee-4a56-ba28-db0074ab3926
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 748bc373e8b0dbad0a91247e068d21b67f2dbc1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637335"
---
# <a name="localdbstartinstance-function"></a><span data-ttu-id="a8504-102">Funzione LocalDBStartInstance</span><span class="sxs-lookup"><span data-stu-id="a8504-102">LocalDBStartInstance Function</span></span>
  <span data-ttu-id="a8504-103">Avvia l'istanza specificata del database locale di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="a8504-103">Starts the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="a8504-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="a8504-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8504-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8504-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           LPWSTR wszSqlConnection,   
           LPDWORD lpcchSqlConnection   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8504-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8504-106">Parameters</span></span>  
 <span data-ttu-id="a8504-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="a8504-107">*pInstanceName*</span></span>  
 <span data-ttu-id="a8504-108">[Input] Nome dell'istanza del database locale da avviare.</span><span class="sxs-lookup"><span data-stu-id="a8504-108">[Input] The name of the LocalDB instance to start.</span></span>  
  
 <span data-ttu-id="a8504-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="a8504-109">*dwFlags*</span></span>  
 <span data-ttu-id="a8504-110">[Input] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="a8504-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="a8504-111">Deve essere impostato attualmente su 0.</span><span class="sxs-lookup"><span data-stu-id="a8504-111">Currently should be set to 0.</span></span>  
  
 <span data-ttu-id="a8504-112">*wszSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="a8504-112">*wszSqlConnection*</span></span>  
 <span data-ttu-id="a8504-113">[Output] Buffer per archiviare la stringa di connessione nell'istanza del database locale.</span><span class="sxs-lookup"><span data-stu-id="a8504-113">[Output] The buffer to store the connection string to the LocalDB instance.</span></span>  
  
 <span data-ttu-id="a8504-114">*lpcchSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="a8504-114">*lpcchSqlConnection*</span></span>  
 <span data-ttu-id="a8504-115">[Input/output] In input contiene la dimensione del buffer *wszSqlConnection* in caratteri, inclusi eventuali valori Null finali.</span><span class="sxs-lookup"><span data-stu-id="a8504-115">[Input/Output] On input contains the size of the *wszSqlConnection* buffer in characters, including any trailing nulls.</span></span> <span data-ttu-id="a8504-116">In fase di output, se le dimensioni del buffer specificate sono troppo piccole, nel parametro sono contenute le dimensioni del buffer richieste in caratteri, inclusi gli spazi vuoti finali.</span><span class="sxs-lookup"><span data-stu-id="a8504-116">On output, if the given buffer size is too small, contains the required buffer size in characters, including any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a8504-117">Restituisce</span><span class="sxs-lookup"><span data-stu-id="a8504-117">Returns</span></span>  
 <span data-ttu-id="a8504-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8504-118">S_OK</span></span>  
 <span data-ttu-id="a8504-119">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="a8504-119">The function succeeded.</span></span>  
  
 [<span data-ttu-id="a8504-120">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="a8504-120">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="a8504-121">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="a8504-121">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="a8504-122">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="a8504-122">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="a8504-123">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="a8504-123">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="a8504-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="a8504-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="a8504-125">Nome dell'stanza specificata non valido.</span><span class="sxs-lookup"><span data-stu-id="a8504-125">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="a8504-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="a8504-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="a8504-127">Istanza inesistente.</span><span class="sxs-lookup"><span data-stu-id="a8504-127">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="a8504-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a8504-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="a8504-129">Il *wszSqlConnection* del buffer specificato è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="a8504-129">The specified buffer *wszSqlConnection* is too small.</span></span>  
  
 [<span data-ttu-id="a8504-130">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a8504-130">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="a8504-131">Timeout durante il tentativo di acquisizione dei blocchi di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8504-131">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="a8504-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="a8504-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="a8504-133">Percorso di archiviazione richiesto per l'istanza più lungo di MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="a8504-133">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="a8504-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="a8504-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="a8504-135">Impossibile recuperare una cartella del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="a8504-135">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="a8504-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="a8504-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="a8504-137">Impossibile accedere alla cartella di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="a8504-137">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="a8504-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="a8504-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="a8504-139">Impossibile accedere al Registro di sistema di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="a8504-139">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="a8504-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="a8504-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="a8504-141">Impossibile modificare il Registro di sistema di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="a8504-141">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="a8504-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="a8504-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-sql-process.md)  
 <span data-ttu-id="a8504-143">Impossibile creare un processo per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8504-143">A process for SQL Server cannot be created.</span></span>  
  
 [<span data-ttu-id="a8504-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="a8504-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="a8504-145">Avviato processo di SQL Server ma tale operazione non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="a8504-145">A SQL Server process was started, but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="a8504-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="a8504-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="a8504-147">Configurazione di un'istanza danneggiata.</span><span class="sxs-lookup"><span data-stu-id="a8504-147">An instance configuration was corrupted.</span></span>  
  
 [<span data-ttu-id="a8504-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="a8504-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span></span>](../express-localdb-error-messages/localdb-error-auto-instance-create-failed.md)  
 <span data-ttu-id="a8504-149">Impossibile creare un'istanza automatica.</span><span class="sxs-lookup"><span data-stu-id="a8504-149">Cannot create an automatic instance.</span></span> <span data-ttu-id="a8504-150">Per informazioni sugli errori, vedere il registro eventi applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="a8504-150">See the Windows Application event log for error details.</span></span>  
  
 [<span data-ttu-id="a8504-151">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="a8504-151">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="a8504-152">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="a8504-152">An unexpected error occurred.</span></span> <span data-ttu-id="a8504-153">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="a8504-153">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a8504-154">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a8504-154">Details</span></span>  
 <span data-ttu-id="a8504-155">Sia l'argomento del buffer di connessione (*wszSqlConnection*) che l'argomento relativo alla dimensione del buffer di connessione (*lpcchSqlConnection*) sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a8504-155">Both the connection buffer argument (*wszSqlConnection*) and the connection buffer size argument (*lpcchSqlConnection*) are optional.</span></span> <span data-ttu-id="a8504-156">Nella tabella seguente vengono mostrate le opzioni per l'utilizzo di questi argomenti e dei relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="a8504-156">The following table shows options for using these arguments and their results.</span></span>  
  
|<span data-ttu-id="a8504-157">Buffer</span><span class="sxs-lookup"><span data-stu-id="a8504-157">Buffer</span></span>|<span data-ttu-id="a8504-158">Dimensioni del buffer</span><span class="sxs-lookup"><span data-stu-id="a8504-158">Buffer size</span></span>|<span data-ttu-id="a8504-159">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a8504-159">Rationale</span></span>|<span data-ttu-id="a8504-160">Action</span><span class="sxs-lookup"><span data-stu-id="a8504-160">Action</span></span>|  
|------------|-----------------|---------------|------------|  
|<span data-ttu-id="a8504-161">NULL</span><span class="sxs-lookup"><span data-stu-id="a8504-161">NULL</span></span>|<span data-ttu-id="a8504-162">NULL</span><span class="sxs-lookup"><span data-stu-id="a8504-162">NULL</span></span>|<span data-ttu-id="a8504-163">L'utente desidera avviare l'istanza e non necessita di un nome di pipe.</span><span class="sxs-lookup"><span data-stu-id="a8504-163">User wants to start the instance and doesn't need a pipe name.</span></span>|<span data-ttu-id="a8504-164">Viene avviata un'istanza. Non viene restituita alcuna pipe né le dimensioni del buffer richieste.</span><span class="sxs-lookup"><span data-stu-id="a8504-164">Starts an instance (no pipe return and no required buffer size return).</span></span>|  
|<span data-ttu-id="a8504-165">NULL</span><span class="sxs-lookup"><span data-stu-id="a8504-165">NULL</span></span>|<span data-ttu-id="a8504-166">Presente</span><span class="sxs-lookup"><span data-stu-id="a8504-166">Present</span></span>|<span data-ttu-id="a8504-167">L'utente richiede le dimensioni del buffer di output.</span><span class="sxs-lookup"><span data-stu-id="a8504-167">User asks for the output buffer size.</span></span> <span data-ttu-id="a8504-168">Nella chiamata successiva probabilmente l'utente richiederà un avvio effettivo.</span><span class="sxs-lookup"><span data-stu-id="a8504-168">(In the next call the user will probably ask for an actual start.)</span></span>|<span data-ttu-id="a8504-169">Vengono restituite le dimensioni del buffer richieste (nessun avvio né restituzione di pipe).</span><span class="sxs-lookup"><span data-stu-id="a8504-169">Returns a required buffer size (no start and no pipe return).</span></span> <span data-ttu-id="a8504-170">Il risultato è S_OK.</span><span class="sxs-lookup"><span data-stu-id="a8504-170">Result is S_OK.</span></span>|  
|<span data-ttu-id="a8504-171">Presente</span><span class="sxs-lookup"><span data-stu-id="a8504-171">Present</span></span>|<span data-ttu-id="a8504-172">NULL</span><span class="sxs-lookup"><span data-stu-id="a8504-172">NULL</span></span>|<span data-ttu-id="a8504-173">Non consentito. Input non corretto.</span><span class="sxs-lookup"><span data-stu-id="a8504-173">Not allowed; incorrect input.</span></span>|<span data-ttu-id="a8504-174">Il risultato restituito è LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="a8504-174">Returned result is LOCALDB_ERROR_INVALID_PARAMETER.</span></span>|  
|<span data-ttu-id="a8504-175">Presente</span><span class="sxs-lookup"><span data-stu-id="a8504-175">Present</span></span>|<span data-ttu-id="a8504-176">Presente</span><span class="sxs-lookup"><span data-stu-id="a8504-176">Present</span></span>|<span data-ttu-id="a8504-177">L'utente desidera avviare l'istanza e necessita del nome della pipe per la connessione a quest'ultima dopo il relativo avvio.</span><span class="sxs-lookup"><span data-stu-id="a8504-177">User wants to start the instance and needs the pipe name to connect to it after it is started.</span></span>|<span data-ttu-id="a8504-178">Vengono controllate le dimensioni del buffer, viene avviata l'istanza e viene restituito il nome della pipe nel buffer.</span><span class="sxs-lookup"><span data-stu-id="a8504-178">Checks the buffer size, starts the instance, and returns the pipe name in the buffer.</span></span> <br /><span data-ttu-id="a8504-179">L'argomento relativo alla dimensione del buffer restituisce la lunghezza della stringa "Server =", esclusi i valori null di terminazione.</span><span class="sxs-lookup"><span data-stu-id="a8504-179">The buffer size argument returns the length of the "server=" string, not including terminating nulls.</span></span>|  
  
 <span data-ttu-id="a8504-180">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a8504-180">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8504-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8504-181">See Also</span></span>  
 [<span data-ttu-id="a8504-182">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="a8504-182">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
