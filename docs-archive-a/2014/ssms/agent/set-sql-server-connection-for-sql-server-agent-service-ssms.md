---
title: Impostare la connessione SQL Server per il servizio di SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, connections
- connections [SQL Server], SQL Server Agent service
ms.assetid: 28b6178b-0a9e-4f2c-8562-7a62d2d2a285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30f68967d6bdb8b0495cbddb1a5b0bd447cd5168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638229"
---
# <a name="set-the-sql-server-connection-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="5adfe-102">Set the SQL Server Connection for the SQL Server Agent Service (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5adfe-102">Set the SQL Server Connection for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5adfe-103">In questo argomento viene illustrato come impostare la connessione tra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e [!INCLUDE[ssDE](../../includes/ssde-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5adfe-103">This topic describes how to set the connection between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5adfe-104">Per la connessione a un'istanza locale di SQL Server il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent può utilizzare Autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="5adfe-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can connect to a local instance of SQL Server by using Windows Authentication.</span></span>  
  
 <span data-ttu-id="5adfe-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5adfe-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5adfe-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5adfe-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5adfe-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5adfe-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5adfe-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5adfe-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5adfe-109">**Per impostare Connessione SQL Server per SQL Server Agent tramite:**</span><span class="sxs-lookup"><span data-stu-id="5adfe-109">**To set the SQL Server Connection for the SQL Server Agent, using:**</span></span>  
  
     [<span data-ttu-id="5adfe-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5adfe-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5adfe-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5adfe-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5adfe-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5adfe-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5adfe-113">In Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="5adfe-113">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="5adfe-114">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è supportata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5adfe-114">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="5adfe-115">Questa opzione è disponibile solo quando si amministra una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5adfe-115">This option is available only when you administer an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5adfe-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5adfe-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5adfe-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5adfe-117">Permissions</span></span>  
 <span data-ttu-id="5adfe-118">Per la corretta esecuzione delle funzioni, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia configurato per utilizzare le credenziali di un account membro del ruolo predefinito del server **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5adfe-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5adfe-119">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="5adfe-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="5adfe-120">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="5adfe-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="5adfe-121">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="5adfe-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="5adfe-122">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="5adfe-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="5adfe-123">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="5adfe-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="5adfe-124">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5adfe-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5adfe-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5adfe-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-sql-server-connection"></a><span data-ttu-id="5adfe-126">Per impostare la connessione a SQL Server</span><span class="sxs-lookup"><span data-stu-id="5adfe-126">To set the SQL Server connection</span></span>  
  
1.  <span data-ttu-id="5adfe-127">In **Esplora oggetti**fare clic sul segno più per espandere il server che si desidera impostare con una connessione al servizio SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="5adfe-127">In **Object Explorer**, click the plus sign to expand the server that you want to set up with a connection to its SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="5adfe-128">Fare clic con il pulsante destro del mouse su **SQL Server Agent** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5adfe-128">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="5adfe-129">Nella finestra di dialogo **Proprietà SQL Server Agent** fare clic su **Connessione** in **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="5adfe-129">In the **SQL Server Agent Properties** dialog box, under **Select a page**, click **Connection**.</span></span>  
  
4.  <span data-ttu-id="5adfe-130">In **Connessione SQL Server** selezionare **Usa autenticazione di Windows** per abilitare la connessione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a un'istanza del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] con l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="5adfe-130">Under **SQL Server connection**, select **Use Windows Authentication** to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="5adfe-131">Per le connessioni ai database di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive è necessario utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="5adfe-131">Connections to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later databases require Windows Authentication.</span></span>  
  
  
