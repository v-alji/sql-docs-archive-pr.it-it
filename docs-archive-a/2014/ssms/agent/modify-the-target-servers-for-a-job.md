---
title: Modificare i server di destinazione per un processo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- modifying target servers
- SQL Server Agent jobs, target servers
- target servers [SQL Server], modifying
ms.assetid: 9dbe24f2-acec-4aa2-920c-e8e96efa18e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246a5bb59a681a70734cc8cabef4f724cda1b52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627042"
---
# <a name="modify-the-target-servers-for-a-job"></a><span data-ttu-id="62de4-102">Modifica dei server di destinazione di un processo</span><span class="sxs-lookup"><span data-stu-id="62de4-102">Modify the Target Servers for a Job</span></span>
  <span data-ttu-id="62de4-103">In questo argomento viene descritto come modificare i server di destinazione per i [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processi di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62de4-103">This topic describes how to change the target servers for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="62de4-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="62de4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="62de4-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="62de4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="62de4-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="62de4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="62de4-107">**Per modificare i server di destinazione per un processo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="62de4-107">**To modify the target servers for a job, using:**</span></span>  
  
     [<span data-ttu-id="62de4-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="62de4-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="62de4-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="62de4-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="62de4-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="62de4-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="62de4-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="62de4-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="62de4-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="62de4-112">Permissions</span></span>  
 <span data-ttu-id="62de4-113">Per impostazione predefinita, i membri del ruolo predefinito del server sysadmin possono eseguire questa stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62de4-113">By default, members of the sysadmin fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="62de4-114">Gli altri utenti devono appartenere a uno dei seguenti ruoli predefiniti del database di SQL Server Agent nel database msdb:</span><span class="sxs-lookup"><span data-stu-id="62de4-114">Other users must be granted one of the following SQL Server Agent fixed database roles in the msdb database:</span></span>  
  
1.  `SQLAgentUserRole`  
  
2.  `SQLAgentReaderRole`  
  
3.  <span data-ttu-id="62de4-115">SQLAgentOperatorRole</span><span class="sxs-lookup"><span data-stu-id="62de4-115">SQLAgentOperatorRole</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="62de4-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="62de4-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="62de4-117">Per modificare i server di destinazione per un processo</span><span class="sxs-lookup"><span data-stu-id="62de4-117">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="62de4-118">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="62de4-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="62de4-119">Espandere **SQL Server Agent**e quindi **Processi**, fare clic con il pulsante destro del mouse sul processo e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="62de4-119">Expand **SQL Server Agent**, expand **Jobs**, right-click a job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="62de4-120">Nella finestra di dialogo **Proprietà processo** , fare clic sulla pagina **Server di destinazione**e quindi su **Server di destinazione locale**oppure **Più server di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="62de4-120">In the **Job Properties** dialog, select the **Targets**page, and click **Target local server**, or **Target multiple servers**.</span></span>  
  
     <span data-ttu-id="62de4-121">Se si sceglie **Più server di destinazione**, specificare quali dovranno essere i server di destinazione del processo selezionando la casella a sinistra del nome di ogni server.</span><span class="sxs-lookup"><span data-stu-id="62de4-121">If you choose **Target multiple servers**, designate the servers that will be targets for the job by checking the box to the left of the server name.</span></span> <span data-ttu-id="62de4-122">Verificare che le caselle di controllo corrispondenti ai server che non saranno server di destinazione del processo siano deselezionate.</span><span class="sxs-lookup"><span data-stu-id="62de4-122">Verify that the check boxes for servers that will not be targets of the job are unchecked.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="62de4-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="62de4-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="62de4-124">Per modificare i server di destinazione per un processo</span><span class="sxs-lookup"><span data-stu-id="62de4-124">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="62de4-125">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62de4-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="62de4-126">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="62de4-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="62de4-127">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="62de4-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="62de4-128">In questo esempio il processo multiserver Weekly Sales Backups viene assegnato al server SEATTLE2.</span><span class="sxs-lookup"><span data-stu-id="62de4-128">This example assigns the multiserver job Weekly Sales Backups to the server SEATTLE2.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_add_jobserver  
    @job_name = N'Weekly Sales Backups',   
    @server_name = N'SEATTLE2' ;   
GO  
  
```  
  
 <span data-ttu-id="62de4-129">Per ulteriori informazioni, vedere [sp_add_jobserver &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62de4-129">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62de4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62de4-130">See Also</span></span>  
 [<span data-ttu-id="62de4-131">Amministrazione automatizzata in un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="62de4-131">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
