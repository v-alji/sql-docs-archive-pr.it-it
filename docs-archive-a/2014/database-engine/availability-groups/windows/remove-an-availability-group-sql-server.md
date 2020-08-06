---
title: Rimuovere un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.deleteag.f1
helpviewer_keywords:
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], dropping
ms.assetid: 4b7f7f62-43a3-49db-a72e-22d4d7c2ddbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c17b7d5b362d8b4030d66ebf7ba0e425495410e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626304"
---
# <a name="remove-an-availability-group-sql-server"></a><span data-ttu-id="2d500-102">Rimuovere un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2d500-102">Remove an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="2d500-103">In questo argomento si illustra come eliminare (rimuovere) un gruppo di disponibilità AlwaysOn utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d500-103">This topic describes how to delete (drop) an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2d500-104">Se un'istanza del server che ospita una delle repliche di disponibilità è offline quando si elimina un gruppo di disponibilità, la replica di disponibilità locale verrà eliminata dall'istanza del server quando torna online.</span><span class="sxs-lookup"><span data-stu-id="2d500-104">If a server instance that hosts one of the availability replicas is offline when you delete an availability group, after coming online, the server instance will drop the local availability replica.</span></span> <span data-ttu-id="2d500-105">La rimozione di un gruppo di disponibilità comporta l'eliminazione di qualsiasi listener del gruppo di disponibilità associato.</span><span class="sxs-lookup"><span data-stu-id="2d500-105">Dropping an availability group deletes any associated availability group listener.</span></span>  
  
 <span data-ttu-id="2d500-106">Si noti che, se necessario, è possibile rimuovere un gruppo di disponibilità da qualsiasi nodo WSFC (Windows Server Failover Clustering) in cui siano disponibili le credenziali di sicurezza corrette per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2d500-106">Note that, if necessary, you can drop an availability group from any Windows Server Failover Clustering (WSFC) node that possesses the correct security credentials for the availability group.</span></span> <span data-ttu-id="2d500-107">In questo modo, è possibile eliminare un gruppo di disponibilità quando non rimane nessuna delle relative repliche di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2d500-107">This enables you to delete an availability group when none of its availability replicas remain.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2d500-108">Se possibile, rimuovere il gruppo di disponibilità solo se connesso all'istanza del server in cui è ospitata la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="2d500-108">If possible, remove the availability group only while connected to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="2d500-109">Se il gruppo di disponibilità viene rimosso dalla replica primaria, sono consentite modifiche nei database primari precedenti (senza protezione a disponibilità elevata).</span><span class="sxs-lookup"><span data-stu-id="2d500-109">When the availability group is dropped from the primary replica, changes are allowed in the former primary databases (without high availability protection).</span></span> <span data-ttu-id="2d500-110">Eliminando un gruppo di disponibilità da una replica secondaria, la replica primaria viene mantenuta nello stato RESTORING e non sono consentite modifiche nei database.</span><span class="sxs-lookup"><span data-stu-id="2d500-110">Deleting an availability group from a secondary replica leaves the primary replica in the RESTORING state, and changes are not allowed on the databases.</span></span>  
  
