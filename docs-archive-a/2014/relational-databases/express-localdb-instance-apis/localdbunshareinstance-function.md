---
title: Funzione LocalDBUnshareInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBUnshareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 54012ccb-eded-43f7-8ea5-da5ce79224c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 77ebf8cad9d410b047fccede4360ca0041637986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624732"
---
# <a name="localdbunshareinstance-function"></a><span data-ttu-id="f831c-102">Funzione LocalDBUnshareInstance</span><span class="sxs-lookup"><span data-stu-id="f831c-102">LocalDBUnshareInstance Function</span></span>
  <span data-ttu-id="f831c-103">Viene arrestata la condivisione dell'istanza del database locale di SQL Server Express specificata.</span><span class="sxs-lookup"><span data-stu-id="f831c-103">Stops the sharing of the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="f831c-104">**File di intestazione:** sqlncli. h</span><span class="sxs-lookup"><span data-stu-id="f831c-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f831c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f831c-105">Syntax</span></span>  
  
```  
HRESULT LocalDBUnShareInstance(  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f831c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f831c-106">Parameters</span></span>  
 <span data-ttu-id="f831c-107">*pInstanceSharedName*</span><span class="sxs-lookup"><span data-stu-id="f831c-107">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="f831c-108">[Input] Nome condiviso dell'istanza di LocalDB di cui interrompere la condivisione.</span><span class="sxs-lookup"><span data-stu-id="f831c-108">[Input] The shared name for the LocalDB instance to unshare.</span></span>  
  
 <span data-ttu-id="f831c-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="f831c-109">*dwFlags*</span></span>  
 <span data-ttu-id="f831c-110">[Input] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="f831c-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="f831c-111">Deve essere impostato attualmente su 0.</span><span class="sxs-lookup"><span data-stu-id="f831c-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f831c-112">Restituisce</span><span class="sxs-lookup"><span data-stu-id="f831c-112">Returns</span></span>  
 <span data-ttu-id="f831c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f831c-113">S_OK</span></span>  
 <span data-ttu-id="f831c-114">Funzione completata.</span><span class="sxs-lookup"><span data-stu-id="f831c-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="f831c-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="f831c-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="f831c-116">Database locale di SQL Server Express non installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="f831c-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="f831c-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="f831c-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="f831c-118">Uno o più parametri di input specificati non validi.</span><span class="sxs-lookup"><span data-stu-id="f831c-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="f831c-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="f831c-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="f831c-120">Nome dell'stanza specificata non valido.</span><span class="sxs-lookup"><span data-stu-id="f831c-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="f831c-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="f831c-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="f831c-122">Istanza specificata inesistente.</span><span class="sxs-lookup"><span data-stu-id="f831c-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="f831c-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="f831c-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="f831c-124">Per eseguire questa operazione, è necessario disporre dei privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f831c-124">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="f831c-125">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="f831c-125">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="f831c-126">Si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="f831c-126">An unexpected error occurred.</span></span> <span data-ttu-id="f831c-127">Per informazioni, vedere il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="f831c-127">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f831c-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f831c-128">Remarks</span></span>  
 <span data-ttu-id="f831c-129">Per un esempio di codice in cui viene utilizzata l'API del database locale, vedere [SQL Server Express riferimento al database locale](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f831c-129">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f831c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f831c-130">See Also</span></span>  
 [<span data-ttu-id="f831c-131">Informazioni sulla versione e intestazione di SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="f831c-131">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
