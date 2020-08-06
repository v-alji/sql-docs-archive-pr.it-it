---
title: Avviare, arrestare o sospendere il servizio SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- SQL Server Agent, pausing
- SQL Server Agent, stopping
ms.assetid: c95a9759-dd30-4ab6-9ab0-087bb3bfb97c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2feb6a18c602271b1bec871fbfc9793979b100e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711568"
---
# <a name="start-stop-or-pause-the-sql-server-agent-service"></a><span data-ttu-id="945b4-102">Start, Stop, or Pause the SQL Server Agent Service</span><span class="sxs-lookup"><span data-stu-id="945b4-102">Start, Stop, or Pause the SQL Server Agent Service</span></span>
  <span data-ttu-id="945b4-103">In questo argomento viene illustrato come avviare, arrestare o riavviare il servizio SQL Server Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="945b4-103">This topic describes how to start, stop, or restart the SQL Server Agent Service in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="945b4-104">È possibile configurare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per l'avvio automatico all'avvio del sistema operativo oppure è possibile avviarlo manualmente quando è necessario completare processi.</span><span class="sxs-lookup"><span data-stu-id="945b4-104">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically when the operating system starts, or you can start it manually when you need to complete jobs.</span></span> <span data-ttu-id="945b4-105">È possibile arrestare o sospendere il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per sospendere processi, notifiche agli operatori e avvisi.</span><span class="sxs-lookup"><span data-stu-id="945b4-105">You can stop or pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to suspend jobs, operator notifications, and alerts.</span></span>  
  
 <span data-ttu-id="945b4-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="945b4-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="945b4-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="945b4-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="945b4-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="945b4-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="945b4-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="945b4-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="945b4-110">Per avviare, arrestare o riavviare il servizio SQL Server Agent utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="945b4-110">To start, stop, or restart the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="945b4-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="945b4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="945b4-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="945b4-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="945b4-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Per automatizzare le attività amministrative, è necessario che Agent sia in esecuzione come servizio.</span><span class="sxs-lookup"><span data-stu-id="945b4-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running as a service in order to automate administrative tasks.</span></span> <span data-ttu-id="945b4-114">Per altre informazioni, vedere [Configure SQL Server Agent](configure-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="945b4-114">For more information, see [Configure SQL Server Agent](configure-sql-server-agent.md).</span></span>  
  
-   <span data-ttu-id="945b4-115">In Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="945b4-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="945b4-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="945b4-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="945b4-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="945b4-117">Permissions</span></span>  
 <span data-ttu-id="945b4-118">Per la corretta esecuzione delle funzioni, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia configurato per utilizzare le credenziali di un account membro del ruolo predefinito del server **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="945b4-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="945b4-119">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="945b4-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="945b4-120">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="945b4-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="945b4-121">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="945b4-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="945b4-122">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="945b4-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="945b4-123">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="945b4-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="945b4-124">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="945b4-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="945b4-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="945b4-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-stop-or-restart-the-sql-server-agent-service"></a><span data-ttu-id="945b4-126">Per avviare, arrestare o riavviare il servizio SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="945b4-126">To start, stop, or restart the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="945b4-127">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera gestire il servizio SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="945b4-127">In **Object Explorer**, click the plus sign to expand the server where you want to manage SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="945b4-128">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, quindi selezionare **Avvia**, **Arresta**o **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="945b4-128">Right-click **SQL Server Agent**, and then select either **Start**, **Stop**, or **Restart**.</span></span>  
  
3.  <span data-ttu-id="945b4-129">Nella finestra di dialogo **Controllo dell'account utente** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="945b4-129">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="945b4-130">Se viene richiesto di eseguire l'azione, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="945b4-130">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
 <span data-ttu-id="945b4-131">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="945b4-131">For more information, see:</span></span>  
  
-   [<span data-ttu-id="945b4-132">Avviare, arrestare, sospendere, riprendere, riavviare il motore di database, SQL Server Agent o SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="945b4-132">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
-   [<span data-ttu-id="945b4-133">Avvio automatico di SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="945b4-133">Autostart SQL Server Agent &#40;SQL Server Management Studio&#41;</span></span>](autostart-sql-server-agent-sql-server-management-studio.md)  
  
  
