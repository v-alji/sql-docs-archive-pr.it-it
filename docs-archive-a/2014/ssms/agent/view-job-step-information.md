---
title: Visualizzare informazioni sui passaggi di processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- displaying job step information
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- viewing job step information
ms.assetid: e3f06492-dc86-4e06-b186-ea58aff6d591
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d9fc6a006884bc564b5db2bfa8b168c8ae59149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623039"
---
# <a name="view-job-step-information"></a><span data-ttu-id="b8351-102">Visualizzare informazioni sui passaggi di processo</span><span class="sxs-lookup"><span data-stu-id="b8351-102">View Job Step Information</span></span>
  <span data-ttu-id="b8351-103">In questo argomento viene illustrato come visualizzare informazioni dettagliate sui passaggi di processo nella finestra di dialogo Proprietà passaggio processo.</span><span class="sxs-lookup"><span data-stu-id="b8351-103">This topic describes how to view job step details in the Job Step Properties dialog.</span></span> <span data-ttu-id="b8351-104">Sono inoltre incluse informazioni sulla visualizzazione dell'output dei passaggi di processo.</span><span class="sxs-lookup"><span data-stu-id="b8351-104">It also includes information about viewing job step output.</span></span>  
  
-   <span data-ttu-id="b8351-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b8351-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b8351-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b8351-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b8351-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b8351-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b8351-108">**Per visualizzare informazioni sui passaggi di processo mediante:**</span><span class="sxs-lookup"><span data-stu-id="b8351-108">**To view job step information, using:**</span></span>  
  
     [<span data-ttu-id="b8351-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8351-109">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b8351-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b8351-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b8351-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b8351-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b8351-112">Se un passaggio di processo è stato configurato per la scrittura dell'output in una tabella o file e il processo è stato eseguito almeno una volta, è possibile esaminare l'output nella scheda **Avanzate** della finestra di dialogo **Proprietà passaggio processo** .</span><span class="sxs-lookup"><span data-stu-id="b8351-112">If the job step has been configured to write its output to a table or file and the job has run at least once, you can view its output on the **Advanced** page of the **Job Step Properties** dialog.</span></span> <span data-ttu-id="b8351-113">Quando un processo o un passaggio di processo viene eliminato, viene eliminato automaticamente anche il log di output.</span><span class="sxs-lookup"><span data-stu-id="b8351-113">When a job or job step is deleted, the output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b8351-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b8351-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b8351-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b8351-115">Permissions</span></span>  
 <span data-ttu-id="b8351-116">È possibile visualizzare solo i processi di cui si è proprietari, a meno che non si appartenga al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="b8351-116">You can view only those jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="b8351-117">I membri di questo ruolo infatti possono visualizzare tutti i processi e tutte le informazioni sui passaggi di processo.</span><span class="sxs-lookup"><span data-stu-id="b8351-117">Members of this role can view all jobs and job step details.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="b8351-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8351-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-step-information"></a><span data-ttu-id="b8351-119">Per visualizzare informazioni sui passaggi di processo</span><span class="sxs-lookup"><span data-stu-id="b8351-119">To view job step information</span></span>  
  
1.  <span data-ttu-id="b8351-120">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="b8351-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="b8351-121">Espandere il nodo **SQL Server Agent**e il nodo **Processi**, fare clic con il pulsante destro del mouse sul processo che include il passaggio da visualizzare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b8351-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that contains the job step to be viewed, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="b8351-122">Nella finestra di dialogo **Proprietà processo** fare clic sulla scheda **Passaggi** .</span><span class="sxs-lookup"><span data-stu-id="b8351-122">In the **Job Properties** dialog, click the **Steps** page.</span></span>  
  
4.  <span data-ttu-id="b8351-123">Fare clic sul passaggio di processo da visualizzare e quindi dare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b8351-123">Click the job step to be viewed, and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="b8351-124">Nella scheda **Generale** della finestra di dialogo **Proprietà passaggio processo** è indicato il tipo di passaggio e la funzione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b8351-124">On the **General** page of the **Job Step Properties** dialog, you can view the type of job step and what it does.</span></span>  
  
6.  <span data-ttu-id="b8351-125">Nella scheda **Avanzate** sono indicate le operazioni eseguite da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se il passaggio di processo ha esito positivo o negativo, il numero di tentativi da eseguire, la posizione in cui viene scritto l'output del passaggio e l'utente in base al quale viene eseguito il passaggio.</span><span class="sxs-lookup"><span data-stu-id="b8351-125">Click the **Advanced** page to view the actions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent takes if the job step succeeds or fails, how many times the job step should be attempted, where the job step output is written, and the user the job step runs as.</span></span>  
  
#### <a name="to-view-job-step-output"></a><span data-ttu-id="b8351-126">Per visualizzare l'output dei passaggi di processo</span><span class="sxs-lookup"><span data-stu-id="b8351-126">To view job step output</span></span>  
  
1.  <span data-ttu-id="b8351-127">Nella finestra di dialogo **Proprietà passaggio processo** fare clic sulla scheda **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="b8351-127">In the **Job Step Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="b8351-128">A seconda della versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui si è connessi, è possibile visualizzare il file o la tabella di output dei passaggi di processo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b8351-128">Depending on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connected to, you can view either the job step output file or table as follows:</span></span>  
  
    -   <span data-ttu-id="b8351-129">Se si è connessi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o versioni successive, è possibile fare clic su **Visualizza** solo quando è selezionata l'opzione **Registra nella tabella** .</span><span class="sxs-lookup"><span data-stu-id="b8351-129">When you are connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later, you can click **View** only when **Log to table** is checked.</span></span> <span data-ttu-id="b8351-130">In questo caso l'output dei passaggi di processo viene scritto nella tabella **sysjobstepslogs** del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="b8351-130">In this case, the job step output is written to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
    -   <span data-ttu-id="b8351-131">Il pulsante **Visualizza** è disabilitato quando l'output dei passaggi di processo viene scritto in un file.</span><span class="sxs-lookup"><span data-stu-id="b8351-131">The **View** button is disabled when job step output is written to a file.</span></span> <span data-ttu-id="b8351-132">Per visualizzare un file di output dei passaggi di processo, utilizzare il Blocco note.</span><span class="sxs-lookup"><span data-stu-id="b8351-132">To view a job step output file, use Notepad.</span></span>  
  
  
