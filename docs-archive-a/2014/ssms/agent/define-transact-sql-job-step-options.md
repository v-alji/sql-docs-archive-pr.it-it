---
title: Definire le opzioni del passaggio di processo Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: b2a47057-f6fb-432b-a7b6-5d61f33a5d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc1d6412e52e74ce0c6d987d6189c0c72ffd7df7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712691"
---
# <a name="define-transact-sql-job-step-options"></a><span data-ttu-id="c213a-102">Definire le opzioni del passaggio di processo Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c213a-102">Define Transact-SQL Job Step Options</span></span>
  <span data-ttu-id="c213a-103">In questo argomento viene descritto come definire le opzioni per i [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] passaggi di processo di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="c213a-103">This topic describes how to define options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent [!INCLUDE[tsql](../../includes/tsql-md.md)] job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="c213a-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c213a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c213a-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c213a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c213a-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c213a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c213a-107">**Per definire le opzioni del passaggio di processo Transact-SQL con** ,</span><span class="sxs-lookup"><span data-stu-id="c213a-107">**To define Transact-SQL job step options, using:** ,</span></span>  
  
     [<span data-ttu-id="c213a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c213a-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="c213a-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c213a-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c213a-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c213a-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c213a-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c213a-111">Security</span></span>  
 <span data-ttu-id="c213a-112">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c213a-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="c213a-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c213a-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-transact-sql-job-step-options"></a><span data-ttu-id="c213a-114">Per definire le opzioni del passaggio di processo Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c213a-114">To define Transact-SQL job step options</span></span>  
  
1.  <span data-ttu-id="c213a-115">In **Esplora oggetti**espandere **SQL Server Agent**e **Processi**, fare clic con il pulsante destro del mouse sul processo da modificare e quindi selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c213a-115">In **Object Explorer**, expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c213a-116">Selezionare la pagina **Passaggi** , fare clic su un passaggio processo e quindi su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c213a-116">Click the **Steps** page, click a job step, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="c213a-117">Nella finestra di dialogo **Proprietà passaggio processo** verificare che il tipo di processo è **Transact-SQL Script (TSQL)** e quindi selezionare la pagina **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="c213a-117">On the **Job Step Properties** dialog, confirm that the job type is **Transact-SQL script (TSQL)**, and then select the **Advanced** page.</span></span>  
  
4.  <span data-ttu-id="c213a-118">Specificare un'operazione da eseguire se il processo ha esito positivo dall'elenco **Azione in caso di esito positivo** .</span><span class="sxs-lookup"><span data-stu-id="c213a-118">Specify an action to take if the job is successful by selecting from the **On success action** list.</span></span>  
  
5.  <span data-ttu-id="c213a-119">Specificare un numero di tentativi digitando un numero compreso tra 0 e 9999 nella casella **Numero tentativi** .</span><span class="sxs-lookup"><span data-stu-id="c213a-119">Specify a number of retry attempts by entering a number from 0 to 9999 into the **Retry attempts** box.</span></span>  
  
6.  <span data-ttu-id="c213a-120">Specificare un intervallo di tentativi digitando un numero di minuti compreso tra 0 e 9999 nella casella **Intervallo tentativi** .</span><span class="sxs-lookup"><span data-stu-id="c213a-120">Specify a retry interval by entering a number of minutes from 0 to 9999 into the **Retry interval** box.</span></span>  
  
7.  <span data-ttu-id="c213a-121">Specificare un'operazione da eseguire se il processo ha esito negativo dall'elenco **Azione in caso di esito negativo** .</span><span class="sxs-lookup"><span data-stu-id="c213a-121">Specify an action to take if the job fails by choosing from the **On failure action** list.</span></span>  
  
8.  <span data-ttu-id="c213a-122">Se il processo è uno script [!INCLUDE[tsql](../../includes/tsql-md.md)] , è possibile scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c213a-122">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="c213a-123">Immettere il nome di un **File di output**.</span><span class="sxs-lookup"><span data-stu-id="c213a-123">Enter the name of an **Output file**.</span></span> <span data-ttu-id="c213a-124">Per impostazione predefinita il file viene sovrascritto a ogni esecuzione del passaggio processo.</span><span class="sxs-lookup"><span data-stu-id="c213a-124">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="c213a-125">Per evitarlo, selezionare **Accoda output a file esistente**.</span><span class="sxs-lookup"><span data-stu-id="c213a-125">If you do not want the output file overwritten, check **Append output to existing file**.</span></span> <span data-ttu-id="c213a-126">L'opzione è disponibile solo ai membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c213a-126">This option is only available to members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="c213a-127">Si noti che [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] non consente agli utenti di visualizzare file arbitrari nel file system, quindi non è possibile utilizzare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] per visualizzare i log dei passaggi scritti nel file system.</span><span class="sxs-lookup"><span data-stu-id="c213a-127">Note that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] does not allow users to view arbitrary files on the file system, so you cannot use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to view job step logs that are written to the file system.</span></span>  
  
    -   <span data-ttu-id="c213a-128">Selezionare **Registra nella tabella** per registrare il passaggio processo in una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="c213a-128">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="c213a-129">Per impostazione predefinita il contenuto della tabella viene sovrascritto a ogni esecuzione del passaggio processo.</span><span class="sxs-lookup"><span data-stu-id="c213a-129">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="c213a-130">Per evitarlo, selezionare **Accoda output a voce esistente nella tabella**.</span><span class="sxs-lookup"><span data-stu-id="c213a-130">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="c213a-131">Dopo l'esecuzione del passaggio processo, è possibile visualizzare il contenuto della tabella facendo clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="c213a-131">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="c213a-132">Selezionare **Includi output passaggio nella cronologia** se si desidera includere l'output nella cronologia dei passaggi.</span><span class="sxs-lookup"><span data-stu-id="c213a-132">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="c213a-133">L'output verrà visualizzato solo se non si sono verificati errori.</span><span class="sxs-lookup"><span data-stu-id="c213a-133">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="c213a-134">È inoltre possibile che l'output sia troncato.</span><span class="sxs-lookup"><span data-stu-id="c213a-134">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="c213a-135">Se l'utente è membro del ruolo predefinito del server **sysadmin** e intende eseguire questo passaggio di processo con un diverso account di accesso SQL, selezionare l'account di accesso SQL dall'elenco **Esegui come utente** .</span><span class="sxs-lookup"><span data-stu-id="c213a-135">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="c213a-136">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c213a-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="c213a-137">**Per definire le opzioni del passaggio di processo Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="c213a-137">**To define Transact-SQL job step options**</span></span>  
  
 <span data-ttu-id="c213a-138">Usare la classe `JobStep` tramite un linguaggio di programmazione scelto come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c213a-138">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
