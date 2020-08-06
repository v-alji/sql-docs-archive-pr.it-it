---
title: Usare i criteri AlwaysOn per visualizzare l'integrità di un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6f1bcbc3-1220-4071-8e53-4b957f5d3089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c4444afc2348b2407dc19c1c12761ef0251631e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724943"
---
# <a name="use-alwayson-policies-to-view-the-health-of-an-availability-group-sql-server"></a><span data-ttu-id="7d115-102">Utilizzare i criteri AlwaysOn per visualizzare l'integrità di un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7d115-102">Use AlwaysOn Policies to View the Health of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="7d115-103">In questo argomento viene illustrato come determinare l'integrità operativa di un gruppo di disponibilità AlwaysOn utilizzando i criteri AlwaysOn in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d115-103">This topic describes how to determine the operational health of an AlwaysOn availability group by using an AlwaysOn policy in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="7d115-104">Per informazioni sulla gestione basata su criteri AlwaysOn, vedere [criteri AlwaysOn per problemi operativi con gruppi di disponibilità AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="7d115-104">For information about AlwaysOn Policy Based Management, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7d115-105">Per i criteri AlwaysOn, i nomi delle categorie vengono utilizzati come ID.</span><span class="sxs-lookup"><span data-stu-id="7d115-105">For AlwaysOn policies, the category names are used as IDs.</span></span> <span data-ttu-id="7d115-106">La modifica del nome di una categoria AlwaysOn causa l'interruzione della funzionalità di valutazione dell'integrità.</span><span class="sxs-lookup"><span data-stu-id="7d115-106">Changing the name of an AlwaysOn category would break its health-evaluation functionality.</span></span> <span data-ttu-id="7d115-107">Pertanto, i nomi di categoria AlwaysOn non devono mai essere modificati.</span><span class="sxs-lookup"><span data-stu-id="7d115-107">Therefore, the names of AlwaysOn category should never be modified.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7d115-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7d115-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7d115-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7d115-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7d115-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7d115-110">Permissions</span></span>  
 <span data-ttu-id="7d115-111">È necessario disporre delle autorizzazioni CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="7d115-111">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="using-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="7d115-112">Uso del dashboard AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7d115-112">Using the AlwaysOn Dashboard</span></span>  
 <span data-ttu-id="7d115-113">**Per aprire il Dashboard AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="7d115-113">**To open the AlwaysOn Dashboard**</span></span>  
  
1.  <span data-ttu-id="7d115-114">In Esplora oggetti connettersi all'istanza del server che ospita una delle repliche di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="7d115-114">In Object Explorer, connect to the server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="7d115-115">Per visualizzare informazioni su tutte le repliche di disponibilità di un determinato gruppo, connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="7d115-115">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="7d115-116">Fare clic sul nome del server per espandere il relativo albero.</span><span class="sxs-lookup"><span data-stu-id="7d115-116">Click the server name to expand the server tree.</span></span>  
  
3.  <span data-ttu-id="7d115-117">Espandere il nodo **Disponibilità elevata AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="7d115-117">Expand the **AlwaysOn High Availability** node.</span></span>  
  
     <span data-ttu-id="7d115-118">Fare clic con il pulsante destro del mouse sul nodo **Gruppi di disponibilità** o espandere il nodo e fare clic con il pulsante destro del mouse su un gruppo di disponibilità specifico.</span><span class="sxs-lookup"><span data-stu-id="7d115-118">Either right-click the **Availability Groups** node or expand this node and right-click a specific availability group.</span></span>  
  
