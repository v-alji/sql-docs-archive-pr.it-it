---
title: Rimuovere un listener del gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeaglistener.default.f1
helpviewer_keywords:
- Availability Groups [SQL Server], listeners
ms.assetid: fd9bba9a-d29f-4c23-8ecd-aaa049ed5f1b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 057b9c137cb4d8bbbdd03be61df600f7e59b264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626310"
---
# <a name="remove-an-availability-group-listener-sql-server"></a><span data-ttu-id="35f63-102">Rimuovere un listener del gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="35f63-102">Remove an Availability Group Listener (SQL Server)</span></span>
  <span data-ttu-id="35f63-103">In questo argomento viene illustrato come rimuovere un listener da un gruppo di disponibilità AlwaysOn utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35f63-103">This topic describes how to remove an availability group listener from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="35f63-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="35f63-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="35f63-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="35f63-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="35f63-106">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="35f63-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="35f63-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="35f63-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="35f63-108">**Per rimuovere un listener utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="35f63-108">**To remove a listener, using:**</span></span>  
  
     [<span data-ttu-id="35f63-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35f63-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="35f63-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="35f63-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="35f63-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="35f63-111">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="35f63-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="35f63-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="35f63-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="35f63-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="35f63-114">È necessario essere connessi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="35f63-114">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="35f63-115">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="35f63-115">Recommendations</span></span>  
 <span data-ttu-id="35f63-116">Prima di eliminare un listener del gruppo di disponibilità, si consiglia di verificare che non sia utilizzato da alcuna applicazione.</span><span class="sxs-lookup"><span data-stu-id="35f63-116">Before you delete an availability group listener, we recommend that you ensure that no applications are using it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="35f63-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="35f63-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="35f63-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="35f63-118">Permissions</span></span>  
 <span data-ttu-id="35f63-119">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="35f63-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="35f63-120">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35f63-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="35f63-121">**Per rimuovere un listener del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="35f63-121">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="35f63-122">In Esplora oggetti connettersi all'istanza del server in cui viene ospitata la replica primaria e fare clic sul nome del server per espandere il relativo albero.</span><span class="sxs-lookup"><span data-stu-id="35f63-122">In Object Explorer, connect to the server instance that hosts the primary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="35f63-123">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="35f63-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="35f63-124">Espandere il nodo del gruppo di disponibilità ed espandere il nodo **Listener gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="35f63-124">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="35f63-125">Fare clic con il pulsante destro del mouse sul listener da rimuovere, quindi scegliere il comando **Elimina** .</span><span class="sxs-lookup"><span data-stu-id="35f63-125">Right-click the listener to be removed, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="35f63-126">Verrà aperta la finestra di dialogo **Rimuovi listener dal gruppo disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="35f63-126">This opens the **Remove Listener from Availability Group** dialog box.</span></span> <span data-ttu-id="35f63-127">Per ulteriori informazioni, vedere [Rimuovi listener dal gruppo di disponibilità](#AgListenerPropertiesDialog), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="35f63-127">For more information, see [Remove Listener from Availability Group](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="remove-listener-from-availability-group-dialog-box"></a><a name="AgListenerPropertiesDialog"></a><span data-ttu-id="35f63-128">Rimuovi listener dal gruppo di disponibilità (finestra di dialogo)</span><span class="sxs-lookup"><span data-stu-id="35f63-128">Remove Listener from Availability Group (Dialog Box)</span></span>  
 <span data-ttu-id="35f63-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="35f63-129">**Name**</span></span>  
 <span data-ttu-id="35f63-130">Nome del listener da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="35f63-130">The name of the listener to be removed.</span></span>  
  
 <span data-ttu-id="35f63-131">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="35f63-131">**Result**</span></span>  
 <span data-ttu-id="35f63-132">Viene visualizzato un collegamento, **Esito positivo** o **Errore**, su cui è possibile fare clic per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="35f63-132">Displays a link, either **Success** or **Error**, which you can click for more information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="35f63-133">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="35f63-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="35f63-134">**Per rimuovere un listener del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="35f63-134">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="35f63-135">Connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="35f63-135">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="35f63-136">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="35f63-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="35f63-137">ALTER AVAILABILITY GROUP *group_name* rimuovere il listener **' *`dns_name`* '**</span><span class="sxs-lookup"><span data-stu-id="35f63-137">ALTER AVAILABILITY GROUP *group_name* REMOVE LISTENER **'*`dns_name`*'**</span></span>  
  
     <span data-ttu-id="35f63-138">dove *group_name* è il nome del gruppo di disponibilità e *dns_name* è il nome DNS del listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="35f63-138">where *group_name* is the name of the availability group and *dns_name* is the DNS name of the availability group listener.</span></span>  
  
     <span data-ttu-id="35f63-139">Nell'esempio seguente viene eliminato il listener del gruppo di disponibilità `AccountsAG` .</span><span class="sxs-lookup"><span data-stu-id="35f63-139">The following example deletes the listener of the `AccountsAG` availability group.</span></span> <span data-ttu-id="35f63-140">Il nome DNS è AccountsAG_Listener.</span><span class="sxs-lookup"><span data-stu-id="35f63-140">The DNS name is AccountsAG_Listener.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP AccountsAG REMOVE LISTENER 'AccountsAG_Listener';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="35f63-141">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="35f63-141">Using PowerShell</span></span>  
 <span data-ttu-id="35f63-142">**Per rimuovere un listener del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="35f63-142">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="35f63-143">Impostare il valore predefinito (`cd`) sull'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="35f63-143">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="35f63-144">Utilizzare il cmdlet `Remove-Item` predefinito per rimuovere un listener.</span><span class="sxs-lookup"><span data-stu-id="35f63-144">Use the built in `Remove-Item` cmdlet to remove a listener.</span></span> <span data-ttu-id="35f63-145">Ad esempio, il seguente comando rimuove il listener `MyListener` dal gruppo di disponibilità `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="35f63-145">For example, the following command removes a listener named `MyListener` from an availability group named `MyAg`.</span></span>  
  
    ```powershell
    Remove-Item SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AGListeners\MyListener  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="35f63-146">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35f63-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="35f63-147">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="35f63-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="35f63-148">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="35f63-148">Related Tasks</span></span>  
  
-   [<span data-ttu-id="35f63-149">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35f63-149">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="35f63-150">Visualizzare le proprietà del listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35f63-150">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="35f63-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35f63-151">See Also</span></span>  
 <span data-ttu-id="35f63-152">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="35f63-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="35f63-153">Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35f63-153">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
