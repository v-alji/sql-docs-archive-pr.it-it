---
title: Spostare un database tramite la funzionalità di scollegamento e collegamento (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database attaching [SQL Server]
- moving databases [SQL Server]
- database detaching [SQL Server]
- relocating databases [SQL Server]
- detaching databases [SQL Server]
- attaching databases [SQL Server]
ms.assetid: 6732a431-cdef-4f1e-9262-4ac3b77c275e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 768a70dfe94af6f8d65f7c76fa08d3dff650fe7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637875"
---
# <a name="move-a-database-using-detach-and-attach-transact-sql"></a><span data-ttu-id="57396-102">Spostamento di un database tramite la funzionalità di scollegamento e collegamento (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="57396-102">Move a Database Using Detach and Attach (Transact-SQL)</span></span>
  <span data-ttu-id="57396-103">In questo argomento si illustra come spostare un database scollegato in un'altra posizione e come ricollegarlo alla stessa istanza oppure a un'altra istanza del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57396-103">This topic describes how to move a detached database to another location and re-attach it to the same or a different server instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="57396-104">Tuttavia, è consigliabile spostare i database utilizzando la procedura di rilocazione pianificata ALTER DATABASE anziché la funzionalità di scollegamento e collegamento.</span><span class="sxs-lookup"><span data-stu-id="57396-104">However, we recommend that you move databases by using the ALTER DATABASE planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="57396-105">Per altre informazioni, vedere [Spostare database utente](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="57396-105">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="57396-106">È consigliabile evitare di collegare o ripristinare database provenienti da origini sconosciute o non attendibili.</span><span class="sxs-lookup"><span data-stu-id="57396-106">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="57396-107">Tali database possono contenere codice dannoso che potrebbe eseguire codice [!INCLUDE[tsql](../../includes/tsql-md.md)] indesiderato o causare errori modificando lo schema o la struttura fisica di database.</span><span class="sxs-lookup"><span data-stu-id="57396-107">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="57396-108">Prima di utilizzare un database da un'origine sconosciuta o non attendibile, eseguire [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sul database in un server non di produzione ed esaminare il codice contenuto nel database, ad esempio le stored procedure o altro codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="57396-108">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="57396-109">Procedura</span><span class="sxs-lookup"><span data-stu-id="57396-109">Procedure</span></span>  
  
#### <a name="to-move-a-database-by-using-detach-and-attach"></a><span data-ttu-id="57396-110">Per spostare un database utilizzando la funzionalità di scollegamento e collegamento</span><span class="sxs-lookup"><span data-stu-id="57396-110">To move a database by using detach and attach</span></span>  
  
1.  <span data-ttu-id="57396-111">Scollegare il database.</span><span class="sxs-lookup"><span data-stu-id="57396-111">Detach the database.</span></span> <span data-ttu-id="57396-112">Per altre informazioni, vedere [Scollegare un database](detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="57396-112">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
2.  <span data-ttu-id="57396-113">In Esplora risorse o in una finestra del prompt dei comandi di Windows spostare nella nuova posizione il file o i file del database scollegato e i relativi file di log.</span><span class="sxs-lookup"><span data-stu-id="57396-113">In a Windows Explorer or Windows Command Prompt window, move the detached database file or files and log file or files to the new location.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57396-114">Per spostare un database composto da un singolo file è possibile utilizzare la posta elettronica se le dimensioni del file sono sufficientemente ridotte.</span><span class="sxs-lookup"><span data-stu-id="57396-114">To move a single-file database, you can use email if the file size is small enough for email to accommodate.</span></span>  
  
     <span data-ttu-id="57396-115">È consigliabile spostare i file di log anche se si prevede di crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="57396-115">You should move the log files even if you intend to create new log files.</span></span> <span data-ttu-id="57396-116">In alcuni casi, per il ricollegamento di un database sono necessari i file di log esistenti.</span><span class="sxs-lookup"><span data-stu-id="57396-116">In some cases, reattaching a database requires its existing log files.</span></span> <span data-ttu-id="57396-117">Mantenere pertanto sempre tutti i file di log scollegati fino a quando il database non è stato collegato senza di essi.</span><span class="sxs-lookup"><span data-stu-id="57396-117">Therefore, always keep all the detached log files until the database has been successfully attached without them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57396-118">Se si tenta di collegare il database senza specificare il file di log, verrà eseguita una ricerca di tale file nella relativa posizione originale.</span><span class="sxs-lookup"><span data-stu-id="57396-118">If you try to attach the database without specifying the log file, the attach operation will look for the log file in its original location.</span></span> <span data-ttu-id="57396-119">Se nella posizione originale esiste ancora una copia del log, verrà collegata tale copia.</span><span class="sxs-lookup"><span data-stu-id="57396-119">If a copy of the log still exists in the original location, that copy is attached.</span></span> <span data-ttu-id="57396-120">Per evitare di utilizzare il file di log originale, specificare il percorso del nuovo file di log oppure rimuovere la copia originale del file di log dopo averlo copiato nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="57396-120">To avoid using the original log file, either specify the path of the new log file or remove the original copy of the log file (after copying it to the new location).</span></span>  
  
3.  <span data-ttu-id="57396-121">Collegare i file copiati.</span><span class="sxs-lookup"><span data-stu-id="57396-121">Attach the copied files.</span></span> <span data-ttu-id="57396-122">Per altre informazioni, vedere [Attach a Database](attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="57396-122">For more information, see [Attach a Database](attach-a-database.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57396-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="57396-123">Example</span></span>  
 <span data-ttu-id="57396-124">Nell'esempio seguente viene creata una copia delle [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] istruzioni che vengono eseguite in una finestra dell'editor di query connessa all'istanza del server a cui è collegato.</span><span class="sxs-lookup"><span data-stu-id="57396-124">The following example creates a copy of the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements are executed in a Query Editor window that is connected to the server instance to which is attached.</span></span>  
  
1.  <span data-ttu-id="57396-125">Scollegare le [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] istruzioni:</span><span class="sxs-lookup"><span data-stu-id="57396-125">Detach the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sp_detach_db @dbname = N'AdventureWorks2012';  
    GO  
    ```  
  
2.  <span data-ttu-id="57396-126">Copiare i file di database (AdventureWorks208R2_Data.mdf e AdventureWorks208R2_log) rispettivamente in: C:\MySQLServer\AdventureWorks208R2_Data.mdf e C:\MySQLServer\AdventureWorks208R2_Log.ldf, utilizzando il metodo desiderato.</span><span class="sxs-lookup"><span data-stu-id="57396-126">Using the method of your choice, copy the database files (AdventureWorks208R2_Data.mdf and AdventureWorks208R2_log) to: C:\MySQLServer\AdventureWorks208R2_Data.mdf and C:\MySQLServer\AdventureWorks208R2_Log.ldf, respectively.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="57396-127">Nel caso di un database di produzione, posizionare su dischi separati il database e il log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="57396-127">For a production database, place the database and transaction log on separate disks.</span></span>  
  
     <span data-ttu-id="57396-128">Per copiare i file in rete su un disco di un computer remoto, utilizzare il nome UNC (Universal Naming Convention) della posizione remota.</span><span class="sxs-lookup"><span data-stu-id="57396-128">To copy files over the network to a disk on a remote computer, use the universal naming convention (UNC) name of the remote location.</span></span> <span data-ttu-id="57396-129">Il formato di un nome UNC è **\\\\** _Servername_ **\\** _Sharename_ **\\** _Path_ **\\** _Filename_.</span><span class="sxs-lookup"><span data-stu-id="57396-129">A UNC name takes the form **\\\\**_Servername_**\\**_Sharename_**\\**_Path_**\\**_Filename_.</span></span> <span data-ttu-id="57396-130">Come per la scrittura di file nel disco rigido locale, è necessario che l'account utente utilizzato dall'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]disponga delle autorizzazioni appropriate per la lettura o la scrittura di un file nel disco remoto.</span><span class="sxs-lookup"><span data-stu-id="57396-130">As with writing files to the local hard disk, the appropriate permissions that are required to read or write to a file on the remote disk must be granted to the user account used by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="57396-131">Collegare il database spostato e, facoltativamente, collegare il relativo log tramite l'esecuzione delle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="57396-131">Attach the moved database and, optionally, its log by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Data.mdf'),  
        (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Log.ldf')  
        FOR ATTACH;  
    GO  
    ```  
  
     <span data-ttu-id="57396-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]un database appena collegato non è immediatamente visibile in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="57396-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], a newly attached database is not immediately visible in Object Explorer.</span></span> <span data-ttu-id="57396-133">Per visualizzarlo, in Esplora oggetti scegliere **Aggiorna** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="57396-133">To view the database, in Object Explorer, click **View,** and then **Refresh**.</span></span> <span data-ttu-id="57396-134">Quando si espande il nodo **Database** in Esplora oggetti, il database appena collegato viene visualizzato nell'elenco dei database.</span><span class="sxs-lookup"><span data-stu-id="57396-134">When the **Databases** node is expanded in Object Explorer, the newly attached database now appears in the list of databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57396-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57396-135">See Also</span></span>  
 [<span data-ttu-id="57396-136">Collegamento e scollegamento di un database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="57396-136">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
