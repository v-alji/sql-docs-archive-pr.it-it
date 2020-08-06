---
title: Configurare le impostazioni HealthCheckTimeout | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 3bbeb979-e6fc-4184-ad6e-cca62108de74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a38cd6e9e4718a2f1c136e5412cde340e92f14c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628276"
---
# <a name="configure-healthchecktimeout-property-settings"></a><span data-ttu-id="cbbea-102">Configurazione delle impostazioni HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="cbbea-102">Configure HealthCheckTimeout Property Settings</span></span>
  <span data-ttu-id="cbbea-103">L'impostazione HealthCheckTimeout viene utilizzata per specificare la durata, in millisecondi, dell'attesa della DLL della risorsa di SQL Server relativamente alle informazioni restituite dalla stored procedure [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) prima di stabilire la mancata risposta da parte dell'istanza del cluster di failover AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="cbbea-103">The HealthCheckTimeout setting is used to specify the length of time, in milliseconds, that the SQL Server resource DLL should wait for information returned by the [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) stored procedure before reporting the AlwaysOn Failover Cluster Instance (FCI) as unresponsive.</span></span> <span data-ttu-id="cbbea-104">Le modifiche apportate alle impostazioni del timeout vengono applicate immediatamente e non richiedono il riavvio della risorsa di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbbea-104">Changes that are made to the timeout settings are effective immediately and do not require a restart of the SQL Server resource.</span></span>  
  
-   <span data-ttu-id="cbbea-105">**Prima di iniziare:**  [Limitazioni e restrizioni](#Limits), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="cbbea-105">**Before you begin:**  [Limitations and Restrictions](#Limits), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="cbbea-106">**Per configurare l'impostazione HeathCheckTimeout, usando:**  [PowerShell](#PowerShellProcedure), [Gestione cluster di failover](#WSFC), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="cbbea-106">**To Configure the HeathCheckTimeout setting, using:**  [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cbbea-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="cbbea-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limits"></a> <span data-ttu-id="cbbea-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="cbbea-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="cbbea-109">Il valore predefinito di questa proprietà è 60.000 millisecondi (60 secondi).</span><span class="sxs-lookup"><span data-stu-id="cbbea-109">The default value for this property is 60,000 milliseconds (60 seconds).</span></span> <span data-ttu-id="cbbea-110">Il valore minimo è 15.000 millisecondi (15 secondi).</span><span class="sxs-lookup"><span data-stu-id="cbbea-110">The minimum value is 15,000 milliseconds (15 seconds).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cbbea-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cbbea-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cbbea-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cbbea-112">Permissions</span></span>  
 <span data-ttu-id="cbbea-113">È necessario disporre delle autorizzazioni ALTER SETTINGS e VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="cbbea-113">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="cbbea-114">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbbea-114">Using PowerShell</span></span>  
  
### <a name="to-configure-healthchecktimeout-settings"></a><span data-ttu-id="cbbea-115">Per configurare le impostazioni HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="cbbea-115">To configure HealthCheckTimeout settings</span></span>  
  
1.  <span data-ttu-id="cbbea-116">Avviare Windows PowerShell con privilegi elevati tramite **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="cbbea-116">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="cbbea-117">Importare il modulo `FailoverClusters` per abilitare i cmdlet del cluster.</span><span class="sxs-lookup"><span data-stu-id="cbbea-117">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="cbbea-118">Utilizzare il `Get-ClusterResource` cmdlet per trovare la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] risorsa, quindi utilizzare il `Set-ClusterParameter` cmdlet per impostare la proprietà **HealthCheckTimeout** per l'istanza del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="cbbea-118">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **HealthCheckTimeout** property for the failover cluster instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="cbbea-119">Ogni volta che viene aperta una nuova finestra di PowerShell, è necessario importare il modulo `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="cbbea-119">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="cbbea-120">Nell'esempio seguente, l'impostazione HealthCheckTimeout nella risorsa di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] "`SQL Server (INST1)`" viene impostata su 60.000 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="cbbea-120">The following example changes the HealthCheckTimeout setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to 60000 milliseconds.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter HealthCheckTimeout 60000  
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="cbbea-121">Contenuto correlato (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cbbea-121">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="cbbea-122">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog) (Clustering e disponibilità elevata - Blog del team di clustering di failover e bilanciamento del carico di rete)</span><span class="sxs-lookup"><span data-stu-id="cbbea-122">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="cbbea-123">[Introduzione a Windows PowerShell in un cluster di failover](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="cbbea-123">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="cbbea-124">Comandi di risorse cluster e cmdlet di Windows PowerShell equivalenti</span><span class="sxs-lookup"><span data-stu-id="cbbea-124">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="cbbea-125">Utilizzo dello snap-in Gestione cluster di failover</span><span class="sxs-lookup"><span data-stu-id="cbbea-125">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="cbbea-126">**Per configurare le impostazioni HealthCheckTimeout**</span><span class="sxs-lookup"><span data-stu-id="cbbea-126">**To configure HealthCheckTimeout setting**</span></span>  
  
1.  <span data-ttu-id="cbbea-127">Aprire lo snap-in Gestione cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="cbbea-127">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="cbbea-128">Espandere **Servizi e applicazioni** e selezionare l'istanza del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="cbbea-128">Expand **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="cbbea-129">Fare clic con il pulsante destro del mouse sulla risorsa **SQL Server** in **Altre risorse** e selezionare **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="cbbea-129">Right-click the **SQL Server resource** under **Other Resources** and select **Properties** from the right-click menu.</span></span> <span data-ttu-id="cbbea-130">Verrà aperta la finestra di dialogo **Proprietà** della risorsa di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbbea-130">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="cbbea-131">Selezionare la scheda **Proprietà** , immettere il valore desiderato per la proprietà **HealthCheckTimeout** , quindi fare clic su **OK** per applicare la modifica.</span><span class="sxs-lookup"><span data-stu-id="cbbea-131">Select the **Properties** tab, enter the desired value for the **HealthCheckTimeout** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cbbea-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cbbea-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="cbbea-133">Utilizzando l'istruzione [ALTER Server Configuration](/sql/t-sql/statements/alter-server-configuration-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] , è possibile specificare il valore della proprietà HealthCheckTimeout.</span><span class="sxs-lookup"><span data-stu-id="cbbea-133">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the HealthCheckTimeOut property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="cbbea-134">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cbbea-134">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="cbbea-135">Nell'esempio seguente l'opzione HealthCheckTimeout viene impostata su 15.000 millisecondi (15 secondi).</span><span class="sxs-lookup"><span data-stu-id="cbbea-135">The following example sets the HealthCheckTimeout option to 15,000 milliseconds (15 seconds).</span></span>  
  
```sql
ALTER SERVER CONFIGURATION   
SET FAILOVER CLUSTER PROPERTY HealthCheckTimeout = 15000;  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbbea-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbbea-136">See Also</span></span>  
 [<span data-ttu-id="cbbea-137">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="cbbea-137">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
