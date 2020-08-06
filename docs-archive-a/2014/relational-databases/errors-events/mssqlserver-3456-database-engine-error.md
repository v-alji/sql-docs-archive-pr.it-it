---
title: MSSQLSERVER_3456 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3456 (Database Engine error)
ms.assetid: d11b2b2c-3ae4-4023-b82f-05b561bfacce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f13316bdd3147bb0ad63c8d4a2fb18f1fce74006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716384"
---
# <a name="mssqlserver_3456"></a><span data-ttu-id="08646-102">MSSQLSERVER_3456</span><span class="sxs-lookup"><span data-stu-id="08646-102">MSSQLSERVER_3456</span></span>
    
## <a name="details"></a><span data-ttu-id="08646-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="08646-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08646-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="08646-104">Product Name</span></span>|<span data-ttu-id="08646-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="08646-105">SQL Server</span></span>|  
|<span data-ttu-id="08646-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="08646-106">Event ID</span></span>|<span data-ttu-id="08646-107">3456</span><span class="sxs-lookup"><span data-stu-id="08646-107">3456</span></span>|  
|<span data-ttu-id="08646-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="08646-108">Event Source</span></span>|<span data-ttu-id="08646-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="08646-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="08646-110">Componente</span><span class="sxs-lookup"><span data-stu-id="08646-110">Component</span></span>|<span data-ttu-id="08646-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="08646-111">SQLEngine</span></span>|  
|<span data-ttu-id="08646-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="08646-112">Symbolic Name</span></span>|<span data-ttu-id="08646-113">REC_REDOLSNMISMATCH</span><span class="sxs-lookup"><span data-stu-id="08646-113">REC_REDOLSNMISMATCH</span></span>|  
|<span data-ttu-id="08646-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="08646-114">Message Text</span></span>|<span data-ttu-id="08646-115">Impossibile eseguire il rollforward del record di log %S_LSN per l'ID di transazione %S_XID, pagina %S_PGID, database '%.\*ls' (ID di database %d).</span><span class="sxs-lookup"><span data-stu-id="08646-115">Could not redo log record %S_LSN, for transaction ID %S_XID, on page %S_PGID, database '%.\*ls' (database ID %d).</span></span> <span data-ttu-id="08646-116">Pagina: LSN = %S_LSN, tipo = %ld.</span><span class="sxs-lookup"><span data-stu-id="08646-116">Page: LSN = %S_LSN, type = %ld.</span></span> <span data-ttu-id="08646-117">Log: OpCode = %ld, contesto=%d, PrevPageLSN: %S_LSN.</span><span class="sxs-lookup"><span data-stu-id="08646-117">Log: OpCode = %ld, context %ld, PrevPageLSN: %S_LSN.</span></span> <span data-ttu-id="08646-118">Correggere il database oppure ripristinarlo da un backup.</span><span class="sxs-lookup"><span data-stu-id="08646-118">Restore from a backup of the database, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08646-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="08646-119">Explanation</span></span>  
 <span data-ttu-id="08646-120">Durante l'operazione di ripristino non è stato possibile eseguire il rollforward del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="08646-120">The restore operation was unable to redo the transaction log.</span></span> <span data-ttu-id="08646-121">Tale errore ha determinato l'impostazione del database sullo stato SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="08646-121">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="08646-122">Il filegroup primario, e probabilmente altri filegroup, sono sospetti e possono essere danneggiati.</span><span class="sxs-lookup"><span data-stu-id="08646-122">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="08646-123">Non è possibile recuperare il database durante l'avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , pertanto non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="08646-123">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="08646-124">Per risolvere il problema, è necessario l'intervento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="08646-124">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="08646-125">Se questo errore si verifica per **tempdb**, l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene arrestata.</span><span class="sxs-lookup"><span data-stu-id="08646-125">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08646-126">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="08646-126">User Action</span></span>  
 <span data-ttu-id="08646-127">Questo errore può essere causato da una condizione temporanea già presente nel sistema durante un determinato tentativo di avvio dell'istanza del server o di recupero di un database.</span><span class="sxs-lookup"><span data-stu-id="08646-127">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="08646-128">Può inoltre essere causato da un errore permanente che si verifica ogni volta che si tenta di avviare il database.</span><span class="sxs-lookup"><span data-stu-id="08646-128">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="08646-129">Per informazioni sulla causa, esaminare il registro eventi di Windows per cercare un errore precedente che indichi l'errore specifico.</span><span class="sxs-lookup"><span data-stu-id="08646-129">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="08646-130">Per informazioni sulla causa di questa occorrenza dell'errore 3456, esaminare il registro eventi di Windows per cercare un errore precedente che indichi l'errore specifico.</span><span class="sxs-lookup"><span data-stu-id="08646-130">For information about the cause of this occurrence of error 3456, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="08646-131">L'azione appropriata dell'utente varia a seconda che le informazioni nel registro eventi di Windows indichino che l'errore [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato causato da una condizione temporanea o da un errore permanente.</span><span class="sxs-lookup"><span data-stu-id="08646-131">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="08646-132">Per informazioni sulle azioni eseguibili dall'utente per risolvere l'errore 3456, vedere la documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08646-132">For information about the user actions for troubleshooting error 3456, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08646-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08646-133">See Also</span></span>  
 <span data-ttu-id="08646-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="08646-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="08646-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="08646-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="08646-136">[Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="08646-136">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="08646-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="08646-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="08646-138">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="08646-138">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
