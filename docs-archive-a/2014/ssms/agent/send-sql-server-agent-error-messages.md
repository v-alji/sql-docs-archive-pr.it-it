---
title: Inviare messaggi di errore di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- messages [SQL Server], SQL Server Agent
- sending messages
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 2597d0d7-951a-48cf-989f-abb67b9fdb36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 03e38b02188eaced65a86b22ed4f22cb6984ce0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630240"
---
# <a name="send-sql-server-agent-error-messages"></a><span data-ttu-id="abaa1-102">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="abaa1-102">Send SQL Server Agent Error Messages</span></span>
  <span data-ttu-id="abaa1-103">In questo argomento viene descritto come configurare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per l'invio di messaggi di errore tramite net send in utilizzando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="abaa1-103">This topic describes how to how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send its error messages by way of net send in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="abaa1-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="abaa1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="abaa1-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="abaa1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="abaa1-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="abaa1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="abaa1-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="abaa1-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="abaa1-108">Per inviare messaggi di errore di SQL Server Agent tramite SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="abaa1-108">To send SQL Server Agent error messages using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="abaa1-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="abaa1-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="abaa1-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="abaa1-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="abaa1-111">In Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="abaa1-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="abaa1-112">Per ricevere eventi Net Send, è necessario che il servizio [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="abaa1-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger service must be running to receive net send events.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="abaa1-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="abaa1-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="abaa1-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="abaa1-114">Permissions</span></span>  
 <span data-ttu-id="abaa1-115">Per la corretta esecuzione delle funzioni, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia configurato per utilizzare le credenziali di un account membro del ruolo predefinito del server **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abaa1-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="abaa1-116">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="abaa1-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="abaa1-117">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="abaa1-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="abaa1-118">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="abaa1-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="abaa1-119">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="abaa1-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="abaa1-120">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="abaa1-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="abaa1-121">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="abaa1-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="abaa1-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="abaa1-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-send-sql-server-agent-error-messages"></a><span data-ttu-id="abaa1-123">Per inviare messaggi di errore di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="abaa1-123">To send SQL Server Agent error messages</span></span>  
  
1.  <span data-ttu-id="abaa1-124">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent da cui si desidera inviare i messaggi di errore tramite Net Send.</span><span class="sxs-lookup"><span data-stu-id="abaa1-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log from which you want to send error messages via net send.</span></span>  
  
2.  <span data-ttu-id="abaa1-125">Fare clic con il pulsante destro del mouse su **SQL Server Agent** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="abaa1-125">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="abaa1-126">Nella finestra di dialogo **proprietà SQL Server Agent-**_server_name_ , in **log degli errori** nella pagina **generale** , digitare il nome utente o il nome computer a cui si desidera inviare i messaggi di errore nella casella **Destinatario Net Send** .</span><span class="sxs-lookup"><span data-stu-id="abaa1-126">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, , type the user name or computer name to which you want to send error messages in the **Net send recipient** box.</span></span>  
  
4.  <span data-ttu-id="abaa1-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="abaa1-127">Click **OK**.</span></span>  
  
  