-   <span data-ttu-id="2d500-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2d500-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2d500-112">Limitazioni e consigli</span><span class="sxs-lookup"><span data-stu-id="2d500-112">Limitations and Recommendations</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2d500-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2d500-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2d500-114">**Per eliminare un gruppo di disponibilità utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="2d500-114">**To delete an availability group, using:**</span></span>  
  
     [<span data-ttu-id="2d500-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d500-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2d500-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d500-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="2d500-117">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d500-117">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="2d500-118">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="2d500-118">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d500-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2d500-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-recommendations"></a><a name="Restrictions"></a><span data-ttu-id="2d500-120">Limitazioni e consigli</span><span class="sxs-lookup"><span data-stu-id="2d500-120">Limitations and Recommendations</span></span>  
  
-   <span data-ttu-id="2d500-121">L'eliminazione del gruppo di disponibilità online da una replica secondaria determina la transizione della replica primaria allo stato RESTORING.</span><span class="sxs-lookup"><span data-stu-id="2d500-121">When the availability group is online, deleting it from a secondary replica causes the primary replica to transition to the RESTORING state.</span></span> <span data-ttu-id="2d500-122">Pertanto, se possibile, rimuovere il gruppo di disponibilità solo dall'istanza del server in cui è ospitata la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="2d500-122">Therefore, if possible, remove the availability group only from the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="2d500-123">Se si elimina un gruppo di disponibilità da un computer rimosso o eliminato dal cluster di failover WSFC, il gruppo di disponibilità viene eliminato solo localmente.</span><span class="sxs-lookup"><span data-stu-id="2d500-123">If you delete an availability group from a computer that has been removed or evicted from the WSFC failover cluster, the availability group is only deleted locally.</span></span>  
  
-   <span data-ttu-id="2d500-124">Evitare di eliminare un gruppo di disponibilità se il cluster WSFC (Windows Server Failover Clustering) non dispone di quorum.</span><span class="sxs-lookup"><span data-stu-id="2d500-124">Avoid dropping an availability group when the Windows Server Failover Clustering (WSFC) cluster has no quorum.</span></span> <span data-ttu-id="2d500-125">Se è necessario eliminare un gruppo di disponibilità quando il cluster non dispone di quorum, non verrà rimosso il gruppo di disponibilità dei metadati archiviato nel cluster.</span><span class="sxs-lookup"><span data-stu-id="2d500-125">If you must drop an availability group while the cluster lacks quorum, the metadata availability group that is stored in the cluster is not removed.</span></span> <span data-ttu-id="2d500-126">Una volta che il cluster avrà riacquisito il quorum, sarà necessario eliminare nuovamente il gruppo di disponibilità per rimuoverlo dal cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="2d500-126">After the cluster regains quorum, you will need to drop the availability group again to remove it from the WSFC cluster.</span></span>  
  
-   <span data-ttu-id="2d500-127">In una replica secondaria è opportuno utilizzare DROP AVAILABILITY GROUP solo in casi di emergenza,</span><span class="sxs-lookup"><span data-stu-id="2d500-127">On a secondary replica, DROP AVAILABILITY GROUP should only be used only for emergency purposes.</span></span> <span data-ttu-id="2d500-128">poiché, se si elimina un gruppo di disponibilità, quest'ultimo viene portato offline.</span><span class="sxs-lookup"><span data-stu-id="2d500-128">This is because dropping an availability group takes the availability group offline.</span></span> <span data-ttu-id="2d500-129">Se si elimina il gruppo di disponibilità da una replica secondaria, la replica primaria non è in grado di determinare se lo stato è passato OFFLINE a causa della perdita del quorum, di un failover forzato o di un comando DROP AVAILABILITY GROUP.</span><span class="sxs-lookup"><span data-stu-id="2d500-129">If you drop the availability group from a secondary replica, the primary replica cannot determine whether the OFFLINE state occurred because of quorum loss, a forced failover, or a DROP AVAILABILITY GROUP command.</span></span> <span data-ttu-id="2d500-130">La replica primaria passa allo stato RESTORING per impedire una possibile situazione split-brain.</span><span class="sxs-lookup"><span data-stu-id="2d500-130">The primary replica transitions to the RESTORING state to prevent a possible split-brain situation.</span></span> <span data-ttu-id="2d500-131">Per altre informazioni, vedere [How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (Funzionamento: comportamenti di DROP AVAILABILITY GROUP) nel blog del Supporto Tecnico di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2d500-131">For more information, see [How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d500-132">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2d500-132">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d500-133">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2d500-133">Permissions</span></span>  
 <span data-ttu-id="2d500-134">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="2d500-134">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span> <span data-ttu-id="2d500-135">Per eliminare un gruppo di disponibilità non ospitato dall'istanza del server locale, è necessaria l'autorizzazione CONTROL SERVER o CONTROL in tale gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2d500-135">To drop an availability group that is not hosted by the local server instance you need CONTROL SERVER permission or CONTROL permission on that Availability Group.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2d500-136">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d500-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2d500-137">**Per eliminare un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="2d500-137">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="2d500-138">In Esplora oggetti connettersi all'istanza del server in cui è ospitata la replica primaria, se possibile, o connettersi a un'altra istanza del server abilitata per la funzionalità Gruppi di disponibilità AlwaysOn in un nodo WSFC che dispone delle credenziali di sicurezza corrette per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2d500-138">In Object Explorer, connect to the server instance that hosts primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span> <span data-ttu-id="2d500-139">Espandere l'albero di server.</span><span class="sxs-lookup"><span data-stu-id="2d500-139">Expand the server tree.</span></span>  
  
2.  <span data-ttu-id="2d500-140">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="2d500-140">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="2d500-141">Questo passaggio dipende dalla scelta di eliminare più gruppi di disponibilità o uno soltanto, come segue:</span><span class="sxs-lookup"><span data-stu-id="2d500-141">This step depends on whether you want to delete multiple availability groups or only one availability group, as follows:</span></span>  
  
    -   <span data-ttu-id="2d500-142">Per eliminare più gruppi di disponibilità le cui repliche primarie sono nell'istanza del server connesso, usare il riquadro **Dettagli Esplora oggetti** per visualizzare e selezionare tutti i gruppi di disponibilità da eliminare.</span><span class="sxs-lookup"><span data-stu-id="2d500-142">To delete multiple availability groups (whose primary replicas are on the connected server instance), use the **Object Explorer Details** pane to view and select all the availability groups that you want to delete.</span></span> <span data-ttu-id="2d500-143">Per altre informazioni, vedere [Utilizzare Dettagli Esplora oggetti per monitorare Gruppi di disponibilità &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="2d500-143">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="2d500-144">Per eliminare un solo gruppo di disponibilità, selezionarlo nel riquadro **Esplora oggetti** o in quello **Dettagli Esplora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="2d500-144">To delete a single availability group, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
4.  <span data-ttu-id="2d500-145">Fare clic con il pulsante destro del mouse sui gruppi di disponibilità selezionati e scegliere il comando **Elimina** .</span><span class="sxs-lookup"><span data-stu-id="2d500-145">Right-click the selected availability group or groups, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="2d500-146">Nella finestra di dialogo **Rimuovi gruppo di disponibilità** scegliere **OK**per eliminare tutti i gruppi di disponibilità elencati.</span><span class="sxs-lookup"><span data-stu-id="2d500-146">In the **Remove Availability Group** dialog box, to delete all the listed availability groups, click **OK**.</span></span> <span data-ttu-id="2d500-147">Se non si desidera rimuovere tutti i gruppi di disponibilità elencati, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="2d500-147">If you do not want to remove all the listed availability groups, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2d500-148">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d500-148">Using Transact-SQL</span></span>  
 <span data-ttu-id="2d500-149">**Per eliminare un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="2d500-149">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="2d500-150">Connettersi all'istanza del server in cui è ospitata la replica primaria, se possibile, o connettersi a un'altra istanza del server abilitata per la funzionalità Gruppi di disponibilità AlwaysOn in un nodo WSFC che dispone delle credenziali di sicurezza corrette per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2d500-150">Connect to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="2d500-151">Utilizzare l'istruzione [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) , come indicato di seguito</span><span class="sxs-lookup"><span data-stu-id="2d500-151">Use the [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) statement, as follows</span></span>  
  
     <span data-ttu-id="2d500-152">DROP AVAILABILITY GROUP *nome_gruppo*</span><span class="sxs-lookup"><span data-stu-id="2d500-152">DROP AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="2d500-153">dove *nome_gruppo* è il nome del gruppo di disponibilità da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="2d500-153">where *group_name* is the name of the availability group to be dropped.</span></span>  
  
     <span data-ttu-id="2d500-154">Nell'esempio seguente viene eliminato il gruppo di disponibilità `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="2d500-154">The following example deletes the `MyAG` availability group.</span></span>  
  
    ```sql
    DROP AVAILABILITY GROUP MyAG;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="2d500-155">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d500-155">Using PowerShell</span></span>  
 <span data-ttu-id="2d500-156">**Per eliminare un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="2d500-156">**To delete an availability group**</span></span>  
  
 <span data-ttu-id="2d500-157">Nel provider PowerShell per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="2d500-157">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="2d500-158">Impostare la directory (`cd`) sull'istanza del server in cui è ospitata la replica primaria, se possibile, o connettersi a un'altra istanza del server abilitata per la funzionalità Gruppi di disponibilità AlwaysOn in un nodo WSFC che dispone delle credenziali di sicurezza corrette per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2d500-158">Change directory (`cd`) to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="2d500-159">Usare il cmdlet **Remove-SqlAvailabilityGroup** .</span><span class="sxs-lookup"><span data-stu-id="2d500-159">Use the **Remove-SqlAvailabilityGroup** cmdlet.</span></span>  
  
     <span data-ttu-id="2d500-160">Ad esempio, il comando seguente rimuove il gruppo di disponibilità denominato `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="2d500-160">For example, the following command removes the availability group named `MyAg`.</span></span> <span data-ttu-id="2d500-161">Il comando può essere eseguito in qualsiasi istanza del server che ospita una replica di disponibilità per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2d500-161">This command can be executed on any server instance that hosts an availability replica for the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d500-162">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d500-162">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="2d500-163">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2d500-163">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="2d500-164">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="2d500-164">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="2d500-165">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="2d500-165">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="2d500-166">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="2d500-166">Related Content</span></span>  
  
-   <span data-ttu-id="2d500-167">[How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (Funzionamento: comportamenti di DROP AVAILABILITY GROUP) nel blog del Supporto Tecnico di SQL Server</span><span class="sxs-lookup"><span data-stu-id="2d500-167">[How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d500-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d500-168">See Also</span></span>  
 <span data-ttu-id="2d500-169">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2d500-169">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="2d500-170">Creazione e configurazione di gruppi di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2d500-170">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
