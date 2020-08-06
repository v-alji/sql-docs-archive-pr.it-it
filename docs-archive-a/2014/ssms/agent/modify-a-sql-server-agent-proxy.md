---
title: Modificare un proxy di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], modifying
- modifying SQL Server Agent proxy
ms.assetid: 6e1dfbaa-8089-4813-940c-d5a2e13d8552
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f86793a8ddcc6fe8f981d6b367d2178c5a794ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627046"
---
# <a name="modify-a-sql-server-agent-proxy"></a><span data-ttu-id="c837c-102">Modify a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="c837c-102">Modify a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="c837c-103">In questo argomento viene descritto come modificare un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proxy di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c837c-103">This topic describes how to modify a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c837c-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c837c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c837c-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c837c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c837c-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c837c-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c837c-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c837c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c837c-108">**Per modificare un proxy di SQL Server Agent utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="c837c-108">**To modify a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="c837c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c837c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c837c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c837c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c837c-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c837c-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c837c-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c837c-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c837c-113">I proxy di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent utilizzano le credenziali per archiviare le informazioni sugli account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="c837c-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="c837c-114">L'utente specificato nella credenziale deve disporre dell'autorizzazione "accesso come processo batch" sul computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c837c-114">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c837c-115">Agent verifica l'accesso al sottosistema per un proxy e garantisce l'accesso al proxy ad ogni esecuzione del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="c837c-115">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="c837c-116">Se il proxy non dispone più di accesso al sottosistema, il passaggio di processo non viene eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c837c-116">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="c837c-117">In caso contrario, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent rappresenta l'utente specificato nel proxy ed esegue il passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="c837c-117">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="c837c-118">Se l'account di accesso per l'utente viene utilizzato per l'accesso al proxy oppure se l'utente appartiene a un qualsiasi ruolo che prevede l'accesso al proxy, l'utente potrà utilizzare il proxy in un passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="c837c-118">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c837c-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c837c-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c837c-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c837c-120">Permissions</span></span>  
 <span data-ttu-id="c837c-121">Gli account proxy possono essere creati, modificati o eliminati unicamente dai membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c837c-121">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c837c-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c837c-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="c837c-123">Per modificare un proxy di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span><span class="sxs-lookup"><span data-stu-id="c837c-123">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="c837c-124">In **Esplora oggetti**fare clic sul segno più per espandere il server che contiene l'account proxy di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent da modificare.</span><span class="sxs-lookup"><span data-stu-id="c837c-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account that you want to modify.</span></span>  
  
2.  <span data-ttu-id="c837c-125">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="c837c-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="c837c-126">Fare clic sul segno più per espandere la cartella **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="c837c-126">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="c837c-127">Fare clic sul segno più per espandere il nodo del sottosistema per il proxy, ad esempio **ActiveX Script**.</span><span class="sxs-lookup"><span data-stu-id="c837c-127">Click the plus sign to expand the subsystem node for the proxy (for example, **ActiveX Script**).</span></span>  
  
5.  <span data-ttu-id="c837c-128">Fare clic con il pulsante destro del mouse sull'account proxy da modificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c837c-128">Right-click the proxy account you want to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="c837c-129">Nella finestra di dialogo _Proprietà account proxy_**nome_proxy** , apportare le modifiche necessarie all'account proxy.</span><span class="sxs-lookup"><span data-stu-id="c837c-129">In the _proxy_name_**Proxy Account Properties** dialog box, make changes to the proxy account as necessary.</span></span> <span data-ttu-id="c837c-130">Per altre informazioni sulle opzioni della finestra di dialogo, vedere [Creazione di un proxy di SQL Server Agent](create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="c837c-130">For more information on the options in this dialog box, see [Create a SQL Server Agent Proxy](create-a-sql-server-agent-proxy.md).</span></span>  
  
7.  <span data-ttu-id="c837c-131">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c837c-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c837c-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c837c-132">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="c837c-133">Per modificare un proxy di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span><span class="sxs-lookup"><span data-stu-id="c837c-133">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="c837c-134">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c837c-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c837c-135">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c837c-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c837c-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c837c-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Disables the proxy named 'Catalog application proxy'.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="c837c-137">Per ulteriori informazioni, vedere [sp_update_proxy &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c837c-137">For more information, see [sp_update_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span></span>  
  
  
