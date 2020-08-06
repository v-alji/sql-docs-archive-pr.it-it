---
title: Eliminare un proxy di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting SQL Server Agent proxies
- proxies [SQL Server Agent], deleting
- removing SQL Server Agent proxies
ms.assetid: 9248841d-7294-47d4-94f3-b34a0521fabc
author: stevestein
ms.author: sstein
ms.openlocfilehash: a672c6392e2ffed3ca2a7ed655b806d9d093b10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635321"
---
# <a name="delete-a-sql-server-agent-proxy"></a><span data-ttu-id="6d92a-102">Delete a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="6d92a-102">Delete a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="6d92a-103">In questo argomento viene descritto come eliminare un account proxy di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d92a-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6d92a-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6d92a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6d92a-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="6d92a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6d92a-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6d92a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6d92a-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6d92a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6d92a-108">**Per eliminare un account proxy di SQL Server Agent utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="6d92a-108">**To delete a SQL Server Agent proxy account, using:**</span></span>  
  
     [<span data-ttu-id="6d92a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d92a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6d92a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d92a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6d92a-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6d92a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6d92a-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6d92a-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6d92a-113">Quando si elimina un account proxy di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, assicurarsi che il proxy non faccia riferimento ad alcun passaggio di processo attivo.</span><span class="sxs-lookup"><span data-stu-id="6d92a-113">When you delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account, make sure the proxy does not reference any active job steps.</span></span> <span data-ttu-id="6d92a-114">Per verificare eventuali passaggi di processo che fanno riferimento al proxy, fare clic con il pulsante destro del mouse sul proxy, scegliere **Proprietà**e quindi nella finestra di dialogo _Proprietà account proxy_**nome_proxy** selezionare la pagina **Riferimenti** .</span><span class="sxs-lookup"><span data-stu-id="6d92a-114">To check for any job steps that reference the proxy, right-click the proxy, select **Properties**, and then, in the _proxy_name_**Proxy Account Properties** dialog box, select the **References** page.</span></span> <span data-ttu-id="6d92a-115">Se si elimina un proxy, la finestra di dialogo **Elimina oggetto** consente di riassegnare tutti i passaggi di processo che utilizzano tale proxy.</span><span class="sxs-lookup"><span data-stu-id="6d92a-115">If you delete a proxy, you are given the option to reassign all job steps that use that proxy in the **Delete Object** dialog box.</span></span>  
  
-   <span data-ttu-id="6d92a-116">I proxy di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent utilizzano le credenziali per archiviare le informazioni sugli account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="6d92a-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="6d92a-117">L'utente specificato nella credenziale deve disporre dell'autorizzazione "accesso come processo batch" sul computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d92a-117">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6d92a-118">Agent verifica l'accesso al sottosistema per un proxy e garantisce l'accesso al proxy ad ogni esecuzione del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="6d92a-118">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="6d92a-119">Se il proxy non dispone più di accesso al sottosistema, il passaggio di processo non viene eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6d92a-119">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="6d92a-120">In caso contrario, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent rappresenta l'utente specificato nel proxy ed esegue il passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="6d92a-120">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="6d92a-121">Se l'account di accesso per l'utente viene utilizzato per l'accesso al proxy oppure se l'utente appartiene a un qualsiasi ruolo che prevede l'accesso al proxy, l'utente potrà utilizzare il proxy in un passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="6d92a-121">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6d92a-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6d92a-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6d92a-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6d92a-123">Permissions</span></span>  
 <span data-ttu-id="6d92a-124">Gli account proxy possono essere creati, modificati o eliminati unicamente dai membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="6d92a-124">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6d92a-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d92a-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="6d92a-126">Per eliminare un account proxy di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="6d92a-126">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="6d92a-127">In **Esplora oggetti**fare clic sul segno più per espandere un server che contiene l'account proxy da eliminare.</span><span class="sxs-lookup"><span data-stu-id="6d92a-127">In **Object Explorer**, click the plus sign to expand a server that contains the proxy account that you want to delete.</span></span>  
  
2.  <span data-ttu-id="6d92a-128">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="6d92a-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="6d92a-129">Fare clic sul segno più per espandere la cartella **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="6d92a-129">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="6d92a-130">Fare clic sul segno più per espandere il sottosistema che contiene l'account proxy da eliminare, ad esempio **ActiveX Script**.</span><span class="sxs-lookup"><span data-stu-id="6d92a-130">Click the plus sign to expand the subsystem that contains the proxy account you want to delete (for example, **ActiveX Script)**.</span></span>  
  
5.  <span data-ttu-id="6d92a-131">Fare clic con il pulsante destro del mouse sull'account proxy da eliminare e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6d92a-131">Right-click the proxy account that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="6d92a-132">Nella finestra di dialogo **Elimina oggetto** verificare che sia selezionato l'account proxy corretto.</span><span class="sxs-lookup"><span data-stu-id="6d92a-132">In the **Delete Object** dialog box, confirm that the correct proxy account is selected.</span></span> <span data-ttu-id="6d92a-133">Selezionare la casella di controllo **Riassegna a** per riassegnare i passaggi del processo che si riferiscono all'account proxy a un altro account.</span><span class="sxs-lookup"><span data-stu-id="6d92a-133">Check the **Reassign to** check box to reassign the job steps that reference this proxy account to another account.</span></span>  
  
7.  <span data-ttu-id="6d92a-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d92a-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6d92a-135">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d92a-135">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="6d92a-136">Per eliminare un account proxy di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="6d92a-136">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="6d92a-137">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d92a-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6d92a-138">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="6d92a-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6d92a-139">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="6d92a-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the proxy "Catalog application proxy"  
    USE msdb ;  
    GO  
    EXEC dbo.sp_delete_proxy  
        @proxy_name = N'Catalog application proxy' ;  
    GO  
    ```  
  
 <span data-ttu-id="6d92a-140">Per ulteriori informazioni, vedere [sp_delete_proxy &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6d92a-140">For more information, see [sp_delete_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span></span>  
  
  
