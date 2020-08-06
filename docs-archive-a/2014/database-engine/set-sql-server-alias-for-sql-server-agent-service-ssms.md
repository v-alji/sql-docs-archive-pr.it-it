---
title: Impostare un alias di SQL Server per il servizio di SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], creating
- SQL Server Agent, aliases
ms.assetid: 02d6295d-ab52-44f0-8f1b-f3910a507d8f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b178d91a47d907b182ef7962b98c7f22d4454094
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624324"
---
# <a name="set-a-sql-server-alias-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="29cc1-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="29cc1-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="29cc1-103">In questo argomento viene descritto come impostare un [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent da utilizzare per la connessione a utilizzando [!INCLUDE[ssDE](../includes/ssde-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29cc1-103">This topic describes how to set a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to use to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="29cc1-104">Per impostazione predefinita, il servizio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent si connette a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] mediante named pipe utilizzando nomi di server dinamici che non richiedono alcuna configurazione client aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="29cc1-104">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] over named pipes by using dynamic server names that require no additional client configuration.</span></span> <span data-ttu-id="29cc1-105">La configurazione di un alias di connessione del server è necessaria solo se non si utilizza il trasporto di rete predefinito o se ci si connette a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] che rimane in attesa su un'altra named pipe.</span><span class="sxs-lookup"><span data-stu-id="29cc1-105">You need to configure a server connection alias only if you are not using the default network transport or if you are connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="29cc1-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="29cc1-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="29cc1-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="29cc1-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="29cc1-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="29cc1-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="29cc1-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="29cc1-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="29cc1-110">Per impostare un alias SQL Server per il servizio SQL Server Agent utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29cc1-110">To set a SQL Server Alias for the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29cc1-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="29cc1-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="29cc1-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="29cc1-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="29cc1-113">Agent non funzionerà correttamente se non si seleziona un alias che fa riferimento all'istanza locale di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29cc1-113">Agent will not work correctly unless you select an alias that refers to the local instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="29cc1-114">In Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="29cc1-114">Object Explorer only displays the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29cc1-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="29cc1-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="29cc1-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="29cc1-116">Permissions</span></span>  
 <span data-ttu-id="29cc1-117">Per la corretta esecuzione delle funzioni, è necessario che [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent sia configurato per utilizzare le credenziali di un account membro del ruolo predefinito del server **sysadmin** in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29cc1-117">To perform its functions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="29cc1-118">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="29cc1-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="29cc1-119">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="29cc1-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="29cc1-120">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="29cc1-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="29cc1-121">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="29cc1-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="29cc1-122">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="29cc1-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="29cc1-123">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="29cc1-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="29cc1-124">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29cc1-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-sql-server-alias-for-the-sql-server-agent-service"></a><span data-ttu-id="29cc1-125">Per impostare un alias SQL Server per il servizio SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="29cc1-125">To set a SQL Server Alias for the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="29cc1-126">In **Esplora oggetti**connettersi a un'istanza di [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] e quindi espandere tale istanza.</span><span class="sxs-lookup"><span data-stu-id="29cc1-126">In the **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="29cc1-127">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="29cc1-127">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="29cc1-128">Nella finestra di dialogo **proprietà SQL Server Agent**_server_name_ fare clic su **connessione**in **Selezione pagina**e</span><span class="sxs-lookup"><span data-stu-id="29cc1-128">In the **SQL Server Agent Properties**_server_name_ dialog box, under **Select a page**, select **Connection**, and</span></span>  
  
4.  <span data-ttu-id="29cc1-129">Nella casella **Alias server host locale** , digitare l'alias del server a cui si deve connettere [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="29cc1-129">In the **Alias local host server** box, type the alias of the server to which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should connect.</span></span>  
  
5.  <span data-ttu-id="29cc1-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="29cc1-130">Click **OK**.</span></span>  
  
  
