---
title: Abilitare e disabilitare Gruppi di disponibilità AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], disabling
- Availability Groups [SQL Server], enabling
ms.assetid: 7c326958-5ae9-4761-9c57-905972276a8f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 585f1d86d328b7c5027241310108d102b56ca327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624958"
---
# <a name="enable-and-disable-alwayson-availability-groups-sql-server"></a><span data-ttu-id="22bbf-102">Abilitare e disabilitare la funzionalità Gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="22bbf-102">Enable and Disable AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="22bbf-103">L'abilitazione di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] è un prerequisito per l'utilizzo di gruppi di disponibilità in un'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="22bbf-103">Enabling [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is a prerequisite for a server instance to use availability groups.</span></span> <span data-ttu-id="22bbf-104">Prima di poter creare e configurare un qualsiasi gruppo di disponibilità, la funzionalità [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] deve essere stata abilitata in ogni istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in cui sarà ospitata una replica di disponibilità per uno o più gruppi di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="22bbf-104">Before you can create and configure any availability group, the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature must have been enabled on the each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that will host an availability replica for one or more availability groups.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="22bbf-105">Se si elimina e si ricrea un cluster WSFC, è necessario disabilitare e riabilitare la funzionalità [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in ogni istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in cui è ospitata una replica di disponibilità nel cluster WSFC originale.</span><span class="sxs-lookup"><span data-stu-id="22bbf-105">If you delete and re-create a WSFC cluster, you must disable and re-enable the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature on each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosted an availability replica on the original WSFC cluster.</span></span>  
  
