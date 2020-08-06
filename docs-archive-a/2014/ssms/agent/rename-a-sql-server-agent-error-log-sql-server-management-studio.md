---
title: Rinominare un log degli errori di SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- renaming SQL Server Agent error log
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: dee2b199-48af-44cb-9177-d029a5edb169
author: stevestein
ms.author: sstein
ms.openlocfilehash: c1c85550a29bfff316ffc275ba2d4e4df10686d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637558"
---
# <a name="rename-a-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="9c7cc-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9c7cc-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="9c7cc-103">In questo argomento viene descritto come rinominare il file [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui vengono scritti gli errori di Agent in utilizzando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c7cc-103">This topic describes how to rename the file where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent errors are written in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9c7cc-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="9c7cc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9c7cc-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="9c7cc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9c7cc-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="9c7cc-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9c7cc-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9c7cc-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="9c7cc-108">Per rinominare un log degli errori di SQL Server Agent utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c7cc-108">To rename a SQL Server Agent error log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9c7cc-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9c7cc-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9c7cc-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="9c7cc-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9c7cc-111">In Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="9c7cc-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9c7cc-112">Agent vengono scritti nel nuovo file solo dopo il riavvio del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="9c7cc-112">Agent will not write to the new log file until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is restarted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9c7cc-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9c7cc-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9c7cc-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="9c7cc-114">Permissions</span></span>  
 <span data-ttu-id="9c7cc-115">Per la corretta esecuzione delle funzioni, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia configurato per utilizzare le credenziali di un account membro del ruolo predefinito del server **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c7cc-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9c7cc-116">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c7cc-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="9c7cc-117">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="9c7cc-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="9c7cc-118">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="9c7cc-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="9c7cc-119">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="9c7cc-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="9c7cc-120">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="9c7cc-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="9c7cc-121">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9c7cc-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9c7cc-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c7cc-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-sql-server-agent-error-log"></a><span data-ttu-id="9c7cc-123">Per rinominare un log degli errori di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="9c7cc-123">To rename a SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="9c7cc-124">In **Esplora oggetti**fare clic sul segno più per espandere il server che contiene il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent da rinominare.</span><span class="sxs-lookup"><span data-stu-id="9c7cc-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to rename.</span></span>  
  
2.  <span data-ttu-id="9c7cc-125">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="9c7cc-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="9c7cc-126">Fare clic con il pulsante destro del mouse sulla cartella **Log degli errori** e scegliere **Configura**.</span><span class="sxs-lookup"><span data-stu-id="9c7cc-126">Right-click the **Error Logs** folder and select **Configure**.</span></span>  
  
4.  <span data-ttu-id="9c7cc-127">Nella casella **File di log degli errori** della finestra di dialogo **Configura log degli errori di SQL Server Agent** immettere il nuovo percorso e il nuovo nome file del log degli errori.</span><span class="sxs-lookup"><span data-stu-id="9c7cc-127">In the **Configure SQL Server Agent Error Logs** dialog box, in the **Error log file** box, enter the new file path and file name for the error log.</span></span> <span data-ttu-id="9c7cc-128">Alternativamente, fare clic sul pulsante con i puntini di sospensione **(...)** per aprire la finestra di dialogo **Specificare il percorso del log degli errori dell'agente** .</span><span class="sxs-lookup"><span data-stu-id="9c7cc-128">Alternately, click the ellipsis **(...)** to open the **Specify agent error log location** dialog box.</span></span>  
  
5.  <span data-ttu-id="9c7cc-129">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c7cc-129">When finished, click **OK**.</span></span>  
  
  
