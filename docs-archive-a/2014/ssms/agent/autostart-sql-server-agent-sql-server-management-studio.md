---
title: Avviare automaticamente SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- autostart SQL Server Agent
ms.assetid: 2ea332da-0ede-4d2b-b122-c4c10eaca191
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39c7c7a112370797a965cfa601bc07f983a7a37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630248"
---
# <a name="autostart-sql-server-agent-sql-server-management-studio"></a><span data-ttu-id="6901d-102">Autostart SQL Server Agent (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6901d-102">Autostart SQL Server Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="6901d-103">In questo argomento viene descritto come configurare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per il riavvio automatico in caso di arresto imprevisto in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6901d-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically restart if it should stop unexpectedly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="6901d-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6901d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6901d-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="6901d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6901d-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6901d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6901d-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6901d-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="6901d-108">Per configurare SQL Server Agent per il riavvio automatico tramite SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6901d-108">To configure SQL Server Agent to automatically restart, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6901d-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6901d-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6901d-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6901d-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="6901d-111">In Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="6901d-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6901d-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6901d-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6901d-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6901d-113">Permissions</span></span>  
 <span data-ttu-id="6901d-114">Per la corretta esecuzione delle funzioni, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia configurato per utilizzare le credenziali di un account membro del ruolo predefinito del server **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6901d-114">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6901d-115">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="6901d-115">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="6901d-116">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="6901d-116">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="6901d-117">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="6901d-117">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="6901d-118">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="6901d-118">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="6901d-119">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="6901d-119">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="6901d-120">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6901d-120">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6901d-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6901d-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent-to-automatically-restart"></a><span data-ttu-id="6901d-122">Per configurare SQL Server Agent per il riavvio automatico</span><span class="sxs-lookup"><span data-stu-id="6901d-122">To configure SQL Server Agent to automatically restart</span></span>  
  
1.  <span data-ttu-id="6901d-123">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si desidera configurare SQL Server Agent per il riavvio automatico.</span><span class="sxs-lookup"><span data-stu-id="6901d-123">In **Object Explorer**, click the plus sign to expand the server where you want to configure SQL Server Agent to automatically restart.</span></span>  
  
2.  <span data-ttu-id="6901d-124">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6901d-124">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6901d-125">Nella pagina **Generale** selezionare **Riavvia automaticamente SQL Server Agent in caso di arresto imprevisto**.</span><span class="sxs-lookup"><span data-stu-id="6901d-125">On the **General** page, check **Auto restart SQL Server Agent if it stops unexpectedly**.</span></span>  
  
  
