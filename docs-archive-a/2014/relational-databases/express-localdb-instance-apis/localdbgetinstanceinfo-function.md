---
title: Funzione LocalDBGetInstanceInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstanceInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 231706f5-26c6-42eb-ab47-315df6b8f824
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dc7cbe2c59a7502a1fd0c8b4f92fb14e5defd50b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626104"
---
# <a name="localdbgetinstanceinfo-function"></a><span data-ttu-id="d9ebb-102">Funzione LocalDBGetInstanceInfo</span><span class="sxs-lookup"><span data-stu-id="d9ebb-102">LocalDBGetInstanceInfo Function</span></span>
  <span data-ttu-id="d9ebb-103">Vengono restituite le informazioni per l'istanza del database locale di SQL Server Express specificata, se esistente, la versione del database locale utilizzata dall'istanza, se quest'ultima è in esecuzione e così via.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-103">Returns information for the specified SQL Server Express LocalDB instance, such as whether it exists, the LocalDB version it uses, whether it is running, and so on.</span></span>  
  
 <span data-ttu-id="d9ebb-104">Le informazioni vengono restituite in un oggetto `struct` denominato **dello structLocalDBInstanceInfo**, che presenta la definizione seguente.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-104">The information is returned in a `struct` named **LocalDBInstanceInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBInstanceInfo  
{  
      // Contains the size of the LocalDBInstanceInfo struct  
      DWORD  cbLocalDBInstanceInfoSize;  
  
      // Holds the instance name  
      TLocalDBInstanceNamewszInstanceName;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // TRUE if the instance configuration registry is corrupted, FALSE otherwise  
      BOOLbConfigurationCorrupted;  
  
      // TRUE if the instance is running at the moment, FALSE otherwise  
      BOOL   bIsRunning;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
  
      // Holds the date and time when the instance was started for the last time  
      FILETIME ftLastStartUTC;  
  
      // Holds the name of the TDS named pipe to connect to the instance  
      WCHARwszConnection;  
  
      // TRUE if the instance is shared, FALSE otherwise  
      BOOLbIsShared;  
  
      // Holds the shared name for the instance (if the instance is shared)  
      TLocalDBInstanceNamewszSharedInstanceName;  
  
      // Holds the SID of the instance owner (if the instance is shared)  
      WCHARwszOwnerSID;   
  
      // TRUE if the instance is Automatic, FALSE otherwise  
      BOOLbIsAutomatic;  
} LocalDBInstanceInfo;  
  
```  
  
 <span data-ttu-id="d9ebb-105">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="d9ebb-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ebb-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9ebb-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetInstanceInfo(  
           PCWSTR wszInstanceName,  
           PLocalDBInstanceInfo pInstanceInfo,  
           DWORD dwInstanceInfoSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9ebb-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9ebb-107">Parameters</span></span>  
 <span data-ttu-id="d9ebb-108">*wszInstanceName*</span><span class="sxs-lookup"><span data-stu-id="d9ebb-108">*wszInstanceName*</span></span>  
 <span data-ttu-id="d9ebb-109">[Input] Nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-109">[Input] The instance name.</span></span>  
  
 <span data-ttu-id="d9ebb-110">*pInstanceInfo*</span><span class="sxs-lookup"><span data-stu-id="d9ebb-110">*pInstanceInfo*</span></span>  
 <span data-ttu-id="d9ebb-111">[Output] Buffer per archiviare le informazioni sull'istanza del database locale.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-111">[Output] The buffer to store the information about the LocalDB instance.</span></span>  
  
 <span data-ttu-id="d9ebb-112">*dwInstanceInfoSize*</span><span class="sxs-lookup"><span data-stu-id="d9ebb-112">*dwInstanceInfoSize*</span></span>  
 <span data-ttu-id="d9ebb-113">Input Include le dimensioni del buffer *InstanceInfo* .</span><span class="sxs-lookup"><span data-stu-id="d9ebb-113">[Input] Holds the size of the *InstanceInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d9ebb-114">Restituisce</span><span class="sxs-lookup"><span data-stu-id="d9ebb-114">Returns</span></span>  
 <span data-ttu-id="d9ebb-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9ebb-115">S_OK</span></span>  
 <span data-ttu-id="d9ebb-116">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="d9ebb-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="d9ebb-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="d9ebb-118">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="d9ebb-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="d9ebb-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="d9ebb-120">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="d9ebb-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="d9ebb-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="d9ebb-122">Nome dell'stanza specificata non valido.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="d9ebb-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="d9ebb-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="d9ebb-124">Istanza inesistente.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-124">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="d9ebb-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="d9ebb-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="d9ebb-126">Percorso di archiviazione richiesto per l'istanza più lungo di MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-126">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="d9ebb-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="d9ebb-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="d9ebb-128">Impossibile accedere alla cartella di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-128">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="d9ebb-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="d9ebb-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="d9ebb-130">Impossibile accedere al Registro di sistema di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-130">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="d9ebb-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="d9ebb-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="d9ebb-132">Configurazione di un'istanza danneggiata.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-132">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="d9ebb-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="d9ebb-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="d9ebb-134">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-134">An unexpected error occurred.</span></span> <span data-ttu-id="d9ebb-135">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-135">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d9ebb-136">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d9ebb-136">Details</span></span>  
 <span data-ttu-id="d9ebb-137">La logica alla base dell'introduzione dell' `struct` argomento size (*lpInstanceInfoSize*) consiste nell'abilitare l'API per la restituzione di versioni diverse di **dello structLocalDBInstanceInfo**, abilitando in modo efficace la compatibilità con le versioni precedenti e precedenti.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-137">The rationale behind the introduction of the `struct` size argument (*lpInstanceInfoSize*) is to enable the API to return different versions of the **LocalDBInstanceInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="d9ebb-138">Se l' `struct` argomento size (*lpInstanceInfoSize*) corrisponde alle dimensioni di una versione nota di **dello structLocalDBInstanceInfo**, `struct` viene restituita tale versione di.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-138">If the `struct` size argument (*lpInstanceInfoSize*) matches the size of a known version of the **LocalDBInstanceInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="d9ebb-139">In caso contrario, viene restituito LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="d9ebb-139">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="d9ebb-140">Un esempio tipico di utilizzo dell'API **LocalDBGetInstanceInfo** è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d9ebb-140">A typical example of **LocalDBGetInstanceInfo** API usage looks like this:</span></span>  
  
```  
LocalDBInstanceInfo ii;  
LocalDBInstanceInfo(L"Test", &ii, sizeof(LocalDBInstanceInfo));  
  
```  
  
 <span data-ttu-id="d9ebb-141">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d9ebb-141">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ebb-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9ebb-142">See Also</span></span>  
 [<span data-ttu-id="d9ebb-143">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="d9ebb-143">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
