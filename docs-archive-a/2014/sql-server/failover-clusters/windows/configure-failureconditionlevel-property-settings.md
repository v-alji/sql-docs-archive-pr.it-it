---
title: Configurare le impostazioni della proprietà FailureConditionLevel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 513dd179-9a46-46da-9fdd-7632cf6d0816
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8924b864d7cc8be078b370e3182713114f54ff6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628278"
---
# <a name="configure-failureconditionlevel-property-settings"></a><span data-ttu-id="e3ad3-102">Configurare le impostazioni della proprietà FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="e3ad3-102">Configure FailureConditionLevel Property Settings</span></span>
  <span data-ttu-id="e3ad3-103">Utilizzare la proprietà FailureConditionLevel per impostare le condizioni per il failover o il riavvio dell'istanza del cluster di failover AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-103">Use the FailureConditionLevel property to set the conditions for the AlwaysOn Failover Cluster Instance (FCI) to fail over or restart.</span></span> <span data-ttu-id="e3ad3-104">Le modifiche apportate a questa proprietà vengono applicate immediatamente senza richiedere il riavvio del servizio cluster di failover di Windows Server (WSFC) o della risorsa istanza cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-104">Changes to this property are applied immediately without requiring a restart of the Windows Server Failover Cluster (WSFC) service or the FCI resource.</span></span>  
  
-   <span data-ttu-id="e3ad3-105">**Prima di iniziare:**  [Impostazioni della proprietà FailureConditionLevel](#Restrictions), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="e3ad3-105">**Before you begin:**  [FailureConditionLevel Property Settings](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="e3ad3-106">**Per configurare le impostazioni della proprietà FailureConditionLevel usando** [PowerShell](#PowerShellProcedure), [Gestione cluster di failover](#WSFC), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="e3ad3-106">**To configure the FailureConditionLevel property settings using,** [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3ad3-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e3ad3-107">Before You Begin</span></span>  
  
###  <a name="failureconditionlevel-property-settings"></a><a name="Restrictions"></a> <span data-ttu-id="e3ad3-108">Impostazioni della proprietà FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="e3ad3-108">FailureConditionLevel Property Settings</span></span>  
 <span data-ttu-id="e3ad3-109">Le condizioni di errore vengono impostate in base a un ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-109">The failure conditions are set on an increasing scale.</span></span> <span data-ttu-id="e3ad3-110">In ognuno dei livelli 1-5 sono incluse tutte le condizioni dei livelli precedenti oltre alle proprie condizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-110">For levels 1-5, each level includes all the conditions from the previous levels in addition to its own conditions.</span></span> <span data-ttu-id="e3ad3-111">Pertanto, in ogni livello la probabilità di un failover o di un riavvio è maggiore.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-111">This means that with each level, there is an increased probability of a failover or restart.</span></span>  <span data-ttu-id="e3ad3-112">Per ulteriori informazioni, vedere la sezione "Determinazione di errori" nell'argomento [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) .</span><span class="sxs-lookup"><span data-stu-id="e3ad3-112">For more information, see the "Determining Failures" section of the [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e3ad3-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e3ad3-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3ad3-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e3ad3-114">Permissions</span></span>  
 <span data-ttu-id="e3ad3-115">È necessario disporre delle autorizzazioni ALTER SETTINGS e VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-115">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="e3ad3-116">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3ad3-116">Using PowerShell</span></span>  
  
### <a name="to-configure-failureconditionlevel-settings"></a><span data-ttu-id="e3ad3-117">Per configurare le impostazioni FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="e3ad3-117">To configure FailureConditionLevel settings</span></span>  
  
1.  <span data-ttu-id="e3ad3-118">Avviare Windows PowerShell con privilegi elevati tramite **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="e3ad3-119">Importare il modulo `FailoverClusters` per abilitare i cmdlet del cluster.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-119">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="e3ad3-120">Utilizzare il `Get-ClusterResource` cmdlet per trovare la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] risorsa, quindi utilizzare il `Set-ClusterParameter` cmdlet per impostare la proprietà **FailureConditionLevel** per un'istanza del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-120">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **FailureConditionLevel** property for a Failover Cluster Instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="e3ad3-121">Ogni volta che viene aperta una nuova finestra di PowerShell, è necessario importare il modulo `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-121">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="e3ad3-122">Nell'esempio seguente, l'impostazione FailureConditionLevel nella risorsa di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] "`SQL Server (INST1)`" viene impostata per eseguire il failover o il riavvio in caso di errori critici del server.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-122">The following example changes the FailureConditionLevel setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to fail over or restart on critical server errors.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter FailureConditionLevel 3
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="e3ad3-123">Contenuto correlato (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e3ad3-123">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="e3ad3-124">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog) (Clustering e disponibilità elevata - Blog del team di clustering di failover e bilanciamento del carico di rete)</span><span class="sxs-lookup"><span data-stu-id="e3ad3-124">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="e3ad3-125">[Introduzione a Windows PowerShell in un cluster di failover](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e3ad3-125">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="e3ad3-126">Comandi di risorse cluster e cmdlet di Windows PowerShell equivalenti</span><span class="sxs-lookup"><span data-stu-id="e3ad3-126">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="e3ad3-127">Utilizzo dello snap-in Gestione cluster di failover</span><span class="sxs-lookup"><span data-stu-id="e3ad3-127">Using the Failover Cluster Manager Snap-in</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="e3ad3-128">Per configurare le impostazioni delle proprietà FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="e3ad3-128">To configure FailureConditionLevel property settings</span></span>
  
1.  <span data-ttu-id="e3ad3-129">Aprire lo snap-in Gestione cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-129">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="e3ad3-130">Espandere **Servizi e applicazioni** e selezionare l'istanza del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-130">Expand the **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="e3ad3-131">Fare clic con il pulsante destro del mouse su **Risorsa di SQL Server** in **Altre risorse**, quindi, nel menu, selezionare **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="e3ad3-131">Right-click the **SQL Server resource** under **Other Resources**, and then select **Properties** from the menu.</span></span> <span data-ttu-id="e3ad3-132">Verrà aperta la finestra di dialogo **Proprietà** della risorsa di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-132">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="e3ad3-133">Selezionare la scheda **Proprietà** , immettere il valore desiderato per la proprietà **FailureConditionLevel** , quindi fare clic su **OK** per applicare la modifica.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-133">Select the **Properties** tab, enter the desired value for the **FaliureConditionLevel** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e3ad3-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3ad3-134">Using Transact-SQL</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="e3ad3-135">Per configurare le impostazioni delle proprietà FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="e3ad3-135">To configure FailureConditionLevel property settings</span></span>
  
 <span data-ttu-id="e3ad3-136">Con l'istruzione [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] è possibile specificare il valore della proprietà FailureConditionLevel.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-136">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the FailureConditionLevel property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="e3ad3-137">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e3ad3-137">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="e3ad3-138">Quando nel seguente esempio la proprietà FailureConditionLevel viene impostata su 0, viene indicato che con qualsiasi condizione di errore non verrà attivato automaticamente alcun failover o riavvio.</span><span class="sxs-lookup"><span data-stu-id="e3ad3-138">The following example sets the FailureConditionLevel property to 0, indicating that failover or restart will not be triggered automatically on any failure conditions.</span></span>  
  
```sql
ALTER SERVER CONFIGURATION SET FAILOVER CLUSTER PROPERTY FailureConditionLevel = 0;  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3ad3-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3ad3-139">See Also</span></span>  
 <span data-ttu-id="e3ad3-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3ad3-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span></span>  
 [<span data-ttu-id="e3ad3-141">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="e3ad3-141">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
