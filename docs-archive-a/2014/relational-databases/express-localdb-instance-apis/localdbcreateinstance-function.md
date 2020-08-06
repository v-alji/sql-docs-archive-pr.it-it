---
title: Funzione LocalDBCreateInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBCreateInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 3eebb485-8a53-4a79-82a9-57b8de9f8e84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ff822c552176ad8c083a1c8ea6c0f2430f72972f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635620"
---
# <a name="localdbcreateinstance-function"></a><span data-ttu-id="9bc1c-102">Funzione LocalDBCreateInstance</span><span class="sxs-lookup"><span data-stu-id="9bc1c-102">LocalDBCreateInstance Function</span></span>
  <span data-ttu-id="9bc1c-103">Viene creata un'istanza del database locale di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-103">Creates a new SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="9bc1c-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="9bc1c-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bc1c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bc1c-105">Syntax</span></span>  
  
```  
HRESULT LocalDBCreateInstance(  
           PCWSTR wszVersion,  
           PCWSTR pInstanceName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bc1c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9bc1c-106">Parameters</span></span>  
 <span data-ttu-id="9bc1c-107">*wszVersion*</span><span class="sxs-lookup"><span data-stu-id="9bc1c-107">*wszVersion*</span></span>  
 <span data-ttu-id="9bc1c-108">[Input] Versione del database locale, ad esempio 11.0 o 11.0.1094.2.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-108">[Input] The LocalDB version, for example 11.0 or 11.0.1094.2.</span></span>  
  
 <span data-ttu-id="9bc1c-109">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="9bc1c-109">*pInstanceName*</span></span>  
 <span data-ttu-id="9bc1c-110">[Input] Nome dell'istanza del database locale da creare.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-110">[Input] The name for the LocalDB instance to create.</span></span>  
  
 <span data-ttu-id="9bc1c-111">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="9bc1c-111">*dwFlags*</span></span>  
 <span data-ttu-id="9bc1c-112">[Input] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-112">[Input] Reserved for future use.</span></span> <span data-ttu-id="9bc1c-113">Deve essere impostato attualmente su 0.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-113">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="9bc1c-114">Restituisce</span><span class="sxs-lookup"><span data-stu-id="9bc1c-114">Returns</span></span>  
 <span data-ttu-id="9bc1c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9bc1c-115">S_OK</span></span>  
 <span data-ttu-id="9bc1c-116">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="9bc1c-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="9bc1c-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="9bc1c-118">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="9bc1c-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="9bc1c-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="9bc1c-120">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="9bc1c-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="9bc1c-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="9bc1c-122">Nome dell'stanza specificata non valido.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="9bc1c-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="9bc1c-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="9bc1c-124">Percorso di archiviazione richiesto per l'istanza più lungo di MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-124">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="9bc1c-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="9bc1c-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>](../express-localdb-error-messages/localdb-error-instance-exists-with-lower-version.md)  
 <span data-ttu-id="9bc1c-126">Istanza specificata già esistente ma con relativa versione meno recente di quella richiesta.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-126">The specified instance already exists but its version is lower than requested.</span></span>  
  
 [<span data-ttu-id="9bc1c-127">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="9bc1c-127">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="9bc1c-128">Versione specificata non disponibile.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-128">The specified version is not available.</span></span>  
  
 [<span data-ttu-id="9bc1c-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="9bc1c-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-version-requested-not-installed.md)  
 <span data-ttu-id="9bc1c-130">Livello di patch specificato non installato.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-130">The specified patch level is not installed.</span></span>  
  
 [<span data-ttu-id="9bc1c-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="9bc1c-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-instance-folder.md)  
 <span data-ttu-id="9bc1c-132">Impossibile creare una cartella in %profiloutente%.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-132">A folder cannot be created under %userprofile%.</span></span>  
  
 [<span data-ttu-id="9bc1c-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="9bc1c-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="9bc1c-134">Impossibile recuperare una cartella del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-134">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="9bc1c-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="9bc1c-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="9bc1c-136">Impossibile accedere alla cartella di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-136">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="9bc1c-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="9bc1c-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="9bc1c-138">Impossibile accedere al Registro di sistema di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-138">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="9bc1c-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="9bc1c-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="9bc1c-140">Impossibile modificare il Registro di sistema di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-140">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="9bc1c-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="9bc1c-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="9bc1c-142">Avviato processo di SQL Server ma tale operazione non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-142">A SQL Server process is started but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="9bc1c-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="9bc1c-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="9bc1c-144">Configurazione di un'istanza danneggiata.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-144">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="9bc1c-145">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="9bc1c-145">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="9bc1c-146">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-146">An unexpected error occurred.</span></span> <span data-ttu-id="9bc1c-147">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-147">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bc1c-148">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9bc1c-148">Remarks</span></span>  
 <span data-ttu-id="9bc1c-149">Se un'istanza del database locale completamente funzionale con il nome specificato già esiste e la versione è uguale o successiva rispetto a quella richiesta, il risultato è S_OK.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-149">If a fully functional LocalDB instance with the specified name already exists and its version is equal to or higher than requested, the result is S_OK.</span></span>  
  
 <span data-ttu-id="9bc1c-150">Nei casi in cui un'istanza esistente è danneggiata, non verranno completate le successive chiamate al metodo API `LocalDBCreateInstance`.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-150">In cases when an existing instance becomes corrupted, subsequent calls to the `LocalDBCreateInstance` API method will fail.</span></span> <span data-ttu-id="9bc1c-151">Le istanze danneggiate devono essere corrette manualmente o eliminate in modo esplicito prima che possano essere utilizzate di nuovo.</span><span class="sxs-lookup"><span data-stu-id="9bc1c-151">Corrupted instances must be fixed manually or explicitly deleted before they can be used again.</span></span>  
  
 <span data-ttu-id="9bc1c-152">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9bc1c-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc1c-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bc1c-153">See Also</span></span>  
 [<span data-ttu-id="9bc1c-154">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="9bc1c-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
