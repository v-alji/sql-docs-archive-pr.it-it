---
title: Funzione LocalDBDeleteInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBDeleteInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 37cb2a7e-672a-4223-b6f3-a94d7b8d58cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8d4c873e045c5effed476ca9d147270d159ec3b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635615"
---
# <a name="localdbdeleteinstance-function"></a><span data-ttu-id="8b78c-102">Funzione LocalDBDeleteInstance</span><span class="sxs-lookup"><span data-stu-id="8b78c-102">LocalDBDeleteInstance Function</span></span>
  <span data-ttu-id="8b78c-103">Rimuove l'istanza specificata del database locale di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="8b78c-103">Removes the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="8b78c-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="8b78c-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b78c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b78c-105">Syntax</span></span>  
  
```  
HRESULT LocalDBDeleteInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b78c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b78c-106">Parameters</span></span>  
 <span data-ttu-id="8b78c-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="8b78c-107">*pInstanceName*</span></span>  
 <span data-ttu-id="8b78c-108">[Input] Nome dell'istanza del database locale da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="8b78c-108">[Input] The name of the LocalDB instance to remove.</span></span>  
  
 <span data-ttu-id="8b78c-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="8b78c-109">*dwFlags*</span></span>  
 <span data-ttu-id="8b78c-110">[Input] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="8b78c-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="8b78c-111">Deve essere impostato attualmente su 0.</span><span class="sxs-lookup"><span data-stu-id="8b78c-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="8b78c-112">Restituisce</span><span class="sxs-lookup"><span data-stu-id="8b78c-112">Returns</span></span>  
 <span data-ttu-id="8b78c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b78c-113">S_OK</span></span>  
 <span data-ttu-id="8b78c-114">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="8b78c-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="8b78c-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="8b78c-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="8b78c-116">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="8b78c-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="8b78c-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="8b78c-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="8b78c-118">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="8b78c-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="8b78c-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b78c-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="8b78c-120">Nome dell'stanza specificata non valido.</span><span class="sxs-lookup"><span data-stu-id="8b78c-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="8b78c-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="8b78c-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="8b78c-122">Istanza specificata inesistente.</span><span class="sxs-lookup"><span data-stu-id="8b78c-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="8b78c-123">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="8b78c-123">LOCALDB_ERROR_INSTANCE_BUSY</span></span>](../express-localdb-error-messages/localdb-error-instance-busy.md)  
 <span data-ttu-id="8b78c-124">Istanza specificata in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8b78c-124">The specified instance is running.</span></span>  
  
 [<span data-ttu-id="8b78c-125">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8b78c-125">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="8b78c-126">Timeout durante il tentativo di acquisizione dei blocchi di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="8b78c-126">A time-out occurred while trying to acquire synchronization locks.</span></span>  
  
 [<span data-ttu-id="8b78c-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="8b78c-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="8b78c-128">Percorso di archiviazione richiesto per l'istanza più lungo di MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="8b78c-128">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="8b78c-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="8b78c-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="8b78c-130">Impossibile recuperare una cartella del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="8b78c-130">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="8b78c-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="8b78c-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="8b78c-132">Impossibile accedere alla cartella di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="8b78c-132">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="8b78c-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="8b78c-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="8b78c-134">Impossibile accedere al Registro di sistema di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="8b78c-134">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="8b78c-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="8b78c-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="8b78c-136">Impossibile modificare il Registro di sistema di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="8b78c-136">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="8b78c-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="8b78c-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="8b78c-138">Configurazione di un'istanza danneggiata.</span><span class="sxs-lookup"><span data-stu-id="8b78c-138">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="8b78c-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b78c-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="8b78c-140">Il chiamante API non è il proprietario dell'istanza del database locale.</span><span class="sxs-lookup"><span data-stu-id="8b78c-140">API caller is not Local Database instance owner.</span></span>  
  
 [<span data-ttu-id="8b78c-141">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="8b78c-141">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="8b78c-142">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="8b78c-142">An unexpected error occurred.</span></span> <span data-ttu-id="8b78c-143">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="8b78c-143">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b78c-144">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8b78c-144">Remarks</span></span>  
 <span data-ttu-id="8b78c-145">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8b78c-145">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b78c-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b78c-146">See Also</span></span>  
 [<span data-ttu-id="8b78c-147">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="8b78c-147">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
