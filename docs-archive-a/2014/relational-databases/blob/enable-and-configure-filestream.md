---
title: Abilitare e configurare FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], enabling
ms.assetid: 78737e19-c65b-48d9-8fa9-aa6f1e1bce73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f6c0e505bd32636d045519b36e439bc21c7079d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623353"
---
# <a name="enable-and-configure-filestream"></a><span data-ttu-id="e2924-102">Abilitare e configurare FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="e2924-102">Enable and Configure FILESTREAM</span></span>
  <span data-ttu-id="e2924-103">Prima di iniziare a utilizzare FILESTREAM, è necessario abilitarlo nell'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2924-103">Before you can start to use FILESTREAM, you must enable FILESTREAM on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="e2924-104">In questo argomento viene descritto come abilitare FILESTREAM utilizzando Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e2924-104">This topic describes how to enable FILESTREAM by using SQL Server Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2924-105">Non è possibile abilitare FILESTREAM in una versione a 32 bit di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eseguita in un sistema operativo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="e2924-105">You cannot enable FILESTREAM on a 32-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on a 64-bit operating system.</span></span>  
  
##  <a name="enabling-filestream"></a><a name="enabling"></a> <span data-ttu-id="e2924-106">Abilitazione di FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="e2924-106">Enabling FILESTREAM</span></span>  
  
#### <a name="to-enable-and-change-filestream-settings"></a><span data-ttu-id="e2924-107">Per abilitare e modificare le impostazioni FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="e2924-107">To enable and change FILESTREAM settings</span></span>  
  
1.  <span data-ttu-id="e2924-108">Fare clic sul menu **Start** , scegliere **Tutti i programmi**, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], **Strumenti di configurazione**e quindi **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e2924-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="e2924-109">Nell'elenco dei servizi fare clic con il pulsante destro del mouse su **Servizi di SQL Server**e quindi scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="e2924-109">In the list of services, right-click **SQL Server Services**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="e2924-110">Nello snap-in **Gestione configurazione SQL Server** trovare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui si vuole abilitare FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e2924-110">In the **SQL Server Configuration Manager** snap-in, locate the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to enable FILESTREAM.</span></span>  
  
4.  <span data-ttu-id="e2924-111">Fare clic con il pulsante destro sull'istanza e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e2924-111">Right-click the instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="e2924-112">Nella finestra di dialogo delle **proprietà di SQL Server** fare clic sulla scheda **FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="e2924-112">In the **SQL Server Properties** dialog box, click the **FILESTREAM** tab.</span></span>  
  
6.  <span data-ttu-id="e2924-113">Selezionare la casella di controllo **Abilita FILESTREAM per l'accesso Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="e2924-113">Select the **Enable FILESTREAM for Transact-SQL access** check box.</span></span>  
  
7.  <span data-ttu-id="e2924-114">Se si vogliono leggere e scrivere dati FILESTREAM da Windows, fare clic su **Abilita FILESTREAM per l'accesso tramite il flusso di I/O dei file**.</span><span class="sxs-lookup"><span data-stu-id="e2924-114">If you want to read and write FILESTREAM data from Windows, click **Enable FILESTREAM for file I/O streaming access**.</span></span> <span data-ttu-id="e2924-115">Immettere il nome della condivisione di Windows nella casella **Nome condivisione di Windows** .</span><span class="sxs-lookup"><span data-stu-id="e2924-115">Enter the name of the Windows share in the **Windows Share Name** box.</span></span>  
  
8.  <span data-ttu-id="e2924-116">Se ai dati FILESTREAM archiviati in tale condivisione devono accedere client remoti, selezionare **Consenti ai client remoti l'accesso tramite flusso ai dati FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="e2924-116">If remote clients must access the FILESTREAM data that is stored on this share, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span>  
  
9. <span data-ttu-id="e2924-117">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="e2924-117">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="e2924-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]fare clic su **Nuova query** per visualizzare l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="e2924-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
11. <span data-ttu-id="e2924-119">Nell'editor di query immettere il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="e2924-119">In Query Editor, enter the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
    ```sql  
    EXEC sp_configure filestream_access_level, 2  
    RECONFIGURE  
    ```  
  
12. <span data-ttu-id="e2924-120">Fare clic su **Execute**.</span><span class="sxs-lookup"><span data-stu-id="e2924-120">Click **Execute**.</span></span>  
  
