---
title: MSSQLSERVER_5235 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5235 (Database Engine error)
ms.assetid: 1aa7e6a5-7ccb-43c8-a1fd-d50e92e0a798
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 42c807944d7506a6a118de97ccd8c2c488942c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723912"
---
# <a name="mssqlserver_5235"></a><span data-ttu-id="5cf5c-102">MSSQLSERVER_5235</span><span class="sxs-lookup"><span data-stu-id="5cf5c-102">MSSQLSERVER_5235</span></span>
    
## <a name="details"></a><span data-ttu-id="5cf5c-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5cf5c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5cf5c-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5cf5c-104">Product Name</span></span>|<span data-ttu-id="5cf5c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5cf5c-105">SQL Server</span></span>|  
|<span data-ttu-id="5cf5c-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="5cf5c-106">Event ID</span></span>|<span data-ttu-id="5cf5c-107">5235</span><span class="sxs-lookup"><span data-stu-id="5cf5c-107">5235</span></span>|  
|<span data-ttu-id="5cf5c-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5cf5c-108">Event Source</span></span>|<span data-ttu-id="5cf5c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5cf5c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5cf5c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5cf5c-110">Component</span></span>|<span data-ttu-id="5cf5c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5cf5c-111">SQLEngine</span></span>|  
|<span data-ttu-id="5cf5c-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5cf5c-112">Symbolic Name</span></span>|<span data-ttu-id="5cf5c-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span><span class="sxs-lookup"><span data-stu-id="5cf5c-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span></span>|  
|<span data-ttu-id="5cf5c-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5cf5c-114">Message Text</span></span>|<span data-ttu-id="5cf5c-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS eseguito da USER_NAME è stato terminato in modo anomalo a causa dello stato di errore ERROR_STATE.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS executed by USER_NAME terminated abnormally due to error state ERROR_STATE.</span></span> <span data-ttu-id="5cf5c-116">Tempo trascorso: HOURS ore MINUTES minuti SECONDS secondi.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-116">Elapsed time: HOURS hours MINUTES minutes SECONDS seconds.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5cf5c-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5cf5c-117">Explanation</span></span>  
 <span data-ttu-id="5cf5c-118">Messaggio di riepilogo registrato da DBCC nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando si verifica una chiusura imprevista durante l'esecuzione del comando.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-118">This is the summary message that DBCC prints to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log when an unexpected termination occurs while the command is running.</span></span> <span data-ttu-id="5cf5c-119">Lo stato dell'errore riportato nel messaggio definisce il tipo di chiusura imprevista.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-119">The error state reported in the message defines the type of unexpected termination.</span></span>  
  
 <span data-ttu-id="5cf5c-120">Nella tabella seguente vengono elencati e definiti gli stati di errore.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-120">The following table lists and defines the error states.</span></span>  
  