4.  <span data-ttu-id="7d115-119">Selezionare il comando **Mostra dashboard** .</span><span class="sxs-lookup"><span data-stu-id="7d115-119">Select the **Show Dashboard** command.</span></span>  
  
 <span data-ttu-id="7d115-120">Per informazioni su come usare il dashboard AlwaysOn, vedere [Utilizzare il Dashboard AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7d115-120">For information about how to use the AlwaysOn Dashboard, see [Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="7d115-121">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d115-121">Using PowerShell</span></span>  
 <span data-ttu-id="7d115-122">**Usare i criteri AlwaysOn per visualizzare l'integrità di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="7d115-122">**Use AlwaysOn policies to view the health of an availability group**</span></span>  
  
1.  <span data-ttu-id="7d115-123">Spostarsi sulla directory (`cd`) dell'istanza del server che ospita una delle repliche di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="7d115-123">Set default (`cd`) to a server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="7d115-124">Per visualizzare informazioni su tutte le repliche di disponibilità di un determinato gruppo, connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="7d115-124">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="7d115-125">Usare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d115-125">Use the following cmdlets:</span></span>  
  
     `Test-SqlAvailabilityGroup`  
     <span data-ttu-id="7d115-126">Valuta l'integrità di un gruppo di disponibilità valutando i criteri della gestione basata su criteri di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d115-126">Assesses the health of an availability group by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="7d115-127">È necessario disporre delle autorizzazioni CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION per eseguire questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d115-127">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="7d115-128">Ad esempio, il comando seguente mostra tutti i gruppi di disponibilità con stato di integrità "Error" nell'istanza del server `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="7d115-128">For example, the following command shows all availability groups with a health state of "Error" on the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups |
        Test-SqlAvailabilityGroup |
        Where-Object { $_.HealthState -eq "Error" }  
    ```  
  
     `Test-SqlAvailabilityReplica`  
     <span data-ttu-id="7d115-129">Valuta l'integrità delle repliche di disponibilità valutando i criteri della gestione basata su criteri di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d115-129">Assesses the health of availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="7d115-130">È necessario disporre delle autorizzazioni CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION per eseguire questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d115-130">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="7d115-131">Ad esempio, il seguente comando valuta l'integrità della replica di disponibilità denominata `MyReplica` nel gruppo di disponibilità `MyAg` e restituisce un breve riepilogo.</span><span class="sxs-lookup"><span data-stu-id="7d115-131">For example, the following command evaluates the health of the availability replica named `MyReplica` in the availability group `MyAg` and outputs a brief summary.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityReplica -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
     `Test-SqlDatabaseReplicaState`  
     <span data-ttu-id="7d115-132">Valuta l'integrità di un database di disponibilità su tutte le repliche di disponibilità aggiunte valutando i criteri della gestione basata su criteri di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d115-132">Assesses the health of an availability database on all joined availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span>  
  
     <span data-ttu-id="7d115-133">Ad esempio, il seguente comando valuta l'integrità di tutte i database di disponibilità nel gruppo di disponibilità `MyAg` e restituisce un breve riepilogo per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="7d115-133">For example, the following command evaluates the health of all availability databases in the availability group `MyAg` and outputs a brief summary for each database.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\DatabaseReplicaStates |
        Test-SqlDatabaseReplicaState  
    ```  
  
     <span data-ttu-id="7d115-134">Questi cmdlet accettano le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d115-134">These cmdlets accept the following options:</span></span>  
  
    |<span data-ttu-id="7d115-135">Opzione</span><span class="sxs-lookup"><span data-stu-id="7d115-135">Option</span></span>|<span data-ttu-id="7d115-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d115-136">Description</span></span>|  
    |------------|-----------------|  
    |`AllowUserPolicies`|<span data-ttu-id="7d115-137">Esegue i criteri utente trovati nelle categorie dei criteri AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="7d115-137">Runs user policies found in the AlwaysOn policy categories.</span></span>|  
    |`InputObject`|<span data-ttu-id="7d115-138">Raccolta di oggetti che rappresentano gruppi di disponibilità, repliche di disponibilità o stati dei database di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="7d115-138">A collection of objects that, represent availability groups, availability replicas, or availability database states (depending on which cmdlet you are using).</span></span> <span data-ttu-id="7d115-139">Il cmdlet calcolerà l'integrità degli oggetti specificati.</span><span class="sxs-lookup"><span data-stu-id="7d115-139">The cmdlet will compute the health of the specified objects.</span></span>|  
    |`NoRefresh`|<span data-ttu-id="7d115-140">Quando questo parametro viene impostato, il cmdlet non aggiorna manualmente gli oggetti specificati dal parametro `-Path` o `-InputObject`.</span><span class="sxs-lookup"><span data-stu-id="7d115-140">When this parameter is set, the cmdlet will not manually refresh the objects specified by the `-Path` or `-InputObject` parameter.</span></span>|  
    |`Path`|<span data-ttu-id="7d115-141">Percorso del gruppo di disponibilità, una o più repliche di disponibilità o stato del cluster della replica di database del database di disponibilità (a seconda del cmdlet utilizzato).</span><span class="sxs-lookup"><span data-stu-id="7d115-141">The path to the availability group, one or more availability replicas, or database replica cluster state of the availability database (depending on which cmdlet you are using).</span></span> <span data-ttu-id="7d115-142">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7d115-142">This is an optional parameter.</span></span> <span data-ttu-id="7d115-143">Se non specificato, il valore predefinito di questo parametro sarà il percorso di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="7d115-143">If not specified, the value of this parameter defaults to the current working location.</span></span>|  
    |`ShowPolicyDetails`|<span data-ttu-id="7d115-144">Mostra il risultato di ogni valutazione dei criteri eseguita da questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d115-144">Shows the result of each policy evaluation performed by this cmdlet.</span></span> <span data-ttu-id="7d115-145">Il cmdlet restituisce un oggetto per ogni valutazione dei criteri e questo oggetto contiene campi che descrivono i risultati della valutazione, ovvero se i criteri sono stati soddisfatti, il nome e la categoria dei criteri e così via.</span><span class="sxs-lookup"><span data-stu-id="7d115-145">The cmdlet outputs one object per policy evaluation, and this object has fields describing the results of evaluation (whether the policy passed or not, the policy name and category, and so forth).</span></span>|  
  
     <span data-ttu-id="7d115-146">Ad esempio, il seguente comando `Test-SqlAvailabilityGroup` specifica il parametro `-ShowPolicyDetails` per mostrare i risultati della valutazione per ciascun criterio eseguita da questo cmdlet per ciascun criterio della gestione basata su criteri eseguito sul gruppo di disponibilità `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="7d115-146">For example, the following `Test-SqlAvailabilityGroup` command specifies the `-ShowPolicyDetails` parameter to show the result of each policy evaluation performed by this cmdlet for each policy-based management (PBM) policy that was executed on the availability group named `MyAg`.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\AgName -ShowPolicyDetails  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d115-147">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d115-147">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="7d115-148">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="7d115-148">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="7d115-149">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="7d115-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="7d115-150">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d115-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="7d115-151">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d115-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="7d115-152">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="7d115-152">Related Content</span></span>  
 <span data-ttu-id="7d115-153">**SQL Server Blog del team AlwaysOn-monitoraggio dell'integrità AlwaysOn con PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="7d115-153">**SQL Server AlwaysOn Team Blogs-Monitoring AlwaysOn Health with PowerShell:**</span></span>  
  
-   [<span data-ttu-id="7d115-154">Pagina relativa alla prima parte riguardante la panoramica su cmdlet di base</span><span class="sxs-lookup"><span data-stu-id="7d115-154">Part 1: Basic Cmdlet Overview</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-1-basic-cmdlet-overview)  
  
-   [<span data-ttu-id="7d115-155">Pagina relativa alla seconda parte riguardante l'utilizzo avanzato di cmdlet</span><span class="sxs-lookup"><span data-stu-id="7d115-155">Part 2: Advanced Cmdlet Usage</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/the-alwayson-health-model-part-2-extending-the-health-model)  
  
-   [<span data-ttu-id="7d115-156">Pagina relativa alla terza parte riguardante un'applicazione di monitoraggio semplice</span><span class="sxs-lookup"><span data-stu-id="7d115-156">Part 3: A Simple Monitoring Application</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-3-a-simple-monitoring-application)  
  
-   [<span data-ttu-id="7d115-157">Pagina relativa alla quarta parte riguardante l'integrazione con SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="7d115-157">Part 4: Integration with SQL Server Agent</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-4-integration-with-sql-server-agent)  
  
## <a name="see-also"></a><span data-ttu-id="7d115-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d115-158">See Also</span></span>  
 <span data-ttu-id="7d115-159">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d115-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7d115-160">[Amministrazione di un gruppo di disponibilità &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d115-160">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="7d115-161">[Monitoraggio di Gruppi di disponibilità &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d115-161">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="7d115-162">Criteri AlwaysOn per problemi operativi con gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7d115-162">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-policies-for-operational-issues-always-on-availability.md) 
