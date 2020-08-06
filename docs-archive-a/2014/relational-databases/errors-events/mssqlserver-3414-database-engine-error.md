---
title: MSSQLSERVER_3414 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3414 (Database Engine error)
ms.assetid: f25852f9-b91c-4356-b817-78bec9ec8db4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: aecaf2a920552b8ea66804600fa8bd4168175e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636110"
---
# <a name="mssqlserver_3414"></a><span data-ttu-id="7f078-102">MSSQLSERVER_3414</span><span class="sxs-lookup"><span data-stu-id="7f078-102">MSSQLSERVER_3414</span></span>
    
## <a name="details"></a><span data-ttu-id="7f078-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7f078-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7f078-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="7f078-104">Product Name</span></span>|<span data-ttu-id="7f078-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7f078-105">SQL Server</span></span>|  
|<span data-ttu-id="7f078-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="7f078-106">Event ID</span></span>|<span data-ttu-id="7f078-107">3414</span><span class="sxs-lookup"><span data-stu-id="7f078-107">3414</span></span>|  
|<span data-ttu-id="7f078-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="7f078-108">Event Source</span></span>|<span data-ttu-id="7f078-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7f078-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7f078-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7f078-110">Component</span></span>|<span data-ttu-id="7f078-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7f078-111">SQLEngine</span></span>|  
|<span data-ttu-id="7f078-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="7f078-112">Symbolic Name</span></span>|<span data-ttu-id="7f078-113">REC_GIVEUP</span><span class="sxs-lookup"><span data-stu-id="7f078-113">REC_GIVEUP</span></span>|  
|<span data-ttu-id="7f078-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="7f078-114">Message Text</span></span>|<span data-ttu-id="7f078-115">Durante il recupero si è verificato un errore che impedisce il riavvio del database '%.\*ls' (ID database %d).</span><span class="sxs-lookup"><span data-stu-id="7f078-115">An error occurred during recovery, preventing the database '%.\*ls' (database ID %d) from restarting.</span></span> <span data-ttu-id="7f078-116">Individuare gli errori e correggerli oppure eseguire il ripristino da una copia di backup valida nota.</span><span class="sxs-lookup"><span data-stu-id="7f078-116">Diagnose the recovery errors and fix them, or restore from a known good backup.</span></span> <span data-ttu-id="7f078-117">Se non è possibile correggere gli errori, contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f078-117">If errors are not corrected or expected, contact Technical Support.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7f078-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="7f078-118">Explanation</span></span>  
 <span data-ttu-id="7f078-119">Il database specificato è stato recuperato, ma non è stato possibile avviarlo a causa di errori verificatisi durante il recupero.</span><span class="sxs-lookup"><span data-stu-id="7f078-119">The specified database was recovered, but failed to start, because errors occurred during recovery.</span></span> <span data-ttu-id="7f078-120">Tale errore ha determinato l'impostazione del database sullo stato SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="7f078-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="7f078-121">Il filegroup primario, e probabilmente altri filegroup, sono sospetti e possono essere danneggiati.</span><span class="sxs-lookup"><span data-stu-id="7f078-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="7f078-122">Non è possibile recuperare il database durante l'avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , pertanto non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="7f078-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="7f078-123">Per risolvere il problema, è necessario l'intervento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7f078-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="7f078-124">Se questo errore si verifica per **tempdb**, l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene arrestata.</span><span class="sxs-lookup"><span data-stu-id="7f078-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7f078-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7f078-125">User Action</span></span>  
 <span data-ttu-id="7f078-126">Questo errore può essere causato da una condizione temporanea già presente nel sistema durante un determinato tentativo di avvio dell'istanza del server o di recupero di un database.</span><span class="sxs-lookup"><span data-stu-id="7f078-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="7f078-127">Può inoltre essere causato da un errore permanente che si verifica ogni volta che si tenta di avviare il database.</span><span class="sxs-lookup"><span data-stu-id="7f078-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="7f078-128">Per informazioni sulla causa, esaminare il registro eventi di Windows per cercare un errore precedente che indichi l'errore specifico.</span><span class="sxs-lookup"><span data-stu-id="7f078-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="7f078-129">Per informazioni sulla causa di questa occorrenza dell'errore 3414, esaminare il registro eventi di Windows per cercare un errore precedente che indichi l'errore specifico.</span><span class="sxs-lookup"><span data-stu-id="7f078-129">For information about the cause of this occurrence of error 3414, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="7f078-130">L'azione appropriata dell'utente varia a seconda che le informazioni nel registro eventi di Windows indichino che l'errore [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato causato da una condizione temporanea o da un errore permanente.</span><span class="sxs-lookup"><span data-stu-id="7f078-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="7f078-131">Per informazioni sulle azioni eseguibili dall'utente per risolvere l'errore 3414, vedere la documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f078-131">For information about the user actions for troubleshooting error 3414, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f078-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f078-132">See Also</span></span>  
 <span data-ttu-id="7f078-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f078-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="7f078-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f078-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="7f078-135">[Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="7f078-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="7f078-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="7f078-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="7f078-137">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f078-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
