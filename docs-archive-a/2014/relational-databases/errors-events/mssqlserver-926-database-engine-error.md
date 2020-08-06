---
title: MSSQLSERVER_926 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 926 (Database Engine error)
ms.assetid: 57e01668-883b-4be4-84a8-a111caaf0486
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae6796c9f4869d45223ab1283a68fc2bfe78aa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627746"
---
# <a name="mssqlserver_926"></a><span data-ttu-id="07e92-102">MSSQLSERVER_926</span><span class="sxs-lookup"><span data-stu-id="07e92-102">MSSQLSERVER_926</span></span>
    
## <a name="details"></a><span data-ttu-id="07e92-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="07e92-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07e92-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="07e92-104">Product Name</span></span>|<span data-ttu-id="07e92-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="07e92-105">SQL Server</span></span>|  
|<span data-ttu-id="07e92-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="07e92-106">Event ID</span></span>|<span data-ttu-id="07e92-107">926</span><span class="sxs-lookup"><span data-stu-id="07e92-107">926</span></span>|  
|<span data-ttu-id="07e92-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="07e92-108">Event Source</span></span>|<span data-ttu-id="07e92-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="07e92-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="07e92-110">Componente</span><span class="sxs-lookup"><span data-stu-id="07e92-110">Component</span></span>|<span data-ttu-id="07e92-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="07e92-111">SQLEngine</span></span>|  
|<span data-ttu-id="07e92-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="07e92-112">Symbolic Name</span></span>|<span data-ttu-id="07e92-113">DB_SUSPECT</span><span class="sxs-lookup"><span data-stu-id="07e92-113">DB_SUSPECT</span></span>|  
|<span data-ttu-id="07e92-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="07e92-114">Message Text</span></span>|<span data-ttu-id="07e92-115">Impossibile aprire il database '%.\*ls'</span><span class="sxs-lookup"><span data-stu-id="07e92-115">Database '%.\*ls' cannot be opened.</span></span> <span data-ttu-id="07e92-116">perché durante il processo di recupero è stato contrassegnato come SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="07e92-116">It has been marked SUSPECT by recovery.</span></span> <span data-ttu-id="07e92-117">Per ulteriori informazioni, vedere il registro errori di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07e92-117">See the SQL Server errorlog for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07e92-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="07e92-118">Explanation</span></span>  
 <span data-ttu-id="07e92-119">Il database è contrassegnato come sospetto a causa dell'esito negativo del processo di recupero che consente di impostare il database in uno stato consistente a livello di transazioni.</span><span class="sxs-lookup"><span data-stu-id="07e92-119">The database is marked as suspect because it failed the recovery process that brings a database to a consistent transactional state.</span></span> <span data-ttu-id="07e92-120">Questo tipo di errore può verificarsi durante le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07e92-120">This can occur during the following operations:</span></span>  
  
-   <span data-ttu-id="07e92-121">Avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07e92-121">Starting up an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="07e92-122">Collegamento di un database.</span><span class="sxs-lookup"><span data-stu-id="07e92-122">Attaching a database.</span></span>  
  
-   <span data-ttu-id="07e92-123">Utilizzo delle procedure RESTORE DATABASE o RESTORE LOG.</span><span class="sxs-lookup"><span data-stu-id="07e92-123">Using the RESTORE database or RESTORE LOG procedures.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07e92-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="07e92-124">User Action</span></span>  
 <span data-ttu-id="07e92-125">Esaminare il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per individuare la causa dell'errore.</span><span class="sxs-lookup"><span data-stu-id="07e92-125">Inspect the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and determine the cause of the error.</span></span> <span data-ttu-id="07e92-126">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato riavviato dopo il recupero non riuscito, esaminare i log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedenti per individuare le cause del problema.</span><span class="sxs-lookup"><span data-stu-id="07e92-126">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been restarted since the failed recovery, look at previous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs to see the reason why recovery failed.</span></span>  
  
 <span data-ttu-id="07e92-127">Se il recupero non è riuscito a causa di un errore di I/O persistente, una pagina incompleta o un altro possibile errore hardware, risolvere il problema hardware sottostante e ripristinare il database utilizzando un backup.</span><span class="sxs-lookup"><span data-stu-id="07e92-127">If the recovery failed because of a persistent I/O error, a torn page, or other possible hardware problem, resolve the underlying hardware problem and restore the database by using a backup.</span></span> <span data-ttu-id="07e92-128">Se non sono disponibili backup, valutare la possibilità di utilizzare le opzioni DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="07e92-128">If no backups are available, consider the repair options of DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="07e92-129">Se non è possibile risolvere il problema, rivolgersi al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="07e92-129">If you are unable to resolve this problem, contact your primary support provider.</span></span> <span data-ttu-id="07e92-130">Tenere a disposizione il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per eventuali verifiche.</span><span class="sxs-lookup"><span data-stu-id="07e92-130">Have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log available for review.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e92-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07e92-131">See Also</span></span>  
 <span data-ttu-id="07e92-132">[Backup e ripristino di database SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="07e92-132">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="07e92-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="07e92-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="07e92-134">[sys.sysdatabase &#40;&#41;Transact-SQL](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="07e92-134">[sys.sysdatabases &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span></span>  
 [<span data-ttu-id="07e92-135">Collegamento e scollegamento di un database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="07e92-135">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/database-detach-and-attach-sql-server.md)  
  
  
