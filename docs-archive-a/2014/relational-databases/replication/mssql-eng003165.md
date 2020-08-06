---
title: MSSQL_ENG003165 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003165 error
ms.assetid: 707d33dd-644e-4cc9-ac51-dddd49031530
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1702588ba6ac1beeb33b87a7afc7fc330271559
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623185"
---
# <a name="mssql_eng003165"></a><span data-ttu-id="6cc14-102">MSSQL_ENG003165</span><span class="sxs-lookup"><span data-stu-id="6cc14-102">MSSQL_ENG003165</span></span>
    
## <a name="message-details"></a><span data-ttu-id="6cc14-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="6cc14-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6cc14-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="6cc14-104">Product Name</span></span>|<span data-ttu-id="6cc14-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6cc14-105">SQL Server</span></span>|  
|<span data-ttu-id="6cc14-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="6cc14-106">Event ID</span></span>|<span data-ttu-id="6cc14-107">3165</span><span class="sxs-lookup"><span data-stu-id="6cc14-107">3165</span></span>|  
|<span data-ttu-id="6cc14-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="6cc14-108">Event Source</span></span>|<span data-ttu-id="6cc14-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6cc14-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6cc14-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6cc14-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="6cc14-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="6cc14-111">Symbolic Name</span></span>||  
|<span data-ttu-id="6cc14-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="6cc14-112">Message Text</span></span>|<span data-ttu-id="6cc14-113">Il database '%ls' è stato ripristinato ma è stato rilevato un errore durante il ripristino o la rimozione della replica.</span><span class="sxs-lookup"><span data-stu-id="6cc14-113">Database '%ls' was restored; however, an error was encountered while replication was being restored/removed.</span></span> <span data-ttu-id="6cc14-114">Il database è stato lasciato offline.</span><span class="sxs-lookup"><span data-stu-id="6cc14-114">The database has been left offline.</span></span> <span data-ttu-id="6cc14-115">Vedere l'argomento MSSQL_ENG003165 della documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6cc14-115">See the topic MSSQL_ENG003165 in SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6cc14-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="6cc14-116">Explanation</span></span>  
 <span data-ttu-id="6cc14-117">Questo errore viene generato se si verifica un problema durante il ripristino di un backup di un database replicato:</span><span class="sxs-lookup"><span data-stu-id="6cc14-117">This error is raised if a problem occurs restoring a backup of a replicated database:</span></span>  
  
-   <span data-ttu-id="6cc14-118">Se il ripristino del backup avviene nello stesso database e nello stesso server sui quali è stato eseguito, l'errore indica che non è stato possibile ripristinare correttamente le impostazioni della replica.</span><span class="sxs-lookup"><span data-stu-id="6cc14-118">If the backup is being restored to the same database and server on which it was taken, the error indicates that replication settings could not be restored properly.</span></span>  
  
-   <span data-ttu-id="6cc14-119">Se invece il backup viene ripristinato in un database o in un server diverso, l'errore indica che non è stato possibile rimuovere correttamente le impostazioni della replica (per impostazione predefinita, queste ultime vengono rimosse se il database o il server è diverso).</span><span class="sxs-lookup"><span data-stu-id="6cc14-119">If the backup is being restored to a different database or server, the error indicates that replication settings could not be removed properly (by default, replication settings are removed if the database or server is different).</span></span>  
  
 <span data-ttu-id="6cc14-120">È probabile che l'errore sia il risultato di una mancata corrispondenza tra lo stato del database ripristinato e uno o più database di sistema contenenti metadati di replica, come il database **msdb**, **master**o il database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6cc14-120">The error is probably the result of a mismatch between the state of the restored database and one or more system databases that contain replication metadata: **msdb**, **master**, or the distribution database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6cc14-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6cc14-121">User Action</span></span>  
 <span data-ttu-id="6cc14-122">Per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="6cc14-122">To resolve this issue:</span></span>  
  
1.  <span data-ttu-id="6cc14-123">Eseguire l'istruzione ALTER DATABASE per portare il database online. Ad esempio: `ALTER DATABASE AdventureWorks SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="6cc14-123">Execute ALTER DATABASE to bring the database online; for example: `ALTER DATABASE AdventureWorks SET ONLINE`.</span></span> <span data-ttu-id="6cc14-124">Per altre informazioni, vedere [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6cc14-124">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span> <span data-ttu-id="6cc14-125">Per mantenere le impostazioni di replica, andare al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="6cc14-125">If you want to preserve replication settings, go to step 2.</span></span> <span data-ttu-id="6cc14-126">In caso contrario, andare al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="6cc14-126">If not, go to step 3.</span></span>  
  
2.  <span data-ttu-id="6cc14-127">Eseguire [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6cc14-127">Execute [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span></span> <span data-ttu-id="6cc14-128">Se l'esecuzione di questa stored procedure riesce, il ripristino sarà completo.</span><span class="sxs-lookup"><span data-stu-id="6cc14-128">If this stored procedure executes successfully, the restore is complete.</span></span> <span data-ttu-id="6cc14-129">In caso contrario, andare al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="6cc14-129">If it does not execute successfully, go to step 3.</span></span>  
  
3.  <span data-ttu-id="6cc14-130">Eseguire [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) per rimuovere tutte le impostazioni della replica.</span><span class="sxs-lookup"><span data-stu-id="6cc14-130">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove all replication settings.</span></span>  
  
     <span data-ttu-id="6cc14-131">Se necessario, riconfigurare la replica.</span><span class="sxs-lookup"><span data-stu-id="6cc14-131">Reconfigure replication if necessary.</span></span> <span data-ttu-id="6cc14-132">Se sono stati creati gli script della topologia di replica, come consigliato, utilizzare tali script per riconfigurare la topologia.</span><span class="sxs-lookup"><span data-stu-id="6cc14-132">If you have scripted the replication topology as recommended, use scripts to reconfigure the topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cc14-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cc14-133">See Also</span></span>  
 <span data-ttu-id="6cc14-134">[Backup e ripristino di database SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="6cc14-134">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="6cc14-135">[Backup e ripristino di database replicati](administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="6cc14-135">[Back Up and Restore Replicated Databases](administration/back-up-and-restore-replicated-databases.md) </span></span>  
 [<span data-ttu-id="6cc14-136">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="6cc14-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
