---
title: Modificare il tempo di recupero di riferimento di un database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/13/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: e466419a-d8a4-48f7-8d97-13a903ad6b15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c4331d2ade2819d172189a0de9daddecf3d9f6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627252"
---
# <a name="change-the-target-recovery-time-of-a-database-sql-server"></a><span data-ttu-id="7b368-102">Modificare il tempo di recupero di riferimento di un database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7b368-102">Change the Target Recovery Time of a Database (SQL Server)</span></span>
  <span data-ttu-id="7b368-103">In questo argomento viene illustrato come impostare la modifica del tempo di recupero di riferimento di un database [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b368-103">This topic describes how to set the change the target recovery time of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7b368-104">Per impostazione predefinita, il tempo di recupero di riferimento è 0 e il database utilizza *checkpoint automatici* (controllati dall'opzione server **recovery interval** ).</span><span class="sxs-lookup"><span data-stu-id="7b368-104">By default, the target recovery time is 0, and the database uses *automatic checkpoints* (which are controlled by the **recovery interval** server option).</span></span> <span data-ttu-id="7b368-105">L'impostazione del tempo di recupero di riferimento su un valore maggiore di 0 fa sì che il database utilizzi i *checkpoint indiretti* e stabilisce un limite superiore per il tempo di recupero per il database.</span><span class="sxs-lookup"><span data-stu-id="7b368-105">Setting the target recovery time to greater than 0 causes the database to use the *indirect-checkpoints* and establishes an upper-bound on recovery time for this database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b368-106">Il limite superiore specificato per un determinato database dall'impostazione del tempo di recupero di riferimento può essere superato se una transazione con esecuzione prolungata provoca tempi eccessivi di UNDO.</span><span class="sxs-lookup"><span data-stu-id="7b368-106">The upper-bound that is specified for a given database by its target recovery time setting could be exceeded if a long-running transaction causes excessive UNDO times.</span></span>  
  
-   <span data-ttu-id="7b368-107">**Prima di iniziare:**  [Limitazioni e restrizioni](#Restrictions), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="7b368-107">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="7b368-108">**Per modificare il tempo di recupero di riferimento tramite:**  [SQL Server Management Studio](#SSMSProcedure) o [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="7b368-108">**To change the target recovery time, using:**  [SQL Server Management Studio](#SSMSProcedure) or [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7b368-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7b368-109">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>  
  
> [!CAUTION]  
>  <span data-ttu-id="7b368-110">Un carico di lavoro transazionale online su un database configurato per i checkpoint indiretti potrebbe subire un calo delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7b368-110">An online transactional workload on a database that is configured for indirect checkpoints could experience performance degradation.</span></span> <span data-ttu-id="7b368-111">I checkpoint indiretti assicurano che il numero di pagine dirty è inferiore a una determinata soglia, in modo che il recupero del database viene completato entro il tempo di recupero di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7b368-111">Indirect checkpoints make sure that the number of dirty pages are below a certain threshold so that the database recovery completes within the target recovery time.</span></span> <span data-ttu-id="7b368-112">A differenza dei checkpoint indiretti che usano il numero di pagine dirty, l'opzione di configurazione recovery interval usa il numero di transazioni per determinare il tempo di recupero.</span><span class="sxs-lookup"><span data-stu-id="7b368-112">The recovery interval configuration option uses the number of transactions to determine the recovery time as opposed to indirect checkpoints which makes use of number of dirty pages.</span></span> <span data-ttu-id="7b368-113">Quando i checkpoint indiretti sono abilitati per un database che riceve un numero elevato di operazioni DML, il writer in background può iniziare a scaricare i buffer dirty su disco in modo intensivo per garantire che il tempo necessario per eseguire il recupero non superi il tempo di recupero di riferimento impostato per il database.</span><span class="sxs-lookup"><span data-stu-id="7b368-113">When indirect checkpoints are enabled on a database receiving a large number of DML operations, the background writer can start aggressively flushing dirty buffers to disk to ensure that the time required to perform recovery is within the target recovery time set of the database.</span></span> <span data-ttu-id="7b368-114">Questo può causare in determinati sistemi ulteriore attività di I/O che può comportare un collo di bottiglia delle prestazioni se il sottosistema del disco opera al di sopra o in prossimità della soglia di I/O.</span><span class="sxs-lookup"><span data-stu-id="7b368-114">This can cause additional I/O activity on certain systems which can contribute to a performance bottleneck if the disk subsystem is operating above or nearing the I/O threshold.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7b368-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7b368-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7b368-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7b368-116">Permissions</span></span>  
 <span data-ttu-id="7b368-117">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="7b368-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7b368-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b368-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7b368-119">**Per modificare il tempo di recupero di riferimento**</span><span class="sxs-lookup"><span data-stu-id="7b368-119">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="7b368-120">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="7b368-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and expand that instance.</span></span>  
  
2.  <span data-ttu-id="7b368-121">Fare clic con il pulsante destro del mouse sul database che si desidera modificare e scegliere il comando **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="7b368-121">Right-click the database you want to change, and click the **Properties** command.</span></span>  
  
3.  <span data-ttu-id="7b368-122">Nella finestra di dialogo **Proprietà database** fare clic sulla pagina **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="7b368-122">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="7b368-123">Nel campo **Tempo di recupero di riferimento (secondi)** del pannello **Recupero** specificare il numero di secondi desiderato come limite superiore nel tempo di recupero per il database.</span><span class="sxs-lookup"><span data-stu-id="7b368-123">In the **Recovery** panel, in the **Target Recovery Time (Seconds)** field, specify the number of seconds that you want as the upper-bound on the recovery time for this database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7b368-124">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b368-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="7b368-125">**Per modificare il tempo di recupero di riferimento**</span><span class="sxs-lookup"><span data-stu-id="7b368-125">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="7b368-126">Connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui risiede il database.</span><span class="sxs-lookup"><span data-stu-id="7b368-126">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the database resides.</span></span>  
  
2.  <span data-ttu-id="7b368-127">Usare l'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options), come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7b368-127">Use the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)statement, as follows:</span></span>  
  
     <span data-ttu-id="7b368-128">TARGET_RECOVERY_TIME **=** _target_recovery_time_ { SECONDS | MINUTES }</span><span class="sxs-lookup"><span data-stu-id="7b368-128">TARGET_RECOVERY_TIME **=**_target_recovery_time_ { SECONDS | MINUTES }</span></span>  
  
     <span data-ttu-id="7b368-129">*target_recovery_time*</span><span class="sxs-lookup"><span data-stu-id="7b368-129">*target_recovery_time*</span></span>  
     <span data-ttu-id="7b368-130">Quando è maggiore di 0 (valore predefinito), il valore specifica il limite superiore del tempo di recupero per il database specificato in caso di arresto anomalo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7b368-130">When greater than 0 (the default), specifies the upper-bound on the recovery time for the specified database in the event of a crash.</span></span>  
  
     <span data-ttu-id="7b368-131">SECONDS</span><span class="sxs-lookup"><span data-stu-id="7b368-131">SECONDS</span></span>  
     <span data-ttu-id="7b368-132">Indica che *target_recovery_time* viene espresso come numero di secondi.</span><span class="sxs-lookup"><span data-stu-id="7b368-132">Indicates that *target_recovery_time* is expressed as the number of seconds.</span></span>  
  
     <span data-ttu-id="7b368-133">MINUTES</span><span class="sxs-lookup"><span data-stu-id="7b368-133">MINUTES</span></span>  
     <span data-ttu-id="7b368-134">Indica che *target_recovery_time* viene espresso come numero di minuti.</span><span class="sxs-lookup"><span data-stu-id="7b368-134">Indicates that *target_recovery_time* is expressed as the number of minutes.</span></span>  
  
     <span data-ttu-id="7b368-135">Nell'esempio seguente viene impostato il tempo di recupero di riferimento del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] su `60` .</span><span class="sxs-lookup"><span data-stu-id="7b368-135">The following example sets the target recovery time of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to `60` seconds.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET TARGET_RECOVERY_TIME = 60 SECONDS;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7b368-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b368-136">See Also</span></span>  
 <span data-ttu-id="7b368-137">[Checkpoint di database &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7b368-137">[Database Checkpoints &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span></span>  
 [<span data-ttu-id="7b368-138">Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7b368-138">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