13. <span data-ttu-id="e2924-121">Riavviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2924-121">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  

  
##  <a name="best-practices"></a><a name="best"></a> <span data-ttu-id="e2924-122">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="e2924-122">Best Practices</span></span>  
  
###  <a name="physical-configuration-and-maintenance"></a><a name="config"></a><span data-ttu-id="e2924-123">Configurazione fisica e manutenzione</span><span class="sxs-lookup"><span data-stu-id="e2924-123">Physical Configuration and Maintenance</span></span>  
 <span data-ttu-id="e2924-124">Quando si configurano i volumi di archiviazione FILESTREAM, tenere presenti le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2924-124">When you set up FILESTREAM storage volumes, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="e2924-125">Disabilitare i nomi di file brevi nei sistemi FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e2924-125">Turn off short file names on FILESTREAM computer systems.</span></span> <span data-ttu-id="e2924-126">La creazione di nomi di file brevi richiede tempi sensibilmente più lunghi.</span><span class="sxs-lookup"><span data-stu-id="e2924-126">Short file names take significantly longer to create.</span></span> <span data-ttu-id="e2924-127">Per disabilitare i nomi di file brevi, usare l'utilità **fsutil** di Windows.</span><span class="sxs-lookup"><span data-stu-id="e2924-127">To disable short file names, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="e2924-128">Deframmentare regolarmente i sistemi FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e2924-128">Regularly defragment FILESTREAM computer systems.</span></span>  
  
-   <span data-ttu-id="e2924-129">Utilizzare cluster NTFS da 64 KB.</span><span class="sxs-lookup"><span data-stu-id="e2924-129">Use 64-KB NTFS clusters.</span></span> <span data-ttu-id="e2924-130">I volumi compressi devono essere impostati su cluster NTFS da 4 KB.</span><span class="sxs-lookup"><span data-stu-id="e2924-130">Compressed volumes must be set to 4-KB NTFS clusters.</span></span>  
  
-   <span data-ttu-id="e2924-131">Disabilitare l'indicizzazione nei volumi FILESTREAM e impostare **disablelastaccess** . Per impostare **disablelastaccess**, usare l'utilità **fsutil** di Windows.</span><span class="sxs-lookup"><span data-stu-id="e2924-131">Disable indexing on FILESTREAM volumes and set **disablelastaccess** To set **disablelastaccess**, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="e2924-132">Disabilitare l'analisi per la ricerca di virus nei volumi FILESTREAM quando non è non necessaria.</span><span class="sxs-lookup"><span data-stu-id="e2924-132">Disable antivirus scanning of FILESTREAM volumes when it is not unnecessary.</span></span> <span data-ttu-id="e2924-133">Se tale analisi è necessaria, evitare di impostare criteri per l'eliminazione automatica dei file infetti.</span><span class="sxs-lookup"><span data-stu-id="e2924-133">If antivirus scanning is necessary, avoid setting policies that will automatically delete offending files.</span></span>  
  
