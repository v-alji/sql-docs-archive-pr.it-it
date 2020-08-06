---
title: Configurare SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, configuring
- accounts [SQL Server], SQL Server Agent
- SQL Server Agent, permissions
- security [SQL Server], SQL Server Agent
ms.assetid: 2e361a62-9e92-4fcd-80d7-d6960f127900
author: stevestein
ms.author: sstein
ms.openlocfilehash: 81c78faf733fac5ffb9a6e74dbf03f8caaff03d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628069"
---
# <a name="configure-sql-server-agent"></a><span data-ttu-id="241fb-102">Configurazione di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="241fb-102">Configure SQL Server Agent</span></span>
  <span data-ttu-id="241fb-103">In questo argomento viene descritto come specificare alcune opzioni di configurazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="241fb-103">This topic describes how to specify some configuration options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent during installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="241fb-104">Il set completo di opzioni di configurazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent è disponibile solo in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) o nelle stored procedure di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="241fb-104">The full set of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent configuration options is only available within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO), or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures.</span></span>  
  
 <span data-ttu-id="241fb-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="241fb-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="241fb-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="241fb-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="241fb-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="241fb-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="241fb-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="241fb-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="241fb-109">Per configurare SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="241fb-109">To configure SQL Server Agent</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="241fb-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="241fb-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="241fb-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="241fb-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="241fb-112">Fare clic su **SQL Server Agent** in Esplora oggetti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per gestire processi, operatori, avvisi e il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="241fb-112">Click **SQL Server Agent** in Object Explorer of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to administer jobs, operators, alerts, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="241fb-113">Tuttavia, in Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione a utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="241fb-113">However, Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="241fb-114">Non è possibile abilitare il riavvio automatico per il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent nelle istanze del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="241fb-114">Auto-restart should not be enabled for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on failover cluster instances.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="241fb-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="241fb-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="241fb-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="241fb-116">Permissions</span></span>  
 <span data-ttu-id="241fb-117">Per la corretta esecuzione delle funzioni, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia configurato per utilizzare le credenziali di un account membro del ruolo predefinito del server **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="241fb-117">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="241fb-118">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="241fb-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="241fb-119">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="241fb-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="241fb-120">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="241fb-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="241fb-121">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="241fb-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="241fb-122">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="241fb-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="241fb-123">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="241fb-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="241fb-124">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="241fb-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent"></a><span data-ttu-id="241fb-125">Per configurare SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="241fb-125">To configure SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="241fb-126">Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**  dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="241fb-126">Click the **Start** button, and then, on the **Start**  menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="241fb-127">Nel Pannello di controllo fare clic su **Sistema e sicurezza**, scegliere **Strumenti di amministrazione**, quindi **Criteri di sicurezza locali**.</span><span class="sxs-lookup"><span data-stu-id="241fb-127">In Control Panel, click **System and Security**, click **Administrative Tools**, and then select **Local Security Policy**.</span></span>  
  
3.  <span data-ttu-id="241fb-128">In Criteri di sicurezza locale fare clic sulle virgolette per espandere la cartella **Criteri locali** , quindi scegliere la cartella **Assegnazione diritti utente** .</span><span class="sxs-lookup"><span data-stu-id="241fb-128">In Local Security Policy, click the chevron to expand the **Local Policies** folder, and then click the **User Rights Assignment** folder.</span></span>  
  
4.  <span data-ttu-id="241fb-129">Fare clic con il pulsante destro del mouse su un'autorizzazione da configurare per l'uso con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="241fb-129">Right-click a permission that you want to configure for use with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="241fb-130">Nella finestra di dialogo delle proprietà dell'autorizzazione, verificare che sia elencato l'account con cui viene eseguito [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="241fb-130">In the permission's properties dialog box, verify that the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs is listed.</span></span> <span data-ttu-id="241fb-131">In caso contrario, fare clic su **Aggiungi utente o gruppo**, immettere l'account con cui viene eseguito [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent nella finestra di dialogo **Selezione utenti, computer, account del servizio o gruppi** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="241fb-131">If not, click **Add User or Group**, enter the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs in the **Select Users, Computers, Service Accounts, or Groups** dialog box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="241fb-132">Ripetere per ogni autorizzazione da aggiungere per l'esecuzione con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="241fb-132">Repeat for each permission that you want to add to run with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="241fb-133">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="241fb-133">When finished, click **OK**.</span></span>  
  
  
