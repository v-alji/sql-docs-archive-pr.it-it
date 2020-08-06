---
title: Impostare l'account di avvio del servizio per SQL Server Agent (Gestione configurazione SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- startup accounts [SQL Server]
- service startup accounts [SQL Server Agent]
ms.assetid: 46ffe818-ebb5-43a0-840b-923f219a2472
author: stevestein
ms.author: sstein
ms.openlocfilehash: 63e5ba7c24f1aa1a3f79f80e5ca28c02a0cd5812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715003"
---
# <a name="set-the-service-startup-account-for-sql-server-agent-sql-server-configuration-manager"></a><span data-ttu-id="6e6f5-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="6e6f5-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="6e6f5-103">L'account di avvio del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent definisce l'account di Windows con cui viene eseguito [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e le relative autorizzazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account defines the Windows account that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs as, as well as its network permissions.</span></span> <span data-ttu-id="6e6f5-104">In questo argomento viene descritto come impostare l'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent con Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e6f5-104">This topic describes how to set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6e6f5-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6e6f5-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6e6f5-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="6e6f5-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6e6f5-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6e6f5-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6e6f5-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e6f5-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="6e6f5-109">Per impostare l'account di avvio del servizio per SQL Server Agent tramite SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e6f5-109">To set the Service Startup Account for SQL Server Agent using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6e6f5-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6e6f5-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6e6f5-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6e6f5-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6e6f5-112">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], non è più necessario che l'account di avvio del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia un membro del gruppo Administrators di [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e6f5-112">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer requires that the service startup account be a member of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Administrators group.</span></span> <span data-ttu-id="6e6f5-113">L'account di avvio del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve tuttavia essere membro del ruolo predefinito del server [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sysadmin.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-113">However, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account must be a member of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sysadmin fixed server role.</span></span> <span data-ttu-id="6e6f5-114">Per usare l'elaborazione dei processi multiserver, l'account deve essere un membro del ruolo TargetServersRole del database msdb nel server master.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-114">The account must also be a member of the msdb database role TargetServersRole on the master server if multiserver job processing is used.</span></span>  
  
-   <span data-ttu-id="6e6f5-115">In Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6e6f5-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6e6f5-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6e6f5-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6e6f5-117">Permissions</span></span>  
 <span data-ttu-id="6e6f5-118">Per eseguire le funzioni, è [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] necessario configurare Agent in modo che utilizzi le credenziali di un account membro del `sysadmin` ruolo predefinito del server in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e6f5-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the `sysadmin` fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6e6f5-119">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e6f5-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="6e6f5-120">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="6e6f5-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="6e6f5-121">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="6e6f5-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="6e6f5-122">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="6e6f5-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="6e6f5-123">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="6e6f5-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="6e6f5-124">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6e6f5-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6e6f5-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e6f5-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-service-startup-account-for-sql-server-agent"></a><span data-ttu-id="6e6f5-126">Per impostare l'account di avvio del servizio SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="6e6f5-126">To set the Service Startup Account for SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="6e6f5-127">In **Server registrati**, fare clic sul segno più per espandere **Motore di database**.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-127">In **Registered Servers**, click the plus sign to expand **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="6e6f5-128">Fare clic sul segno più per espandere la cartella **Gruppi di server locali** .</span><span class="sxs-lookup"><span data-stu-id="6e6f5-128">Click the plus sign to expand the **Local Server Groups** folder.</span></span>  
  
3.  <span data-ttu-id="6e6f5-129">Fare clic con il pulsante destro del mouse sull'istanza del server dove si intende impostare l'account di avvio del servizio e selezionare **Gestione configurazione SQL Server...**.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-129">Right-click the server instance where you want set up the Service Startup Account, and select **SQL Server Configuration Manager...**.</span></span>  
  
4.  <span data-ttu-id="6e6f5-130">Nella finestra di dialogo **Controllo dell'account utente** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-130">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="6e6f5-131">Nel riquadro della console di Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , selezionare **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-131">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, select **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="6e6f5-132">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse su **SQL Server Agent**_(nome_server)_, dove *nome_server* è il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per cui si vuole modificare l'account di avvio del servizio e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-132">In the details pane, right-click **SQL Server Agent**_(server_name)_, where *server_name* is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance for which you want to change the service startup account, and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="6e6f5-133">Nella finestra di dialogo **proprietà** **SQL Server Agent**_(server_name)_ , nella scheda **accesso** , selezionare una delle seguenti opzioni in **Accedi come**:</span><span class="sxs-lookup"><span data-stu-id="6e6f5-133">In the **SQL Server Agent**_(server_name)_ **Properties** dialog box, in the **Log On** tab, select one of the following options under **Log on as**:</span></span>  
  
    -   <span data-ttu-id="6e6f5-134">**Account predefinito**: selezionare questa opzione se i processi usano solo risorse del server locale.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-134">**Built-in account**: select this option if your jobs require resources from the local server only.</span></span> <span data-ttu-id="6e6f5-135">Per informazioni sulla selezione di un account predefinito di Windows, vedere [Selezionare un account per il servizio SQL Server Agent](https://msdn.microsoft.com/library/ms191543.aspx).</span><span class="sxs-lookup"><span data-stu-id="6e6f5-135">For information about how to choose a Windows built-in account type, see [Selecting an Account for SQL Server Agent Service.](https://msdn.microsoft.com/library/ms191543.aspx)</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="6e6f5-136"> Il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non supporta l'account **Servizio locale** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e6f5-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service does not support the **Local Service** account in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="6e6f5-137">**Account seguente**: selezionare questa opzione se i processi richiedono risorse dalla rete, incluse le risorse dell'applicazione, per inoltrare eventi ad altri registri applicazioni di Windows oppure se per inviare una notifica agli operatori tramite messaggi di posta elettronica o cercapersone.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-137">**This account**: select this option if your jobs require resources across the network, including application resources; if you want to forward events to other Windows application logs; or if you want to notify operators through e-mail or pagers.</span></span>  
  
         <span data-ttu-id="6e6f5-138">Se si seleziona questa opzione:</span><span class="sxs-lookup"><span data-stu-id="6e6f5-138">If you select this option:</span></span>  
  
        1.  <span data-ttu-id="6e6f5-139">Nella casella **Nome account** , immettere l'account che sarà utilizzato per eseguire SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-139">In the **Account Name** box, enter the account that will be used to run SQL Server Agent.</span></span> <span data-ttu-id="6e6f5-140">In alternativa, fare clic su **Sfoglia** per aprire la finestra di dialogo **Seleziona utente o gruppo** e selezionare l'account da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-140">Alternately, click **Browse** to open the **Select User or Group** dialog box and select the account to use.</span></span>  
  
        2.  <span data-ttu-id="6e6f5-141">Immettere nella casella **Password** la password per l'account.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-141">In the **Password** box, enter the password for the account.</span></span> <span data-ttu-id="6e6f5-142">Immettere nuovamente la password nella casella **Conferma password** .</span><span class="sxs-lookup"><span data-stu-id="6e6f5-142">Re-enter the password in the **Confirm password** box.</span></span>  
  
8.  <span data-ttu-id="6e6f5-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-143">Click **OK**.</span></span>  
  
9. <span data-ttu-id="6e6f5-144">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Fare clic sul pulsante **Chiudi** in Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="6e6f5-144">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click the **Close** button.</span></span>  
  
  