-   <span data-ttu-id="e2924-134">Configurare e ottimizzare il livello RAID per la tolleranza di errore e le prestazioni richieste da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2924-134">Set up and tune the RAID level for fault tolerance and the performance that is required by an application.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="e2924-135">Livello RAID</span><span class="sxs-lookup"><span data-stu-id="e2924-135">RAID level</span></span>|<span data-ttu-id="e2924-136">Prestazioni di scrittura</span><span class="sxs-lookup"><span data-stu-id="e2924-136">Write performance</span></span>|<span data-ttu-id="e2924-137">Prestazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="e2924-137">Read performance</span></span>|<span data-ttu-id="e2924-138">Tolleranza di errore</span><span class="sxs-lookup"><span data-stu-id="e2924-138">Fault tolerance</span></span>|<span data-ttu-id="e2924-139">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e2924-139">Remarks</span></span>|  
|<span data-ttu-id="e2924-140">RAID 5</span><span class="sxs-lookup"><span data-stu-id="e2924-140">RAID 5</span></span>|<span data-ttu-id="e2924-141">Normale</span><span class="sxs-lookup"><span data-stu-id="e2924-141">Normal</span></span>|<span data-ttu-id="e2924-142">Normale</span><span class="sxs-lookup"><span data-stu-id="e2924-142">Normal</span></span>|<span data-ttu-id="e2924-143">Eccellenti</span><span class="sxs-lookup"><span data-stu-id="e2924-143">Excellent</span></span>|<span data-ttu-id="e2924-144">Le prestazioni sono più elevate rispetto all'utilizzo di un unico disco o di JBOD e meno elevate rispetto all'utilizzo di RAID 0 o RAID 5 con striping.</span><span class="sxs-lookup"><span data-stu-id="e2924-144">Performance is better than one disk or JBOD; and less than RAID 0 or RAID 5 with striping.</span></span>|  
|<span data-ttu-id="e2924-145">RAID 0</span><span class="sxs-lookup"><span data-stu-id="e2924-145">RAID 0</span></span>|<span data-ttu-id="e2924-146">Eccellenti</span><span class="sxs-lookup"><span data-stu-id="e2924-146">Excellent</span></span>|<span data-ttu-id="e2924-147">Eccellenti</span><span class="sxs-lookup"><span data-stu-id="e2924-147">Excellent</span></span>|<span data-ttu-id="e2924-148">nessuno</span><span class="sxs-lookup"><span data-stu-id="e2924-148">None</span></span>||  
|<span data-ttu-id="e2924-149">RAID 5 + striping</span><span class="sxs-lookup"><span data-stu-id="e2924-149">RAID 5 + stripping</span></span>|<span data-ttu-id="e2924-150">Eccellenti</span><span class="sxs-lookup"><span data-stu-id="e2924-150">Excellent</span></span>|<span data-ttu-id="e2924-151">Eccellenti</span><span class="sxs-lookup"><span data-stu-id="e2924-151">Excellent</span></span>|<span data-ttu-id="e2924-152">Eccellenti</span><span class="sxs-lookup"><span data-stu-id="e2924-152">Excellent</span></span>|<span data-ttu-id="e2924-153">Opzione più costosa.</span><span class="sxs-lookup"><span data-stu-id="e2924-153">Most expensive option.</span></span>|  
  

  
###  <a name="physical-database-design"></a><a name="database"></a><span data-ttu-id="e2924-154">Progettazione fisica di database</span><span class="sxs-lookup"><span data-stu-id="e2924-154">Physical Database Design</span></span>  
 <span data-ttu-id="e2924-155">Quando si progetta un database FILESTREAM, tenere presenti le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2924-155">When you design a FILESTREAM database, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="e2924-156">Le colonne FILESTREAM devono essere associate a una `uniqueidentifier` colonna ROWGUID corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e2924-156">FILESTREAM columns must be accompanied by a corresponding `uniqueidentifier`ROWGUID column.</span></span> <span data-ttu-id="e2924-157">Questi tipi di tabelle devono inoltre essere associati a un indice univoco.</span><span class="sxs-lookup"><span data-stu-id="e2924-157">These kinds of tables must also be accompanied by a unique index.</span></span> <span data-ttu-id="e2924-158">Solitamente questo indice non è cluster.</span><span class="sxs-lookup"><span data-stu-id="e2924-158">Typically this index is not a clustered index.</span></span> <span data-ttu-id="e2924-159">Se la logica di business dei database richiede un indice cluster, è necessario assicurarsi che i valori archiviati nell'indice non siano casuali.</span><span class="sxs-lookup"><span data-stu-id="e2924-159">If the databases business logic requires a clustered index, you have to make sure that the values stored in the index are not random.</span></span> <span data-ttu-id="e2924-160">In caso contrario, l'indice verrà riordinato ogni volta che viene aggiunta o rimossa una riga dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="e2924-160">Random values will cause the index to be reordered every time that a row is added or removed from the table.</span></span>  
  
-   <span data-ttu-id="e2924-161">Ai fini delle prestazioni, i contenitori e i filegroup FILESTREAM dovrebbero risiedere in volumi anziché nel sistema operativo, nel database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , nel log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o nel file di paging.</span><span class="sxs-lookup"><span data-stu-id="e2924-161">For performance reasons, FILESTREAM filegroups and containers should reside on volumes other than the operating system, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log, tempdb, or paging file.</span></span>  
  
-   <span data-ttu-id="e2924-162">La gestione dello spazio e i criteri non sono supportati direttamente da FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e2924-162">Space management and policies are not directly supported by FILESTREAM.</span></span> <span data-ttu-id="e2924-163">È tuttavia possibile gestire lo spazio e applicare criteri in modo indiretto assegnando ogni filegroup FILESTREAM a un volume distinto e utilizzando le funzionalità di gestione di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="e2924-163">However, you can manage space and apply policies indirectly by assigning each FILESTREAM filegroup to a separate volume and using the volume's management features.</span></span>  
  
  