|<span data-ttu-id="5cf5c-121">Stato di errore</span><span class="sxs-lookup"><span data-stu-id="5cf5c-121">Error state</span></span>|<span data-ttu-id="5cf5c-122">Definizione</span><span class="sxs-lookup"><span data-stu-id="5cf5c-122">Definition</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="5cf5c-123">Stato 0</span><span class="sxs-lookup"><span data-stu-id="5cf5c-123">State 0</span></span>|<span data-ttu-id="5cf5c-124">L'istruzione è stata interrotta a causa di un danneggiamento irreversibile dei metadati.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-124">The statement was terminated because of a fatal metadata corruption.</span></span> <span data-ttu-id="5cf5c-125">Insieme al messaggio saranno presenti una o più istanze dell'errore 8930.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-125">This message will be accompanied by one or more instances of error 8930.</span></span>|  
|<span data-ttu-id="5cf5c-126">Stato 1</span><span class="sxs-lookup"><span data-stu-id="5cf5c-126">State 1</span></span>|<span data-ttu-id="5cf5c-127">L'istruzione è stata interrotta a causa di un errore di controllo interno.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-127">The statement was terminated because of an internal check failure.</span></span> <span data-ttu-id="5cf5c-128">Insieme al messaggio saranno presenti una o più istanze dell'errore 8967.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-128">This message will be accompanied by one or more instances of error 8967.</span></span>|  
|<span data-ttu-id="5cf5c-129">Stato 2</span><span class="sxs-lookup"><span data-stu-id="5cf5c-129">State 2</span></span>|<span data-ttu-id="5cf5c-130">I controlli delle tabelle di sistema del motore di archiviazione principali da parte della tabella di sistema di base non sono stati eseguiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-130">Basic system table checks of the core storage engine system tables failed.</span></span> <span data-ttu-id="5cf5c-131">Insieme al messaggio saranno presenti una o più istanze dell'errore [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md) o [7988](mssqlserver-7988-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="5cf5c-131">This message will be accompanied by one or more instances of error [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md), or [7988](mssqlserver-7988-database-engine-error.md).</span></span>|  
|<span data-ttu-id="5cf5c-132">Stato 3</span><span class="sxs-lookup"><span data-stu-id="5cf5c-132">State 3</span></span>|<span data-ttu-id="5cf5c-133">La correzione in modalità di emergenza di DBCC non è stata eseguita correttamente poiché non è stato possibile avviare il database dopo la ricompilazione del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-133">DBCC emergency-mode repair failed because the database could not be started after rebuilding the transaction log.</span></span> <span data-ttu-id="5cf5c-134">Insieme al messaggio sarà presente l'errore 7909.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-134">This message will be accompanied by error 7909.</span></span>|  
|<span data-ttu-id="5cf5c-135">Stato 4</span><span class="sxs-lookup"><span data-stu-id="5cf5c-135">State 4</span></span>|<span data-ttu-id="5cf5c-136">Durante l'esecuzione del comando si è verificata un'asserzione non riuscita o una violazione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-136">A failed assertion or access violation occurred during the execution of the command.</span></span>|  
|<span data-ttu-id="5cf5c-137">Stato 5</span><span class="sxs-lookup"><span data-stu-id="5cf5c-137">State 5</span></span>|<span data-ttu-id="5cf5c-138">Si è verificato un errore sconosciuto che ha causato l'interruzione imprevista del comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-138">An unknown failure occurred that unexpectedly terminated the DBCC command.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="5cf5c-139">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5cf5c-139">User Action</span></span>  
 <span data-ttu-id="5cf5c-140">Nella tabella seguente vengono illustrate le azioni utente appropriate agli stati di errore specificati.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-140">The following table provides the user action that is appropriate for the specified error state.</span></span>  
  
|<span data-ttu-id="5cf5c-141">Stato di errore</span><span class="sxs-lookup"><span data-stu-id="5cf5c-141">Error state</span></span>|<span data-ttu-id="5cf5c-142">Azione utente</span><span class="sxs-lookup"><span data-stu-id="5cf5c-142">User action</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5cf5c-143">Stato 0</span><span class="sxs-lookup"><span data-stu-id="5cf5c-143">State 0</span></span>|<span data-ttu-id="5cf5c-144">Eseguire un ripristino dal backup.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-144">Restore from backup.</span></span>|  
|<span data-ttu-id="5cf5c-145">Stato 1</span><span class="sxs-lookup"><span data-stu-id="5cf5c-145">State 1</span></span>|<span data-ttu-id="5cf5c-146">Contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cf5c-146">Contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>|  
|<span data-ttu-id="5cf5c-147">Stato 2</span><span class="sxs-lookup"><span data-stu-id="5cf5c-147">State 2</span></span>|<span data-ttu-id="5cf5c-148">Eseguire un ripristino dal backup.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-148">Restore from backup.</span></span>|  
|<span data-ttu-id="5cf5c-149">Stato 3</span><span class="sxs-lookup"><span data-stu-id="5cf5c-149">State 3</span></span>|<span data-ttu-id="5cf5c-150">Eseguire un ripristino dal backup.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-150">Restore from backup.</span></span>|  
|<span data-ttu-id="5cf5c-151">Stato 4</span><span class="sxs-lookup"><span data-stu-id="5cf5c-151">State 4</span></span>|<span data-ttu-id="5cf5c-152">Contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-152">Contact CSS.</span></span>|  
|<span data-ttu-id="5cf5c-153">Stato 5</span><span class="sxs-lookup"><span data-stu-id="5cf5c-153">State 5</span></span>|<span data-ttu-id="5cf5c-154">Eseguire di nuovo il comando.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-154">Run the command again.</span></span> <span data-ttu-id="5cf5c-155">Se il problema persiste, contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5cf5c-155">If the problem persists, contact CSS.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5cf5c-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cf5c-156">See Also</span></span>  
 [<span data-ttu-id="5cf5c-157">DBCC &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5cf5c-157">DBCC &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-transact-sql)  
  
  