-   <span data-ttu-id="22bbf-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="22bbf-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="22bbf-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="22bbf-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="22bbf-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="22bbf-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="22bbf-109">**Come si fa:**</span><span class="sxs-lookup"><span data-stu-id="22bbf-109">**How To:**</span></span>  
  
    -   [<span data-ttu-id="22bbf-110">Determinare se la funzionalità Gruppi di disponibilità AlwaysOn è abilitata</span><span class="sxs-lookup"><span data-stu-id="22bbf-110">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>](#IsEnabled)  
  
    -   [<span data-ttu-id="22bbf-111">Abilita Gruppi di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="22bbf-111">Enable AlwaysOn Availability Groups</span></span>](#EnableAOAG)  
  
    -   [<span data-ttu-id="22bbf-112">Disabilitare Gruppi di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="22bbf-112">Disable AlwaysOn Availability Groups</span></span>](#DisableAOAG)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="22bbf-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="22bbf-113">Before You Begin</span></span>  
  
###  <a name="prerequisites-for-enabling-alwayson-availability-groups"></a><a name="Prerequisites"></a><span data-ttu-id="22bbf-114">Prerequisiti per l'abilitazione di Gruppi di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="22bbf-114">Prerequisites for Enabling AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="22bbf-115">L'istanza del server deve trovarsi in un nodo WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="22bbf-115">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="22bbf-116">Nell'istanza del server deve essere in esecuzione un'edizione di SQL Server che supporta [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22bbf-116">The server instance must be running an edition of SQL Server that supports [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="22bbf-117">Per ulteriori informazioni, vedere [Features Supported by the Editions of SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="22bbf-117">For more information, see [Features Supported by the Editions of SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="22bbf-118">Abilitare Gruppi di disponibilità AlwaysOn in una sola istanza del server per volta.</span><span class="sxs-lookup"><span data-stu-id="22bbf-118">Enable AlwaysOn Availability Groups on only one server instance at a time.</span></span> <span data-ttu-id="22bbf-119">Dopo aver abilitato Gruppi di disponibilità AlwaysOn, attendere il riavvio del servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] prima di continuare con un'altra istanza del server.</span><span class="sxs-lookup"><span data-stu-id="22bbf-119">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
 <span data-ttu-id="22bbf-120">Per informazioni sui prerequisiti aggiuntivi per la creazione e la configurazione dei gruppi di disponibilità, vedere [prerequisiti, restrizioni e consigli per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="22bbf-120">For information about additional prerequisites for creating and configuring availability groups, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="22bbf-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="22bbf-121">Security</span></span>  
 <span data-ttu-id="22bbf-122">Mentre la funzionalità Gruppi di disponibilità AlwaysOn è abilitata in un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'istanza del server dispone del controllo completo nel cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="22bbf-122">While AlwaysOn Availability Groups is enabled on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server instance has full control on the WSFC cluster.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="22bbf-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="22bbf-123">Permissions</span></span>  
 <span data-ttu-id="22bbf-124">È richiesta l'appartenenza al gruppo degli **amministratori** nel computer locale, nonché il controllo totale nel cluster WSCF.</span><span class="sxs-lookup"><span data-stu-id="22bbf-124">Requires membership in the **Administrator** group on the local computer and full control on the WSFC cluster.</span></span> <span data-ttu-id="22bbf-125">Quando si abilita AlwaysOn tramite PowerShell, aprire la finestra del prompt dei comandi utilizzando l'opzione **Esegui come amministratore** .</span><span class="sxs-lookup"><span data-stu-id="22bbf-125">When enabling AlwaysOn by using PowerShell, open the Command Prompt window using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="22bbf-126">Richiede le autorizzazioni per la gestione e la creazione degli oggetti di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="22bbf-126">Requires Active Directory Create Objects and Manage Objects permissions.</span></span>  
  
##  <a name="determine-whether-alwayson-availability-groups-is-enabled"></a><a name="IsEnabled"></a><span data-ttu-id="22bbf-127">Determinare se Gruppi di disponibilità AlwaysOn è abilitato</span><span class="sxs-lookup"><span data-stu-id="22bbf-127">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>  
  
-   [<span data-ttu-id="22bbf-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="22bbf-128">SQL Server Management Studio</span></span>](#SSMS1Procedure)  
  
-   [<span data-ttu-id="22bbf-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="22bbf-129">Transact-SQL</span></span>](#Tsql1Procedure)  
  
-   [<span data-ttu-id="22bbf-130">PowerShell</span><span class="sxs-lookup"><span data-stu-id="22bbf-130">PowerShell</span></span>](#PowerShell1Procedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMS1Procedure"></a> <span data-ttu-id="22bbf-131">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="22bbf-131">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="22bbf-132">**Per determinare se la funzionalità Gruppi di disponibilità AlwaysOn è abilitata**</span><span class="sxs-lookup"><span data-stu-id="22bbf-132">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="22bbf-133">In Esplora oggetti fare clic con il pulsante destro del mouse sull'istanza del server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="22bbf-133">In Object Explorer, right-click the server instance, and  click **Properties**.</span></span>  
  
2.  <span data-ttu-id="22bbf-134">Nella finestra di dialogo **Proprietà server** scegliere la pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="22bbf-134">In the **Server Properties** dialog box, click the **General** page.</span></span> <span data-ttu-id="22bbf-135">Per la proprietà **Is HADR Enabled** è visualizzato uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="22bbf-135">The **Is HADR Enabled** property displays one of the following values:</span></span>  
  
    -   <span data-ttu-id="22bbf-136">**True**, se la funzionalità Gruppi di disponibilità AlwaysOn è abilitata</span><span class="sxs-lookup"><span data-stu-id="22bbf-136">**True**, if AlwaysOn Availability Groups is enabled</span></span>  
  
    -   <span data-ttu-id="22bbf-137">**False**, se la funzionalità Gruppi di disponibilità AlwaysOn è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="22bbf-137">**False**, if AlwaysOn Availability Groups is disabled.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="Tsql1Procedure"></a> <span data-ttu-id="22bbf-138">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="22bbf-138">Using Transact-SQL</span></span>  
 <span data-ttu-id="22bbf-139">**Per determinare se la funzionalità Gruppi di disponibilità AlwaysOn è abilitata**</span><span class="sxs-lookup"><span data-stu-id="22bbf-139">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="22bbf-140">Utilizzare l'istruzione [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) seguente:</span><span class="sxs-lookup"><span data-stu-id="22bbf-140">Use the following [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) statement:</span></span>  
  
    ```sql
    SELECT SERVERPROPERTY ('IsHadrEnabled');  
    ```  
  
     <span data-ttu-id="22bbf-141">L'impostazione della proprietà del server `IsHadrEnabled` indica se un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è abilitata per Gruppi di disponibilità AlwaysOn, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="22bbf-141">The setting of the `IsHadrEnabled` server property indicates whether an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is enabled for AlwaysOn Availability Groups, as follows:</span></span>  
  
    -   <span data-ttu-id="22bbf-142">Se `IsHadrEnabled` = 1, la funzionalità Gruppi di disponibilità AlwaysOn è abilitata.</span><span class="sxs-lookup"><span data-stu-id="22bbf-142">If `IsHadrEnabled` = 1, AlwaysOn Availability Groups is enabled.</span></span>  
  
    -   <span data-ttu-id="22bbf-143">Se `IsHadrEnabled` = 0, la funzionalità Gruppi di disponibilità AlwaysOn è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="22bbf-143">If `IsHadrEnabled` = 0, AlwaysOn Availability Groups is disabled.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22bbf-144">Per ulteriori informazioni sulla `IsHadrEnabled` proprietà del server, vedere [SERVERPROPERTY &#40;&#41;Transact-SQL ](/sql/t-sql/functions/serverproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="22bbf-144">For more information about the `IsHadrEnabled` server property, see [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShell1Procedure"></a> <span data-ttu-id="22bbf-145">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="22bbf-145">Using PowerShell</span></span>  
 <span data-ttu-id="22bbf-146">**Per determinare se la funzionalità Gruppi di disponibilità AlwaysOn è abilitata**</span><span class="sxs-lookup"><span data-stu-id="22bbf-146">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="22bbf-147">Impostare il valore predefinito ( `cd` ) sull'istanza del server, ad esempio `\SQL\NODE1\DEFAULT` , in cui si desidera determinare se [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] è abilitato.</span><span class="sxs-lookup"><span data-stu-id="22bbf-147">Set default (`cd`) to the server instance (e.g. `\SQL\NODE1\DEFAULT`) on which you want to determine whether [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is enabled.</span></span>  
  
2.  <span data-ttu-id="22bbf-148">Eseguire il comando PowerShell `Get-Item` riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="22bbf-148">Enter the following PowerShell `Get-Item` command:</span></span>  
  
    ```powershell
    Get-Item . | Select IsHadrEnabled  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="22bbf-149">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22bbf-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="22bbf-150">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="22bbf-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="22bbf-151">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="22bbf-151">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="22bbf-152">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="22bbf-152">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="enable-alwayson-availability-groups"></a><a name="EnableAOAG"></a> <span data-ttu-id="22bbf-153">Abilitare Gruppi di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="22bbf-153">Enable AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="22bbf-154">**Per abilitare AlwaysOn mediante:**</span><span class="sxs-lookup"><span data-stu-id="22bbf-154">**To enable AlwaysOn, using:**</span></span>  
  
-   [<span data-ttu-id="22bbf-155">Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="22bbf-155">SQL Server Configuration Manager</span></span>](#SQLCM2Procedure)  
  
-   [<span data-ttu-id="22bbf-156">PowerShell</span><span class="sxs-lookup"><span data-stu-id="22bbf-156">PowerShell</span></span>](#PScmd2Procedure)  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM2Procedure"></a> <span data-ttu-id="22bbf-157">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="22bbf-157">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="22bbf-158">**Per abilitare Gruppi di disponibilità AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="22bbf-158">**To enable AlwaysOn Availability Groups**</span></span>  
  
1.  <span data-ttu-id="22bbf-159">Connettersi al nodo WSCF (Windows Server Failover Clustering) in cui è ospitata l'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nella quale si desidera abilitare Gruppi di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="22bbf-159">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to enable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="22bbf-160">Nel menu **Start** scegliere **Tutti i programmi**, [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], **Strumenti di configurazione**, quindi fare clic su **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="22bbf-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and  click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="22bbf-161">In **Gestione configurazione SQL Server**fare clic su **servizi SQL Server**, fare clic con il pulsante destro del mouse su SQL Server (\*\* < *`instance name`*>)\*\*, dove **<*`instance name`*>** è il nome di un'istanza del server locale per cui si desidera abilitare gruppi di disponibilità AlwaysOn e quindi fare clic su **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="22bbf-161">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to enable AlwaysOn Availability Groups, and click **Properties.**</span></span>  
  
4.  <span data-ttu-id="22bbf-162">Selezionare la scheda **Disponibilità elevata AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="22bbf-162">Select the **AlwaysOn High Availability** tab.</span></span>  
  
5.  <span data-ttu-id="22bbf-163">Verificare che nel campo **Nome cluster di failover Windows** sia incluso il nome del cluster di failover locale.</span><span class="sxs-lookup"><span data-stu-id="22bbf-163">Verify that **Windows failover cluster name** field contains the name of the local failover cluster.</span></span> <span data-ttu-id="22bbf-164">Se il campo è vuoto, questa istanza del server non supporta attualmente [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22bbf-164">If this field is blank, this server instance currently does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="22bbf-165">Il computer locale non è un nodo del cluster, il cluster WSFC è stato chiuso, oppure si tratta di un'edizione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] che non supporta [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22bbf-165">Either the local computer is not a cluster node, the WSFC cluster has been shut down, or this edition of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] that does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span>  
  
6.  <span data-ttu-id="22bbf-166">Selezionare la casella di controllo **abilita gruppi di disponibilità AlwaysOn** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22bbf-166">Select the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="22bbf-167">.</span><span class="sxs-lookup"><span data-stu-id="22bbf-167">Configuration Manager saves your change.</span></span> <span data-ttu-id="22bbf-168">Successivamente, è necessario riavviare manualmente il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22bbf-168">Then, you must manually restart the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="22bbf-169">In questo modo è possibile scegliere un'ora per il riavvio che meglio soddisfa le esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="22bbf-169">This enables you to choose a restart time that is best for your business requirements.</span></span> <span data-ttu-id="22bbf-170">Al riavvio del servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], AlwaysOn sarà abilitato e la proprietà del server `IsHadrEnabled` sarà impostata su 1.</span><span class="sxs-lookup"><span data-stu-id="22bbf-170">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be enabled, and the `IsHadrEnabled` server property will be set to 1.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd2Procedure"></a> <span data-ttu-id="22bbf-171">Utilizzo di SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="22bbf-171">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="22bbf-172">**Per abilitare AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="22bbf-172">**To enable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="22bbf-173">Impostare la directory (`cd`) su un'istanza del server che si desidera abilitare per Gruppi di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="22bbf-173">Change directory (`cd`) to a server instance that you want to enable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="22bbf-174">Utilizzare il cmdlet `Enable-SqlAlwaysOn` per abilitare Gruppi di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="22bbf-174">Use the `Enable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="22bbf-175">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22bbf-175">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="22bbf-176">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="22bbf-176">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22bbf-177">Per informazioni su come controllare se il `Enable-SqlAlwaysOn` cmdlet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Riavvia il servizio, vedere [quando un cmdlet riavvia il servizio SQL Server?](#WhenCmdletRestartsSQL), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="22bbf-177">For information about how to control whether the `Enable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
 <span data-ttu-id="22bbf-178">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="22bbf-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="22bbf-179">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="22bbf-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
####  <a name="example-enable-sqlalwayson"></a><a name="ExmplEnable-SqlHadrServic"></a> <span data-ttu-id="22bbf-180">Esempio: Enable-SqlAlwaysOn</span><span class="sxs-lookup"><span data-stu-id="22bbf-180">Example: Enable-SqlAlwaysOn</span></span>  
 <span data-ttu-id="22bbf-181">Il comando di PowerShell seguente abilita [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in un'istanza di SQL Server (*Computer*\\*Istanza*).</span><span class="sxs-lookup"><span data-stu-id="22bbf-181">The following PowerShell command enables [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  
  
```powershell
Enable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
```  
  
##  <a name="disable-alwayson-availability-groups"></a><a name="DisableAOAG"></a><span data-ttu-id="22bbf-182">Disabilitare Gruppi di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="22bbf-182">Disable AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="22bbf-183">**Prima di disabilitare AlwaysOn:**</span><span class="sxs-lookup"><span data-stu-id="22bbf-183">**Before you disable AlwaysOn:**</span></span>  
  
     [<span data-ttu-id="22bbf-184">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="22bbf-184">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="22bbf-185">**Per disabilitare AlwaysOn mediante:**</span><span class="sxs-lookup"><span data-stu-id="22bbf-185">**To disable AlwaysOn, using:**</span></span>  
  
    -   [<span data-ttu-id="22bbf-186">Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="22bbf-186">SQL Server Configuration Manager</span></span>](#SQLCM3Procedure)  
  
    -   [<span data-ttu-id="22bbf-187">PowerShell</span><span class="sxs-lookup"><span data-stu-id="22bbf-187">PowerShell</span></span>](#PScmd3Procedure)  
  
-   <span data-ttu-id="22bbf-188">**Completamento:**  [dopo la disabilitazione di AlwaysOn](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="22bbf-188">**Follow Up:**  [After Disabling AlwaysOn](#FollowUp)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="22bbf-189">Disabilitare AlwaysOn in una sola un'istanza del server per volta.</span><span class="sxs-lookup"><span data-stu-id="22bbf-189">Disable AlwaysOn on only one server instance at a time.</span></span> <span data-ttu-id="22bbf-190">Dopo aver disabilitato Gruppi di disponibilità AlwaysOn, attendere il riavvio del servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] prima di continuare con un'altra istanza del server.</span><span class="sxs-lookup"><span data-stu-id="22bbf-190">After disabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="22bbf-191">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="22bbf-191">Recommendations</span></span>  
 <span data-ttu-id="22bbf-192">Prima di disabilitare AlwaysOn su un'istanza del server, si consiglia di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22bbf-192">Before you disable AlwaysOn on a server instance, we recommend that you do the following:</span></span>  
  
1.  <span data-ttu-id="22bbf-193">Se l'istanza del server sta attualmente ospitando la replica primaria di un gruppo di disponibilità che si desidera tenere, si consiglia di eseguire manualmente un failover sul gruppo di disponibilità a una replica secondaria sincronizzata, se possibile.</span><span class="sxs-lookup"><span data-stu-id="22bbf-193">If the server instance is currently hosting the primary replica of an availability group that you want to keep, we recommend that you manually fail over the availability group to a synchronized secondary replica, if possible.</span></span> <span data-ttu-id="22bbf-194">Per altre informazioni, vedere [Eseguire un failover manuale pianificato di un gruppo di disponibilità &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="22bbf-194">For more information, see [Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="22bbf-195">Rimuovere tutte le repliche secondarie locali.</span><span class="sxs-lookup"><span data-stu-id="22bbf-195">Remove all local secondary replicas.</span></span> <span data-ttu-id="22bbf-196">Per altre informazioni, vedere [Rimuovere una replica secondaria da un gruppo di disponibilità &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="22bbf-196">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM3Procedure"></a> <span data-ttu-id="22bbf-197">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="22bbf-197">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="22bbf-198">**Per disabilitare AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="22bbf-198">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="22bbf-199">Connettersi al nodo WSCF (Windows Server Failover Clustering) nel quale è ospitata l'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in cui si desidera disabilitare Gruppi di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="22bbf-199">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to disable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="22bbf-200">Nel menu **Start** scegliere **Tutti i programmi**, [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], **Strumenti di configurazione**, quindi fare clic su **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="22bbf-200">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="22bbf-201">In **Gestione configurazione SQL Server**fare clic su **servizi SQL Server**, fare clic con il pulsante destro del mouse su SQL Server (\*\* < *`instance name`*>)\*\*, dove **<*`instance name`*>** è il nome di un'istanza del server locale per cui si desidera disabilitare gruppi di disponibilità AlwaysOn, quindi fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="22bbf-201">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to disable AlwaysOn Availability Groups, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="22bbf-202">Deselezionare la casella di controllo**Abilita gruppi di disponibilità AlwaysOn**nella scheda **Disponibilità elevata AlwaysOn** e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="22bbf-202">On the**AlwaysOn High Availability**tab, deselect the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="22bbf-203">è possibile salvare la modifica e riavviare il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22bbf-203">Configuration Manager saves your change and restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="22bbf-204">Al riavvio del servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], AlwaysOn sarà disabilitato e la proprietà del server `IsHadrEnabled` sarà impostata su 0, per indicare che la funzionalità Gruppi di disponibilità AlwaysOn è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="22bbf-204">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be disabled, and the `IsHadrEnabled` server property will be set to 0, to indicate that AlwaysOn Availability Groups is disabled.</span></span>  
  
5.  <span data-ttu-id="22bbf-205">Si consiglia di leggere le informazioni in [Completamento: Dopo la disabilitazione di AlwaysOn](#FollowUp), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="22bbf-205">We recommend that you read the information in [Follow Up: After Disabling AlwaysOn](#FollowUp), later in this topic.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd3Procedure"></a> <span data-ttu-id="22bbf-206">Utilizzo di SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="22bbf-206">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="22bbf-207">**Per disabilitare AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="22bbf-207">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="22bbf-208">Modificare la directory ( `cd` ) in un'istanza del server attualmente abilitata che si desidera disattivarla per gruppi di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="22bbf-208">Change directory (`cd`) to a currently-enabled server instance that you want to disenable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="22bbf-209">Utilizzare il cmdlet `Disable-SqlAlwaysOn` per abilitare Gruppi di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="22bbf-209">Use the `Disable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="22bbf-210">Il comando seguente, ad esempio, Disabilita gruppi di disponibilità AlwaysOn in un'istanza di SQL Server (istanza del*computer* \\ *Instance*).</span><span class="sxs-lookup"><span data-stu-id="22bbf-210">For example, the following command disables AlwaysOn Availability Groups on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  <span data-ttu-id="22bbf-211">Il comando richiede il riavvio dell'istanza per cui verrà richiesta la conferma all'utente.</span><span class="sxs-lookup"><span data-stu-id="22bbf-211">This command requires restarting the instance, and you will be prompted to confirm this restart.</span></span>  
  
    ```powershell
    Disable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="22bbf-212">Per informazioni su come controllare se il `Disable-SqlAlwaysOn` cmdlet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Riavvia il servizio, vedere [quando un cmdlet riavvia il servizio SQL Server?](#WhenCmdletRestartsSQL), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="22bbf-212">For information about how to control whether the `Disable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
     <span data-ttu-id="22bbf-213">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22bbf-213">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="22bbf-214">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="22bbf-214">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="22bbf-215">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="22bbf-215">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="22bbf-216">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="22bbf-216">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="follow-up-after-disabling-alwayson"></a><a name="FollowUp"></a><span data-ttu-id="22bbf-217">Completamento: dopo la disabilitazione di AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="22bbf-217">Follow Up: After Disabling AlwaysOn</span></span>  
 <span data-ttu-id="22bbf-218">Dopo avere disabilitato Gruppi di disponibilità AlwaysOn, è necessario riavviare l'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22bbf-218">After you disable AlwaysOn Availability Groups, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must be restarted.</span></span> <span data-ttu-id="22bbf-219">Gestione configurazione SQL Server riavvia l'istanza del server automaticamente.</span><span class="sxs-lookup"><span data-stu-id="22bbf-219">SQL Configuration Manager restarts the server instance automatically.</span></span> <span data-ttu-id="22bbf-220">Tuttavia, se è stato utilizzato il cmdlet `Disable-SqlAlwaysOn`, sarà necessario riavviare manualmente l'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="22bbf-220">However, if you used the `Disable-SqlAlwaysOn` cmdlet, you will need to restart the server instance manually.</span></span> <span data-ttu-id="22bbf-221">Per altre informazioni, vedere [sqlservr Application](../../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="22bbf-221">For more information, see [sqlservr Application](../../../tools/sqlservr-application.md).</span></span>  
  
 <span data-ttu-id="22bbf-222">Nell'istanza del server riavviata:</span><span class="sxs-lookup"><span data-stu-id="22bbf-222">On the restarted server instance:</span></span>  
  
-   <span data-ttu-id="22bbf-223">Poiché i database di disponibilità non vengono avviati insieme a SQL Server, non saranno accessibili.</span><span class="sxs-lookup"><span data-stu-id="22bbf-223">Availability databases do not start up at SQL Server startup, making them inaccessible.</span></span>  
  
-   <span data-ttu-id="22bbf-224">L'unica istruzione AlwaysOn [!INCLUDE[tsql](../../../includes/tsql-md.md)] supportata è [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="22bbf-224">The only supported AlwaysOn [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement is [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span></span> <span data-ttu-id="22bbf-225">CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP e le opzioni SET HADR di ALTER DATABASE non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="22bbf-225">CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP, and the SET HADR options of ALTER DATABASE are not supported.</span></span>  
  
-   <span data-ttu-id="22bbf-226">I metadati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e i dati di configurazione di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in WSFC non sono interessati dalla disabilitazione di Gruppi di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="22bbf-226">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] metadata and [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration data in WSFC are unaffected by disabling AlwaysOn Availability Groups.</span></span>  
  
 <span data-ttu-id="22bbf-227">Se si disabilita in modo permanente Gruppi di disponibilità AlwaysOn su ogni istanza del server che ospita una replica di disponibilità per uno o più gruppi di disponibilità, si consiglia di completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22bbf-227">If you permanently disable AlwaysOn Availability Groups on every server instance that hosts an availability replica for one or more availability groups, we recommend that you complete the following steps:</span></span>  
  
1.  <span data-ttu-id="22bbf-228">Se le repliche di disponibilità locali non sono state rimosse prima di disabilitare AlwaysOn, eliminare ogni gruppo di disponibilità per il quale l'istanza del server ospita una replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="22bbf-228">If you did not remove the local availability replicas before disabling AlwaysOn, delete (drop) each availability group for which the server instance is hosting an availability replica.</span></span> <span data-ttu-id="22bbf-229">Per informazioni sull'eliminazione di un gruppo di disponibilità, vedere [Rimuovere un gruppo di disponibilità &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="22bbf-229">For information about deleting an availability group, see [Remove an Availability Group &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="22bbf-230">Per rimuovere i metadati rimanenti, eliminare ogni gruppo di disponibilità interessato su un'istanza del server che fa parte del cluster WSFC originale.</span><span class="sxs-lookup"><span data-stu-id="22bbf-230">To remove the metadata left behind, delete (drop) each affected availability group on a server instance that is part of the original WSFC cluster.</span></span>  
  
3.  <span data-ttu-id="22bbf-231">Tutti i database primari continuano a essere accessibili a tutte le connessioni, ma la sincronizzazione dei dati tra i database primario e secondario viene arrestata.</span><span class="sxs-lookup"><span data-stu-id="22bbf-231">Any primary databases continue to be accessible to all connections but the data synchronization between the primary and secondary databases stops.</span></span>  
  
4.  <span data-ttu-id="22bbf-232">Per i database secondari viene impostato lo stato RESTORING.</span><span class="sxs-lookup"><span data-stu-id="22bbf-232">The secondary databases enter the RESTORING state.</span></span> <span data-ttu-id="22bbf-233">È possibile eliminare i database o ripristinarli tramite RESTORE WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="22bbf-233">You can delete them, or you can restore them by using RESTORE WITH RECOVERY.</span></span> <span data-ttu-id="22bbf-234">Tuttavia, i database ripristinati non fanno più parte della sincronizzazione dei dati del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="22bbf-234">However, restored databases are no longer participating in availability-group data synchronization.</span></span>  
  
##  <a name="when-does-a-cmdlet-restart-the-sql-server-service"></a><a name="WhenCmdletRestartsSQL"></a> <span data-ttu-id="22bbf-235">Situazioni in cui un cmdlet comporta il riavvio del servizio SQL Server</span><span class="sxs-lookup"><span data-stu-id="22bbf-235">When Does a Cmdlet Restart the SQL Server Service?</span></span>  
 <span data-ttu-id="22bbf-236">In un'istanza del server attualmente in esecuzione, l'utilizzo di `Enable-SqlAlwaysOn` o `Disable-SqlAlwaysOn` per modificare l'impostazione AlwaysOn corrente può causare il riavvio del servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="22bbf-236">On a server instance that is currently running, using `Enable-SqlAlwaysOn` or `Disable-SqlAlwaysOn` to change the current AlwaysOn setting could cause the SQL Server service to restart.</span></span> <span data-ttu-id="22bbf-237">Il comportamento del riavvio dipende dalle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22bbf-237">The restart behavior on depends on the following conditions:</span></span>  
  
|<span data-ttu-id="22bbf-238">Specifica del parametro -NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="22bbf-238">-NoServiceRestart parameter specified</span></span>|<span data-ttu-id="22bbf-239">Specifica del parametro -Force</span><span class="sxs-lookup"><span data-stu-id="22bbf-239">-Force parameter specified</span></span>|<span data-ttu-id="22bbf-240">Riavvio del servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22bbf-240">Is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarted?</span></span>|  
|--------------------------------------------|---------------------------------|---------------------------------------------------------|  
|<span data-ttu-id="22bbf-241">No</span><span class="sxs-lookup"><span data-stu-id="22bbf-241">No</span></span>|<span data-ttu-id="22bbf-242">No</span><span class="sxs-lookup"><span data-stu-id="22bbf-242">No</span></span>|<span data-ttu-id="22bbf-243">Per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="22bbf-243">By default.</span></span> <span data-ttu-id="22bbf-244">Tuttavia dal cmdlet è richiesto quanto segue:</span><span class="sxs-lookup"><span data-stu-id="22bbf-244">But the cmdlet prompts you as follows:</span></span><br /><br /> <span data-ttu-id="22bbf-245">**Per completare l'azione, è necessario riavviare il servizio SQL Server per l'istanza del server '<nome_istanza>'. Continuare?**</span><span class="sxs-lookup"><span data-stu-id="22bbf-245">**To complete this action, we must restart the SQL Server service for server instance '<instance_name>'. Do you want to continue?**</span></span><br /><br /> <span data-ttu-id="22bbf-246">**[Y] Sì [N] No [S] Sospendi [?] Guida (l'impostazione predefinita è "Y"):**</span><span class="sxs-lookup"><span data-stu-id="22bbf-246">**[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):**</span></span><br /><br /> <span data-ttu-id="22bbf-247">Se si specifica **N** o **S**, il servizio non viene riavviato.</span><span class="sxs-lookup"><span data-stu-id="22bbf-247">If you specify **N** or **S**, the service is not restarted.</span></span>|  
|<span data-ttu-id="22bbf-248">No</span><span class="sxs-lookup"><span data-stu-id="22bbf-248">No</span></span>|<span data-ttu-id="22bbf-249">Sì</span><span class="sxs-lookup"><span data-stu-id="22bbf-249">Yes</span></span>|<span data-ttu-id="22bbf-250">Servizio riavviato.</span><span class="sxs-lookup"><span data-stu-id="22bbf-250">Service is restarted.</span></span>|  
|<span data-ttu-id="22bbf-251">Sì</span><span class="sxs-lookup"><span data-stu-id="22bbf-251">Yes</span></span>|<span data-ttu-id="22bbf-252">No</span><span class="sxs-lookup"><span data-stu-id="22bbf-252">No</span></span>|<span data-ttu-id="22bbf-253">Servizio non riavviato.</span><span class="sxs-lookup"><span data-stu-id="22bbf-253">Service is not restarted.</span></span>|  
|<span data-ttu-id="22bbf-254">Sì</span><span class="sxs-lookup"><span data-stu-id="22bbf-254">Yes</span></span>|<span data-ttu-id="22bbf-255">Sì</span><span class="sxs-lookup"><span data-stu-id="22bbf-255">Yes</span></span>|<span data-ttu-id="22bbf-256">Servizio non riavviato.</span><span class="sxs-lookup"><span data-stu-id="22bbf-256">Service is not restarted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22bbf-257">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22bbf-257">See Also</span></span>  
 <span data-ttu-id="22bbf-258">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="22bbf-258">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="22bbf-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="22bbf-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
