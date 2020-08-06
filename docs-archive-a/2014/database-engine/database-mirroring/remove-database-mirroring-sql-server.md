---
title: Rimuovere il mirroring del database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- removing database mirroring [SQL Server]
ms.assetid: bbc4d7f7-3bc7-40d6-a822-af195fe7f8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19c1d0449fa1c7434aeaf9c51e3b2dc7bc6b68c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716755"
---
# <a name="remove-database-mirroring-sql-server"></a><span data-ttu-id="467da-102">Rimuovere il mirroring del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="467da-102">Remove Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="467da-103">In questo argomento verrà descritto come rimuovere il mirroring del database da un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="467da-103">This topic describes how to remove database mirroring from a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  <span data-ttu-id="467da-104">Il proprietario del database può arrestare manualmente una sessione di mirroring del database in qualsiasi momento, rimuovendo il mirroring dal database.</span><span class="sxs-lookup"><span data-stu-id="467da-104">At any time, the database owner can manually stop a database mirroring session by removing mirroring from the database.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="467da-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="467da-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="467da-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="467da-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="467da-107">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="467da-107">Permissions</span></span>  
 <span data-ttu-id="467da-108">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="467da-108">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="467da-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="467da-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="467da-110">Per rimuovere il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="467da-110">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="467da-111">Durante una sessione di mirroring del database, connettersi all'istanza del server principale e in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="467da-111">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="467da-112">Espandere **Database**e selezionare il database.</span><span class="sxs-lookup"><span data-stu-id="467da-112">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="467da-113">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Server mirror**.</span><span class="sxs-lookup"><span data-stu-id="467da-113">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="467da-114">Viene visualizzata la pagina **Mirroring** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="467da-114">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="467da-115">Nel riquadro **Selezione pagina** fare clic su **Mirroring**.</span><span class="sxs-lookup"><span data-stu-id="467da-115">In the **Select a Page** pane, click **Mirroring**.</span></span>  
  
5.  <span data-ttu-id="467da-116">Per rimuovere il mirroring, scegliere **Rimuovi mirroring**.</span><span class="sxs-lookup"><span data-stu-id="467da-116">To remove mirroring, click **Remove Mirroring**.</span></span> <span data-ttu-id="467da-117">Verrà richiesta una conferma.</span><span class="sxs-lookup"><span data-stu-id="467da-117">A prompt asks for confirmation.</span></span> <span data-ttu-id="467da-118">Se si fa clic su **Sì**, la sessione verrà arrestata e il mirroring verrà rimosso dal database.</span><span class="sxs-lookup"><span data-stu-id="467da-118">If you click **Yes**, the session is stopped and mirroring is removed from the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="467da-119">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="467da-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="467da-120">Per rimuovere il mirroring del database, utilizzare **Proprietà database**.</span><span class="sxs-lookup"><span data-stu-id="467da-120">To remove database mirroring, use the **Database Properties**.</span></span> <span data-ttu-id="467da-121">Utilizzare la pagina **Mirroring** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="467da-121">use the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="467da-122">Per rimuovere il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="467da-122">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="467da-123">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)] di qualsiasi partner di mirroring.</span><span class="sxs-lookup"><span data-stu-id="467da-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] of either mirroring partner.</span></span>  
  
2.  <span data-ttu-id="467da-124">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="467da-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="467da-125">Eseguire l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="467da-125">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    ALTER DATABASE database_name SET PARTNER OFF  
    ```  
  
     <span data-ttu-id="467da-126">dove *database_name* è il database con mirroring di cui si vuole rimuovere la sessione.</span><span class="sxs-lookup"><span data-stu-id="467da-126">where *database_name* is the mirrored database whose session you want to remove.</span></span>  
  
     <span data-ttu-id="467da-127">Nell'esempio seguente viene rimosso il mirroring del database dal database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="467da-127">The following example removes database mirroring from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER OFF;  
    ```  
  
##  <a name="follow-up-removing-database-mirroring"></a><a name="FollowUp"></a> <span data-ttu-id="467da-128">Completamento: Rimozione del mirroring del database</span><span class="sxs-lookup"><span data-stu-id="467da-128">Follow Up: Removing Database Mirroring</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="467da-129">Per informazioni sull'impatto della rimozione del mirroring del database, vedere [Rimozione del mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="467da-129">For information about the impact of removing mirroring, see [Removing Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="467da-130">**In caso di riavvio del mirroring nel database**</span><span class="sxs-lookup"><span data-stu-id="467da-130">**If you intend to restart mirroring on the database**</span></span>  
  
     <span data-ttu-id="467da-131">Prima di poter riavviare il mirroring è necessario che tutti i backup di log eseguiti nel database principale dopo la rimozione del mirroring vengano applicati al database mirror.</span><span class="sxs-lookup"><span data-stu-id="467da-131">Any log backups taken on the principal database after mirroring was removed must all be applied to the mirror database before you can restart mirroring.</span></span>  
  
-   <span data-ttu-id="467da-132">**In caso di non riavvio del mirroring**</span><span class="sxs-lookup"><span data-stu-id="467da-132">**If you do not intent to restart mirroring**</span></span>  
  
     <span data-ttu-id="467da-133">Facoltativamente, è possibile recuperare il database mirror precedente.</span><span class="sxs-lookup"><span data-stu-id="467da-133">Optionally, you can recover the former mirror database.</span></span> <span data-ttu-id="467da-134">Nell'istanza del server mirror è possibile utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="467da-134">On the server instance that was the mirror server, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    RESTORE DATABASE database_name WITH RECOVERY;  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="467da-135">Se questo database viene recuperato, online saranno disponibili due database divergenti con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="467da-135">If you recover this database, two divergent databases with the same name are online.</span></span> <span data-ttu-id="467da-136">Di conseguenza, è necessario assicurarsi che i client possano accedere soltanto a uno di essi, generalmente al database principale più recente.</span><span class="sxs-lookup"><span data-stu-id="467da-136">Therefore, you need to ensure that clients can access only one of them-typically the most recent principal database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="467da-137">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="467da-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="467da-138">Sospendere o riprendere una sessione di mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="467da-138">Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;</span></span>](pause-or-resume-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="467da-139">Rimuovere il server di controllo del mirroring da una sessione di mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="467da-139">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="467da-140">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="467da-140">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="467da-141">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="467da-141">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="467da-142">Esempio: Configurazione del mirroring del database tramite certificati &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="467da-142">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="467da-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="467da-143">See Also</span></span>  
 <span data-ttu-id="467da-144">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="467da-144">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="467da-145">[Impostazione del mirroring del database &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="467da-145">[Setting Up Database Mirroring &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="467da-146">Gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="467da-146">AlwaysOn Availability Groups (SQL Server)</span></span>](../availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
