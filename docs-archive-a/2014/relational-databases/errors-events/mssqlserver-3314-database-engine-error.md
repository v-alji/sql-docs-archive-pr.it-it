---
title: MSSQLSERVER_3314 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3314 (Database Engine error)
ms.assetid: f3a5ca6a-b502-4cab-b3b1-4bc753763fa9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3b891b438f71d70f5dd62174eae2c5a07d29a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636117"
---
# <a name="mssqlserver_3314"></a><span data-ttu-id="b6a4b-102">MSSQLSERVER_3314</span><span class="sxs-lookup"><span data-stu-id="b6a4b-102">MSSQLSERVER_3314</span></span>
    
## <a name="details"></a><span data-ttu-id="b6a4b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b6a4b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6a4b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b6a4b-104">Product Name</span></span>|<span data-ttu-id="b6a4b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b6a4b-105">SQL Server</span></span>|  
|<span data-ttu-id="b6a4b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b6a4b-106">Event ID</span></span>|<span data-ttu-id="b6a4b-107">3314</span><span class="sxs-lookup"><span data-stu-id="b6a4b-107">3314</span></span>|  
|<span data-ttu-id="b6a4b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b6a4b-108">Event Source</span></span>|<span data-ttu-id="b6a4b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b6a4b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b6a4b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b6a4b-110">Component</span></span>|<span data-ttu-id="b6a4b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b6a4b-111">SQLEngine</span></span>|  
|<span data-ttu-id="b6a4b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b6a4b-112">Symbolic Name</span></span>|<span data-ttu-id="b6a4b-113">ERR_LOG_RID2</span><span class="sxs-lookup"><span data-stu-id="b6a4b-113">ERR_LOG_RID2</span></span>|  
|<span data-ttu-id="b6a4b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b6a4b-114">Message Text</span></span>|<span data-ttu-id="b6a4b-115">Durante il rollback di un'operazione registrata nel database '%.\*ls' si è verificato un errore in corrispondenza dell'ID del record di log ID %S_LSN.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-115">During undoing of a logged operation in database '%.\*ls', an error occurred at log record ID %S_LSN.</span></span> <span data-ttu-id="b6a4b-116">L'errore specifico viene in genere registrato in precedenza come errore nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-116">Typically, the specific failure is logged previously as an error in the Windows Event Log service.</span></span> <span data-ttu-id="b6a4b-117">Ripristinare il database o il file da un backup oppure correggere il database.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-117">Restore the database or file from a backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b6a4b-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b6a4b-118">Explanation</span></span>  
 <span data-ttu-id="b6a4b-119">Si tratta di un errore di rollup per il recupero dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-119">This is a rollup error for undo recovery.</span></span> <span data-ttu-id="b6a4b-120">Tale errore ha determinato l'impostazione del database sullo stato SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="b6a4b-121">Il filegroup primario, e probabilmente altri filegroup, sono sospetti e possono essere danneggiati.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="b6a4b-122">Non è possibile recuperare il database durante l'avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , pertanto non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="b6a4b-123">Per risolvere il problema, è necessario l'intervento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="b6a4b-124">Se questo errore si verifica per **tempdb**, l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene arrestata.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b6a4b-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b6a4b-125">User Action</span></span>  
 <span data-ttu-id="b6a4b-126">Questo errore può essere causato da una condizione temporanea già presente nel sistema durante un determinato tentativo di avvio dell'istanza del server o di recupero di un database.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="b6a4b-127">Può inoltre essere causato da un errore permanente che si verifica ogni volta che si tenta di avviare il database.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="b6a4b-128">Per informazioni sulla causa, esaminare il registro eventi di Windows per cercare un errore precedente che indichi l'errore specifico.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="b6a4b-129">Per informazioni sulla causa di questa occorrenza dell'errore 3314, esaminare il registro eventi di Windows per cercare un errore precedente che indichi l'errore specifico.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-129">For information about the cause of this occurrence of error 3314, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="b6a4b-130">L'azione appropriata dell'utente varia a seconda che le informazioni nel registro eventi di Windows indichino che l'errore [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato causato da una condizione temporanea o da un errore permanente.</span><span class="sxs-lookup"><span data-stu-id="b6a4b-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="b6a4b-131">Per informazioni sulle azioni dell'utente per la risoluzione dell'errore 3314, vedere la documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6a4b-131">For information about the user actions for troubleshooting error 3314, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a4b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6a4b-132">See Also</span></span>  
 <span data-ttu-id="b6a4b-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6a4b-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="b6a4b-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6a4b-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="b6a4b-135">[Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="b6a4b-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="b6a4b-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="b6a4b-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="b6a4b-137">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b6a4b-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
