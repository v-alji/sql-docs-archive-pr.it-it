---
title: Funzione LocalDBShareInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBShareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 21eb3b9a-7d32-455b-89bb-f624198cd202
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 238bff0b3512ceb03ead186dc001165274bd4e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627706"
---
# <a name="localdbshareinstance-function"></a><span data-ttu-id="387fc-102">Funzione LocalDBShareInstance</span><span class="sxs-lookup"><span data-stu-id="387fc-102">LocalDBShareInstance Function</span></span>
  <span data-ttu-id="387fc-103">Condivide l'istanza di SQL Server Express LocalDB specificata con altri utenti del computer, utilizzando il nome condiviso specificato.</span><span class="sxs-lookup"><span data-stu-id="387fc-103">Shares the specified SQL Server Express LocalDB instance with other users of the computer, using the specified shared name.</span></span>  
  
 <span data-ttu-id="387fc-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="387fc-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="387fc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="387fc-105">Syntax</span></span>  
  
```  
HRESULT LocalDBShareInstance(  
           PSID pOwnerSID,  
           PCWSTR pInstancePrivateName,  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="387fc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="387fc-106">Parameters</span></span>  
 <span data-ttu-id="387fc-107">*pOwnerSID*</span><span class="sxs-lookup"><span data-stu-id="387fc-107">*pOwnerSID*</span></span>  
 <span data-ttu-id="387fc-108">[Input] SID del proprietario dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="387fc-108">[Input] The SID of the instance owner.</span></span>  
  
 <span data-ttu-id="387fc-109">*pInstancePrivateName*</span><span class="sxs-lookup"><span data-stu-id="387fc-109">*pInstancePrivateName*</span></span>  
 <span data-ttu-id="387fc-110">[Input] Nome privato dell'istanza di LocalDB da condividere.</span><span class="sxs-lookup"><span data-stu-id="387fc-110">[Input] The private name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="387fc-111">*pInstanceSharedName*</span><span class="sxs-lookup"><span data-stu-id="387fc-111">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="387fc-112">[Input] Nome condiviso dell'istanza di LocalDB da condividere.</span><span class="sxs-lookup"><span data-stu-id="387fc-112">[Input] The shared name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="387fc-113">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="387fc-113">*dwFlags*</span></span>  
 <span data-ttu-id="387fc-114">[Input] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="387fc-114">[Input] Reserved for future use.</span></span> <span data-ttu-id="387fc-115">Deve essere impostato attualmente su 0.</span><span class="sxs-lookup"><span data-stu-id="387fc-115">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="387fc-116">Restituisce</span><span class="sxs-lookup"><span data-stu-id="387fc-116">Returns</span></span>  
 <span data-ttu-id="387fc-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="387fc-117">S_OK</span></span>  
 <span data-ttu-id="387fc-118">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="387fc-118">The function succeeded.</span></span>  
  
 [<span data-ttu-id="387fc-119">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="387fc-119">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="387fc-120">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="387fc-120">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="387fc-121">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="387fc-121">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="387fc-122">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="387fc-122">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="387fc-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="387fc-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="387fc-124">Nome dell'stanza specificata non valido.</span><span class="sxs-lookup"><span data-stu-id="387fc-124">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="387fc-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="387fc-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="387fc-126">Istanza specificata inesistente.</span><span class="sxs-lookup"><span data-stu-id="387fc-126">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="387fc-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="387fc-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="387fc-128">Per eseguire questa operazione, è necessario disporre dei privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="387fc-128">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="387fc-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span><span class="sxs-lookup"><span data-stu-id="387fc-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span></span>](../express-localdb-error-messages/localdb-error-shared-name-taken.md)  
 <span data-ttu-id="387fc-130">Nome condiviso specificato già accettato.</span><span class="sxs-lookup"><span data-stu-id="387fc-130">The specified shared name is already taken.</span></span>  
  
 [<span data-ttu-id="387fc-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="387fc-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>](../express-localdb-error-messages/localdb-error-instance-already-shared.md)  
 <span data-ttu-id="387fc-132">Istanza specificata già condivisa.</span><span class="sxs-lookup"><span data-stu-id="387fc-132">The specified instance is already shared.</span></span>  
  
 [<span data-ttu-id="387fc-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="387fc-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="387fc-134">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="387fc-134">An unexpected error occurred.</span></span> <span data-ttu-id="387fc-135">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="387fc-135">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="387fc-136">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="387fc-136">Remarks</span></span>  
 <span data-ttu-id="387fc-137">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="387fc-137">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="387fc-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="387fc-138">See Also</span></span>  
 [<span data-ttu-id="387fc-139">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="387fc-139">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
