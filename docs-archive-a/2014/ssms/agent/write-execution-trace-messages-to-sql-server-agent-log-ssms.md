---
title: Scrivere messaggi di traccia esecuzione nel log degli errori di SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- writing trace messages
- traces [SQL Server], SQL Server Agent logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 90e3731e-6fae-43db-833e-9accecdd1c03
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38b08452ef2680b654dd735b901488cb5f5f5f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719367"
---
# <a name="write-execution-trace-messages-to-the-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="aa8fa-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="aa8fa-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="aa8fa-103">In questo argomento viene descritto come configurare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per includere i messaggi di traccia esecuzione nel relativo log degli errori in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aa8fa-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to include execution trace messages in its error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="aa8fa-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="aa8fa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aa8fa-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="aa8fa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aa8fa-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="aa8fa-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="aa8fa-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="aa8fa-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="aa8fa-108">Per scrivere i messaggi di traccia esecuzione nel log degli errori di SQL Server Agent tramite SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aa8fa-108">To write execution trace messages to the SQL Server Agent Error Log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aa8fa-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="aa8fa-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="aa8fa-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="aa8fa-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="aa8fa-111">In Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="aa8fa-112">Includere i messaggi della traccia di esecuzione nei log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo per esigenze di analisi di un problema specifico di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, in quanto essa comporta un aumento significativo delle dimensioni del log degli errori.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-112">Because this option can cause the error log to become large, only include execution trace messages in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs when investigating a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent problem.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aa8fa-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="aa8fa-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aa8fa-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="aa8fa-114">Permissions</span></span>  
 <span data-ttu-id="aa8fa-115">Per la corretta esecuzione delle funzioni, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia configurato per utilizzare le credenziali di un account membro del ruolo predefinito del server **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa8fa-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aa8fa-116">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa8fa-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="aa8fa-117">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="aa8fa-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="aa8fa-118">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="aa8fa-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="aa8fa-119">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="aa8fa-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="aa8fa-120">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="aa8fa-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="aa8fa-121">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="aa8fa-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>   
#### <a name="to-write-execution-trace-messages-to-the-sql-server-agent-error-log"></a><span data-ttu-id="aa8fa-122">Per scrivere messaggi di traccia esecuzione nel log degli errori di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="aa8fa-122">To write execution trace messages to the SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="aa8fa-123">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in cui si desidera registrare i messaggi di traccia di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-123">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log to which you want to write execution trace messages.</span></span>  
  
2.  <span data-ttu-id="aa8fa-124">Fare clic con il pulsante destro del mouse su **SQL Server Agent** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="aa8fa-125">Nella finestra di dialogo **proprietà SQL Server Agent-**_server_name_ , in **log degli errori** nella pagina **generale** , selezionare la casella di controllo **Includi messaggi di traccia esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="aa8fa-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, select the **Include execution trace messages** check box.</span></span>  
  
4.  <span data-ttu-id="aa8fa-126">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-126">Click **OK**.</span></span>  
  
  
