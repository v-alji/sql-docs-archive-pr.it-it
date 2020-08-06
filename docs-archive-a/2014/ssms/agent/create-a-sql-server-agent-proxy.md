---
title: Creare un proxy di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], creating
ms.assetid: 142e0c55-a8b9-4669-be49-b9dc602d5988
author: stevestein
ms.author: sstein
ms.openlocfilehash: a7582aef38d57b15de968d96357e56c1974d733e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635325"
---
# <a name="create-a-sql-server-agent-proxy"></a><span data-ttu-id="5e248-102">Creazione di un proxy di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="5e248-102">Create a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="5e248-103">In questo argomento viene descritto come creare un proxy SQL Server Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e248-103">This topic describes how to create a SQL Server Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5e248-104">Un account proxy di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent definisce un contesto di sicurezza in cui è possibile l'esecuzione di un passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="5e248-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account defines a security context in which a job step can run.</span></span> <span data-ttu-id="5e248-105">Ogni proxy corrisponde a una credenziale di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5e248-105">Each proxy corresponds to a security credential.</span></span> <span data-ttu-id="5e248-106">Per impostare le autorizzazioni per un particolare passaggio di processo, creare un proxy dotato delle autorizzazioni necessarie per un sottosistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e quindi assegnarlo al passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="5e248-106">To set permissions for a particular job step, create a proxy that has the required permissions for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent subsystem, and then assign that proxy to the job step.</span></span>  
  
 <span data-ttu-id="5e248-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5e248-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5e248-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5e248-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5e248-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5e248-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5e248-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5e248-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5e248-111">**Per creare un proxy di SQL Server Agent utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="5e248-111">**To create a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="5e248-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e248-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5e248-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e248-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5e248-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5e248-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5e248-115">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5e248-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5e248-116">Se non disponibili, prima di creare un proxy è necessario creare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="5e248-116">You must create a credential before you create a proxy if one is not already available.</span></span>  
  
-   <span data-ttu-id="5e248-117">I proxy di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent utilizzano le credenziali per archiviare le informazioni sugli account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="5e248-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="5e248-118">L'utente specificato nella credenziale deve disporre dell'autorizzazione "accesso come processo batch" sul computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5e248-118">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e248-119">Agent verifica l'accesso al sottosistema per un proxy e garantisce l'accesso al proxy ad ogni esecuzione del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="5e248-119">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="5e248-120">Se il proxy non dispone più di accesso al sottosistema, il passaggio di processo non viene eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5e248-120">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="5e248-121">In caso contrario, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent rappresenta l'utente specificato nel proxy ed esegue il passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="5e248-121">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="5e248-122">La creazione di un proxy non implica la modifica delle autorizzazioni per l'utente specificato nella credenziale del proxy.</span><span class="sxs-lookup"><span data-stu-id="5e248-122">Creation of a proxy does not change the permissions for the user that is specified in the credential for the proxy.</span></span> <span data-ttu-id="5e248-123">È possibile ad esempio creare un proxy per un utente che non dispone dell'autorizzazione per la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e248-123">For example, you can create a proxy for a user that does not have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5e248-124">In questo caso, i passaggi di processo che utilizzano il proxy non sono in grado di connettersi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e248-124">In this case, job steps that use that proxy are unable to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="5e248-125">Se l'account di accesso per l'utente viene utilizzato per l'accesso al proxy oppure se l'utente appartiene a un qualsiasi ruolo che prevede l'accesso al proxy, l'utente potrà utilizzare il proxy in un passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="5e248-125">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5e248-126">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5e248-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5e248-127">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5e248-127">Permissions</span></span>  
  
-   <span data-ttu-id="5e248-128">Solo i membri del ruolo predefinito del server **sysadmin** sono autorizzati a creare, modificare o eliminare gli account proxy.</span><span class="sxs-lookup"><span data-stu-id="5e248-128">Only members of the **sysadmin** fixed server role have permission to create, modify, or delete proxy accounts.</span></span> <span data-ttu-id="5e248-129">Gli utenti che non sono membri del ruolo predefinito del server **sysadmin** devono essere aggiunti a uno dei ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel database **msdb** per poter utilizzare i proxy: **SQLAgentUserRole**, **SQLAgentReaderRole**o **SQLAgentOperatorRole**.</span><span class="sxs-lookup"><span data-stu-id="5e248-129">Users who are not members of the **sysadmin** fixed server role must be added to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database to use proxies: **SQLAgentUserRole**, **SQLAgentReaderRole**, or **SQLAgentOperatorRole**.</span></span>  
  
