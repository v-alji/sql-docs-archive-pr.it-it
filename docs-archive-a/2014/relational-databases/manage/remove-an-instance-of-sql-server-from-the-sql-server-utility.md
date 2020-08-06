---
title: Rimuovere un'istanza di SQL Server da Utilità SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.utility.remove.f1
ms.assetid: ae1d126a-46d2-47bf-b339-17c743df6491
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c09897fcd3ac6d82308288391cf54176eef49d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637846"
---
# <a name="remove-an-instance-of-sql-server-from-the-sql-server-utility"></a><span data-ttu-id="3ec6d-102">Rimuovere un'istanza di SQL Server da Utilità SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ec6d-102">Remove an Instance of SQL Server from the SQL Server Utility</span></span>
  <span data-ttu-id="3ec6d-103">Usare i passaggi seguenti per rimuovere un'istanza gestita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ec6d-103">Use the following steps to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="3ec6d-104">Questa procedura rimuove l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dalla visualizzazione elenco del punto di controllo dell'utilità e arresta la raccolta dati in Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ec6d-104">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection stops.</span></span> <span data-ttu-id="3ec6d-105">L'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non viene disinstallata.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-105">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3ec6d-106">Prima di utilizzare questa procedura per rimuovere un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , verificare che i servizi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e SQL Server Agent siano in esecuzione nell'istanza da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-106">Before you use this procedure to remove an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and SQL Server Agent services are running on the instance to remove.</span></span>  
  
1.  <span data-ttu-id="3ec6d-107">Da Esplora utilità in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]fare clic su **Istanze gestite**.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-107">From the Utility Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click on **Managed Instances**.</span></span> <span data-ttu-id="3ec6d-108">Osservare la visualizzazione elenco delle istanze gestite di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel riquadro del contenuto di Esplora utilità.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-108">Observe the list view of managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the Utility Explorer content pane.</span></span>  
  
2.  <span data-ttu-id="3ec6d-109">Nella colonna **Nome istanza di SQL Server** della visualizzazione elenco selezionare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da rimuovere da Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ec6d-109">In the **SQL Server Instance Name** column of the list view, select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to remove from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="3ec6d-110">Fare clic con il pulsante destro del mouse sull'istanza da rimuovere e scegliere **Rimuovi istanza gestita**.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-110">Right-click on the instance to remove, and select **Remove Managed Instance...**.</span></span>  
  
3.  <span data-ttu-id="3ec6d-111">Specificare le credenziali con privilegi di amministratore per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: Fare clic su **Connetti**, verificare le informazioni nella finestra di dialogo **Connetti al server** e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-111">Specify credentials with administrator privileges for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: Click **Connect...**, verify the information in the **Connect to Server** dialog box, then click **Connect**.</span></span> <span data-ttu-id="3ec6d-112">Le informazioni di accesso verranno visualizzate nella finestra di dialogo **Rimuovi istanza gestita** .</span><span class="sxs-lookup"><span data-stu-id="3ec6d-112">You will see the login information on the **Remove Managed Instance** dialog.</span></span>  
  
4.  <span data-ttu-id="3ec6d-113">Fare clic su **OK**per confermare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-113">To confirm the operation, click **OK**.</span></span> <span data-ttu-id="3ec6d-114">Per uscire dall'operazione, scegliere **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-114">To quit the operation, click **Cancel**.</span></span>  
  
## <a name="manually-remove-a-managed-instance-of-sql-server-from-a-sql-server-utility"></a><span data-ttu-id="3ec6d-115">Rimozione manuale di un'istanza gestita di SQL Server da un'Utilità SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ec6d-115">Manually Remove a Managed Instance of SQL Server from a SQL Server Utility</span></span>  
 <span data-ttu-id="3ec6d-116">Questa procedura rimuove l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dalla visualizzazione elenco del punto di controllo dell'utilità e arresta la raccolta dati in Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ec6d-116">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and stops [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection.</span></span> <span data-ttu-id="3ec6d-117">L'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non viene disinstallata.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-117">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
 <span data-ttu-id="3ec6d-118">È possibile usare PowerShell per rimuovere un'istanza gestita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ec6d-118">To use PowerShell to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="3ec6d-119">lo script esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ec6d-119">This script performs the following operations:</span></span>  
  
-   <span data-ttu-id="3ec6d-120">Ottiene il punto di controllo dell'utilità tramite il nome dell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-120">Gets the UCP by server instance name.</span></span>  
  
-   <span data-ttu-id="3ec6d-121">Rimuove l'istanza gestita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ec6d-121">Removes the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
```powershell
# Get Ucp connection  
$UcpServerInstanceName = "ComputerName\InstanceName";  
$UtilityInstance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $UcpServerInstanceName;  
$UcpConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $UtilityInstance.ConnectionContext.SqlConnectionObject;  
$Utility = [Microsoft.SqlServer.Management.Utility.Utility]::Connect($UcpConnection);  
  
# Now remove the ManagedInstance from the SQL Server Utility  
$ServerInstanceName = "ComputerName\InstanceName";  
$Instance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $ServerInstanceName;  
$InstanceConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $Instance.ConnectionContext.SqlConnectionObject;  
$ManagedInstance = $Utility.ManagedInstances[$ServerInstanceName];  
$ManagedInstance.Remove($InstanceConnection);  
```  
  
<span data-ttu-id="3ec6d-122">È importante fare riferimento al nome dell' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istanza esattamente come viene archiviato in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ec6d-122">It's important to refer to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name exactly as it is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3ec6d-123">Su un'istanza con distinzione tra maiuscole e minuscole di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è necessario specificare il nome dell'istanza usando la combinazione di maiuscole e minuscole esatta restituita da @@SERVERNAME.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-123">On a case-sensitive instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must specify the instance name using the exact casing as returned by @@SERVERNAME.</span></span> 

<span data-ttu-id="3ec6d-124">Per ottenere il nome dell'istanza per l'istanza gestita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], eseguire la seguente query sull'istanza gestita:</span><span class="sxs-lookup"><span data-stu-id="3ec6d-124">To get the instance name for the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run this query on the managed instance:</span></span>  
  
```sql
select @@SERVERNAME AS instance_name  
```  
  
 <span data-ttu-id="3ec6d-125">A questo punto, l'istanza gestita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene rimossa completamente dal punto di controllo dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-125">At this point, the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is fully removed from the UCP.</span></span> <span data-ttu-id="3ec6d-126">Al successivo aggiornamento dei dati per Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non risulterà più presente nella visualizzazione elenco.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-126">It disappears from the list view the next time you refresh data for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="3ec6d-127">Il risultato è identico al caso in cui un utente esegue la rimozione dell'istanza gestita nell'interfaccia utente di SSMS.</span><span class="sxs-lookup"><span data-stu-id="3ec6d-127">This state is identical to a user successfully going through the remove managed instance operation in the SSMS user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ec6d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ec6d-128">See Also</span></span>  
 <span data-ttu-id="3ec6d-129">[Utilizzo di Esplora utilità per gestire Utilità SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="3ec6d-129">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="3ec6d-130">Attività e funzionalità di Utilità SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ec6d-130">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
