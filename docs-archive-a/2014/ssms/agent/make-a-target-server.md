---
title: Configurare un server di destinazione| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.tsxwiz.msx.f1
- sql12.ag.tsxwiz.cover.f1
- sql12.ag.tsxwiz.credentials.f1
- sql12.ag.tsxwiz.complete.f1
helpviewer_keywords:
- Target Server Wizard
- SQL Server Agent jobs, target servers
- target servers [SQL Server], creating
ms.assetid: 13aabe2d-67fe-4c67-8d49-2928dd705b7a
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd60a19234d186bb0912978589fa60fd8e8a8c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711580"
---
# <a name="make-a-target-server"></a><span data-ttu-id="a57e6-102">Configurare un server di destinazione</span><span class="sxs-lookup"><span data-stu-id="a57e6-102">Make a Target Server</span></span>
  <span data-ttu-id="a57e6-103">In questo argomento viene descritto come configurare un server di destinazione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o SQL Server Management Objects (SMO).</span><span class="sxs-lookup"><span data-stu-id="a57e6-103">This topic describes how to make a target server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="a57e6-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a57e6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a57e6-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a57e6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a57e6-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a57e6-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a57e6-107">**Per configurare un server di destinazione utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="a57e6-107">**To make a target server, using:**</span></span>  
  
     [<span data-ttu-id="a57e6-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a57e6-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a57e6-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a57e6-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a57e6-110">SMO</span><span class="sxs-lookup"><span data-stu-id="a57e6-110">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a57e6-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a57e6-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a57e6-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a57e6-112">Security</span></span>  
 <span data-ttu-id="a57e6-113">I processi distribuiti con passaggi associati a un proxy vengono eseguiti nel contesto dell'account proxy nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a57e6-113">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="a57e6-114">Verificare che siano soddisfatte le condizioni seguenti, per assicurare che i passaggi di processo associati a un proxy vengano scaricati dal server master a quello di destinazione:</span><span class="sxs-lookup"><span data-stu-id="a57e6-114">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="a57e6-115">La sottochiave del registro di sistema del server master **\ HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Microsoft SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) è impostata su 1 (true).</span><span class="sxs-lookup"><span data-stu-id="a57e6-115">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="a57e6-116">Per impostazione predefinita, questa sottochiave è impostata su 0 (False).</span><span class="sxs-lookup"><span data-stu-id="a57e6-116">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="a57e6-117">Nel server di destinazione deve esistere un account proxy con lo stesso nome dell'account proxy del server master utilizzato per l'esecuzione del passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="a57e6-117">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="a57e6-118">Se si verificano errori nel download dei passaggi dei processi che usano account proxy dal server master a quello di destinazione, è possibile controllare se nella colonna **error_message** della tabella **sysdownloadlist** nel database **msdb** sono presenti i messaggi di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="a57e6-118">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="a57e6-119">"Per questo passaggio del processo è necessario un account proxy, ma l'individuazione dei proxy è disabilitata nel server di destinazione."</span><span class="sxs-lookup"><span data-stu-id="a57e6-119">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="a57e6-120">Per risolvere il problema, impostare la sottochiave del Registro di sistema **AllowDownloadedJobsToMatchProxyName** su 1.</span><span class="sxs-lookup"><span data-stu-id="a57e6-120">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="a57e6-121">"Impossibile trovare il proxy."</span><span class="sxs-lookup"><span data-stu-id="a57e6-121">"Proxy not found."</span></span>  
  
     <span data-ttu-id="a57e6-122">Per risolvere il problema, verificare che nel server di destinazione sia disponibile un account proxy con lo stesso nome dell'account proxy del server master utilizzato per l'esecuzione del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="a57e6-122">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a57e6-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a57e6-123">Permissions</span></span>  
 <span data-ttu-id="a57e6-124">Le autorizzazioni di esecuzione per questa procedura vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="a57e6-124">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a57e6-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a57e6-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="a57e6-126">Per configurare un server di destinazione</span><span class="sxs-lookup"><span data-stu-id="a57e6-126">To make a target server</span></span>  
  
1.  <span data-ttu-id="a57e6-127">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="a57e6-127">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a57e6-128">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Amministrazione multiserver**e fare clic su **Imposta come server di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="a57e6-128">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Target**.</span></span> <span data-ttu-id="a57e6-129">**Configurazione guidata server di destinazione** consente di eseguire in modo semplificato i passaggi necessari per configurare un server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a57e6-129">The **Target Server Wizard** guides you through the process of making a target server.</span></span>  
  
3.  <span data-ttu-id="a57e6-130">Nella pagina **Selezione server master** selezionare il server master dal quale il server di destinazione corrente riceverà i processi.</span><span class="sxs-lookup"><span data-stu-id="a57e6-130">From the **Select a Master Server** page, select the master server that this target server will receive jobs from.</span></span>  
  
     <span data-ttu-id="a57e6-131">**Seleziona server**</span><span class="sxs-lookup"><span data-stu-id="a57e6-131">**Pick Server**</span></span>  
     <span data-ttu-id="a57e6-132">Tramite questa opzione è possibile connettersi al server master.</span><span class="sxs-lookup"><span data-stu-id="a57e6-132">Connect to the master server.</span></span>  
  
     <span data-ttu-id="a57e6-133">**Descrizione del server**</span><span class="sxs-lookup"><span data-stu-id="a57e6-133">**Description of this server**</span></span>  
     <span data-ttu-id="a57e6-134">Consente di digitare una descrizione del server di destinazione corrente.</span><span class="sxs-lookup"><span data-stu-id="a57e6-134">Type a description for this target server.</span></span> <span data-ttu-id="a57e6-135">Tale descrizione verrà caricata sul server master dal server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a57e6-135">The target server uploads this description to the master server.</span></span>  
  
4.  <span data-ttu-id="a57e6-136">Nella pagina **Credenziali account di accesso al server master** creare un nuovo account di accesso al server di destinazione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="a57e6-136">From the **Master Server Login Credentials** page, create a new login on the target server, if necessary.</span></span>  
  
     <span data-ttu-id="a57e6-137">**Crea un nuovo account di accesso se necessario e assegna i diritti per il server MSX**</span><span class="sxs-lookup"><span data-stu-id="a57e6-137">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="a57e6-138">Tramite questa opzione è possibile creare un nuovo account di accesso nel server di destinazione se l'account di accesso specificato non esiste già.</span><span class="sxs-lookup"><span data-stu-id="a57e6-138">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a57e6-139">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a57e6-139">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="a57e6-140">Per configurare un server di destinazione</span><span class="sxs-lookup"><span data-stu-id="a57e6-140">To make a target server</span></span>  
  
1.  <span data-ttu-id="a57e6-141">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a57e6-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a57e6-142">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a57e6-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a57e6-143">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a57e6-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a57e6-144">In questo esempio il server corrente viene integrato nel server master AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="a57e6-144">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="a57e6-145">L'ubicazione del server corrente è Building 21, Room 309, Rack 5.</span><span class="sxs-lookup"><span data-stu-id="a57e6-145">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
        N'Building 21, Room 309, Rack 5' ;   
    GO;  
    ```  
  
     <span data-ttu-id="a57e6-146">Per ulteriori informazioni, vedere [sp_msx_enlist &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a57e6-146">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="a57e6-147">Utilizzo di SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="a57e6-147">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a57e6-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a57e6-148">See Also</span></span>  
 [<span data-ttu-id="a57e6-149">Amministrazione automatizzata in un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a57e6-149">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