-   <span data-ttu-id="5e248-130">Richiede l'autorizzazione `ALTER ANY CREDENTIAL` se si creano le credenziali oltre al proxy.</span><span class="sxs-lookup"><span data-stu-id="5e248-130">Requires `ALTER ANY CREDENTIAL` permission if creating a credential in addition to the proxy.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5e248-131">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e248-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="5e248-132">Per creare un proxy di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="5e248-132">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="5e248-133">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera creare un proxy SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="5e248-133">In **Object Explorer**, click the plus sign to expand the server where you want to create a proxy on SQL Server Agent.</span></span>  
  
2.  <span data-ttu-id="5e248-134">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="5e248-134">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="5e248-135">Fare clic con il pulsante destro del mouse sulla cartella **Proxy** e scegliere **Nuovo proxy**.</span><span class="sxs-lookup"><span data-stu-id="5e248-135">Right-click the **Proxies** folder and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="5e248-136">Nella pagina **Generale** della finestra di dialogo **Nuovo account proxy** immettere il nome del nuovo account proxy nella casella **Nome proxy** .</span><span class="sxs-lookup"><span data-stu-id="5e248-136">On the **New Proxy Account** dialog box, on the **General** page, enter the name of the proxy account in the **Proxy name** box.</span></span>  
  
5.  <span data-ttu-id="5e248-137">Nella casella **Nome credenziali** immettere il nome delle credenziali di sicurezza che verranno utilizzate dall'account proxy.</span><span class="sxs-lookup"><span data-stu-id="5e248-137">In the **Credential name** box, enter the name of the security credential that the proxy account will use.</span></span>  
  
6.  <span data-ttu-id="5e248-138">Immettere una descrizione dell'account proxy nella casella **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="5e248-138">In the **Description** box, enter a description for the proxy account</span></span>  
  
7.  <span data-ttu-id="5e248-139">In **Attivo nei sottosistemi seguenti**, selezionare il sottosistema o i sottosistemi adatti per questo proxy.</span><span class="sxs-lookup"><span data-stu-id="5e248-139">Under **Active to the following subsystems**, select the appropriate subsystem or subsystems for this proxy.</span></span>  
  
8.  <span data-ttu-id="5e248-140">Nella pagina **Entità** aggiungere o rimuovere account di accesso oppure ruoli per concedere o negare l'accesso all'account proxy.</span><span class="sxs-lookup"><span data-stu-id="5e248-140">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
9. <span data-ttu-id="5e248-141">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e248-141">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5e248-142">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e248-142">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="5e248-143">Per creare un proxy di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="5e248-143">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="5e248-144">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e248-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e248-145">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5e248-145">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5e248-146">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5e248-146">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates credential CatalogApplicationCredential  
    USE msdb ;  
    GO  
    CREATE CREDENTIAL CatalogApplicationCredential WITH IDENTITY = 'REDMOND/TestUser',   
        SECRET = 'G3$1o)lkJ8HNd!';  
    GO  
    -- creates proxy "Catalog application proxy" and assigns the credential 'CatalogApplicationCredential' to it.  
    EXEC dbo.sp_add_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 1,  
        @description = 'Maintenance tasks on catalog application.',  
        @credential_name = 'CatalogApplicationCredential' ;  
    GO  
    -- grants the proxy "Catalog application proxy" access to the ActiveX Scripting subsystem.  
    EXEC dbo.sp_grant_proxy_to_subsystem  
        @proxy_name = N'Catalog application proxy',  
        @subsystem_id = 2 ;  
    GO  
    ```  
  
 <span data-ttu-id="5e248-147">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="5e248-147">For more information, see:</span></span>  
  
-   [<span data-ttu-id="5e248-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5e248-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="5e248-149">sp_add_proxy &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e248-149">sp_add_proxy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-proxy-transact-sql)  
  
-   [<span data-ttu-id="5e248-150">sp_grant_proxy_to_subsystem &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e248-150">sp_grant_proxy_to_subsystem &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-grant-proxy-to-subsystem-transact-sql)  
  
  
