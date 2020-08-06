---
title: Configurare un server master | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.msxwiz.complete.f1
- sql12.ag.msxwiz.target.f1
- sql12.ag.msxwiz.login.f1
- sql12.ag.msxwiz.cover.f1
- sql12.ag.msxwiz.operator.f1
helpviewer_keywords:
- master servers [SQL Server], creating
- wizards [SQL Server Management Studio], Master Server Wizard
- SQL Server Agent jobs, master servers
- Master Server Wizard
ms.assetid: 05739a73-1fdf-4d9d-92a6-70f328380322
author: stevestein
ms.author: sstein
ms.openlocfilehash: ce8e7428aaf8ba459bcf6831988c61da3f192bac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628062"
---
# <a name="make-a-master-server"></a><span data-ttu-id="1979b-102">Make a Master Server</span><span class="sxs-lookup"><span data-stu-id="1979b-102">Make a Master Server</span></span>
  <span data-ttu-id="1979b-103">In questo argomento viene descritto come configurare un server master [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1979b-103">This topic describes how to make a master server [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1979b-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="1979b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1979b-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="1979b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1979b-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1979b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1979b-107">**Per configurare un server master tramite:**</span><span class="sxs-lookup"><span data-stu-id="1979b-107">**To make a master server, using:**</span></span>  
  
     [<span data-ttu-id="1979b-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1979b-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1979b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1979b-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1979b-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1979b-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1979b-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1979b-111">Security</span></span>  
 <span data-ttu-id="1979b-112">I processi distribuiti con passaggi associati a un proxy vengono eseguiti nel contesto dell'account proxy nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1979b-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="1979b-113">Verificare che siano soddisfatte le condizioni seguenti, per assicurare che i passaggi di processo associati a un proxy vengano scaricati dal server master a quello di destinazione:</span><span class="sxs-lookup"><span data-stu-id="1979b-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="1979b-114">La sottochiave del registro di sistema del server master **\ HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Microsoft SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) è impostata su 1 (true).</span><span class="sxs-lookup"><span data-stu-id="1979b-114">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="1979b-115">Per impostazione predefinita, questa sottochiave è impostata su 0 (False).</span><span class="sxs-lookup"><span data-stu-id="1979b-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="1979b-116">Nel server di destinazione deve esistere un account proxy con lo stesso nome dell'account proxy del server master utilizzato per l'esecuzione del passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="1979b-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="1979b-117">Se si verificano errori nel download dei passaggi dei processi che usano account proxy dal server master a quello di destinazione, è possibile controllare se nella colonna **error_message** della tabella **sysdownloadlist** nel database **msdb** sono presenti i messaggi di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="1979b-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="1979b-118">"Per questo passaggio del processo è necessario un account proxy, ma l'individuazione dei proxy è disabilitata nel server di destinazione."</span><span class="sxs-lookup"><span data-stu-id="1979b-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="1979b-119">Per risolvere il problema, impostare la sottochiave del Registro di sistema **AllowDownloadedJobsToMatchProxyName** su 1.</span><span class="sxs-lookup"><span data-stu-id="1979b-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="1979b-120">"Impossibile trovare il proxy."</span><span class="sxs-lookup"><span data-stu-id="1979b-120">"Proxy not found."</span></span>  
  
     <span data-ttu-id="1979b-121">Per risolvere il problema, verificare che nel server di destinazione sia disponibile un account proxy con lo stesso nome dell'account proxy del server master utilizzato per l'esecuzione del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="1979b-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1979b-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1979b-122">Permissions</span></span>  
 <span data-ttu-id="1979b-123">Le autorizzazioni di esecuzione per questa procedura vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="1979b-123">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1979b-124">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1979b-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="1979b-125">Per configurare un server master</span><span class="sxs-lookup"><span data-stu-id="1979b-125">To make a master server</span></span>  
  
1.  <span data-ttu-id="1979b-126">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="1979b-126">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1979b-127">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Amministrazione multiserver**e quindi fare clic su **Imposta come server master**.</span><span class="sxs-lookup"><span data-stu-id="1979b-127">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Master**.</span></span> <span data-ttu-id="1979b-128">**Configurazione guidata server master** consente di eseguire in modo semplificato i passaggi necessari per configurare un server master e aggiungere server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1979b-128">The **Master Server Wizard** guides you through the process of making a master server and adding target servers.</span></span>  
  
3.  <span data-ttu-id="1979b-129">Nella pagina **Operatore server master** configurare un operatore per il server master. Per l'invio di notifiche agli operatori via posta elettronica o cercapersone, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia configurato per l'invio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1979b-129">From the **Master Server Operator** page, configure an operator for the master server To send notifications to operators by using e-mail or pagers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to send e-mail.</span></span> <span data-ttu-id="1979b-130">Per inviare notifiche agli operatori con **net send**, il servizio Messenger deve essere in esecuzione nel server in cui si trova [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="1979b-130">To send notifications to operators by using **net send**, the Messenger service must be running on the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent resides.</span></span>  
  
     <span data-ttu-id="1979b-131">**Indirizzo di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="1979b-131">**E-mail address**</span></span>  
     <span data-ttu-id="1979b-132">Imposta l'indirizzo di posta elettronica dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="1979b-132">Sets the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="1979b-133">**Indirizzo cercapersone**</span><span class="sxs-lookup"><span data-stu-id="1979b-133">**Pager address**</span></span>  
     <span data-ttu-id="1979b-134">Imposta l'indirizzo di posta elettronica del cercapersone dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="1979b-134">Sets the pager e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="1979b-135">**Indirizzo Net Send**</span><span class="sxs-lookup"><span data-stu-id="1979b-135">**Net send address**</span></span>  
     <span data-ttu-id="1979b-136">Imposta l'indirizzo **net send** dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="1979b-136">Sets the **net send** address for the operator.</span></span>  
  
4.  <span data-ttu-id="1979b-137">Nella pagina **Server di destinazione** selezionare i server di destinazione per il server master.</span><span class="sxs-lookup"><span data-stu-id="1979b-137">From the **Target Server** page, select target servers for the master server.</span></span>  
  
     <span data-ttu-id="1979b-138">**Server registrati**</span><span class="sxs-lookup"><span data-stu-id="1979b-138">**Registered Servers**</span></span>  
     <span data-ttu-id="1979b-139">Elenca i server registrati in Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] che non sono già server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1979b-139">Lists the servers registered in Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] that are not already target servers.</span></span>  
  
     <span data-ttu-id="1979b-140">**Server di destinazione**</span><span class="sxs-lookup"><span data-stu-id="1979b-140">**Target Servers**</span></span>  
     <span data-ttu-id="1979b-141">Elenca i server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1979b-141">Lists the servers that are target servers.</span></span>  
  
     **>**  
     <span data-ttu-id="1979b-142">Consente di spostare il server selezionato nell'elenco dei server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1979b-142">Move the selected server to the target server list.</span></span>  
  
     **>>**  
     <span data-ttu-id="1979b-143">Consente di spostare tutti i server nell'elenco dei server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1979b-143">Move all servers to the target server list.</span></span>  
  
     **<**  
     <span data-ttu-id="1979b-144">Consente di eliminare il server selezionato dall'elenco dei server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1979b-144">Remove the selected server from the target server list.</span></span>  
  
     **<<**  
     <span data-ttu-id="1979b-145">Consente di eliminare tutti i server dall'elenco dei server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1979b-145">Remove all servers from the target server list.</span></span>  
  
     <span data-ttu-id="1979b-146">**Aggiungi connessione**</span><span class="sxs-lookup"><span data-stu-id="1979b-146">**Add connection**</span></span>  
     <span data-ttu-id="1979b-147">Consente di aggiungere un server all'elenco dei server di destinazione senza registrarlo.</span><span class="sxs-lookup"><span data-stu-id="1979b-147">Add a server to the target server list without registering the server.</span></span>  
  
     <span data-ttu-id="1979b-148">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1979b-148">**Connection**</span></span>  
     <span data-ttu-id="1979b-149">Modificare le proprietà di connessione per il server selezionato.</span><span class="sxs-lookup"><span data-stu-id="1979b-149">Change the connection properties for the selected server.</span></span>  
  
5.  <span data-ttu-id="1979b-150">Nella pagina **Credenziali account di accesso al server master** specificare se si desidera creare un nuovo account di accesso per il server di destinazione, se necessario, e assegnare a tale account di accesso i diritti per il server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1979b-150">From the **Master Server Login Credentials** page to specify if you want to create a new login for the target server, if necessary, and assign it rights to the master server.</span></span>  
  
     <span data-ttu-id="1979b-151">**Crea un nuovo account di accesso se necessario e assegna i diritti per il server MSX**</span><span class="sxs-lookup"><span data-stu-id="1979b-151">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="1979b-152">Tramite questa opzione è possibile creare un nuovo account di accesso nel server di destinazione se l'account di accesso specificato non esiste già.</span><span class="sxs-lookup"><span data-stu-id="1979b-152">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1979b-153">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1979b-153">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="1979b-154">Per configurare un server master</span><span class="sxs-lookup"><span data-stu-id="1979b-154">To make a master server</span></span>  
  
1.  <span data-ttu-id="1979b-155">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1979b-155">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1979b-156">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="1979b-156">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1979b-157">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1979b-157">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1979b-158">In questo esempio il server corrente viene integrato nel server master AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="1979b-158">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="1979b-159">L'ubicazione del server corrente è Building 21, Room 309, Rack 5.</span><span class="sxs-lookup"><span data-stu-id="1979b-159">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
    N'Building 21, Room 309, Rack 5' ;   
GO;  
```  
  
 <span data-ttu-id="1979b-160">Per ulteriori informazioni, vedere [sp_msx_enlist &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1979b-160">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1979b-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1979b-161">See Also</span></span>  
 <span data-ttu-id="1979b-162">[Creazione di un ambiente multiserver](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="1979b-162">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 [<span data-ttu-id="1979b-163">Amministrazione automatizzata in un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1979b-163">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
