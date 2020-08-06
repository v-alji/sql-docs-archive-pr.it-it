---
title: Eliminare automaticamente un processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- dropping jobs
- SQL Server Agent jobs, removing
- automatic job removal
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 92dbb6da-5919-4bde-9354-d454e9ea3da0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07a10ec4a31d553a548bfecdcba426e3b46a1782
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630253"
---
# <a name="automatically-delete-a-job"></a><span data-ttu-id="067f1-102">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="067f1-102">Automatically Delete a Job</span></span>
  <span data-ttu-id="067f1-103">In questo argomento viene descritto come configurare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] per eliminare automaticamente i processi in caso di esito positivo, esito negativo o completamento tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="067f1-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to automatically delete jobs when they succeed, fail, or complete by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="067f1-104">Tramite le risposte ai processi gli amministratori del database vengono informati in merito al completamento e alla frequenza di esecuzione dei processi.</span><span class="sxs-lookup"><span data-stu-id="067f1-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="067f1-105">Le risposte ai processi tipiche includono:</span><span class="sxs-lookup"><span data-stu-id="067f1-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="067f1-106">Notifica all'operatore tramite posta elettronica, trasmissione di messaggi su cercapersone o messaggi **Net Send** .</span><span class="sxs-lookup"><span data-stu-id="067f1-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="067f1-107">Usare uno di questi metodi di risposta al processo se l'operatore dovrà eseguire operazioni basate sull'esito.</span><span class="sxs-lookup"><span data-stu-id="067f1-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="067f1-108">Ad esempio, se un processo di backup viene completato, l'operatore dovrà ricevere una notifica per rimuovere il nastro di backup e riporlo in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="067f1-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="067f1-109">Scrittura di un messaggio di evento nel registro delle applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="067f1-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="067f1-110">Questa risposta può essere usata esclusivamente per i processi non riusciti.</span><span class="sxs-lookup"><span data-stu-id="067f1-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="067f1-111">Eliminazione automatica del processo.</span><span class="sxs-lookup"><span data-stu-id="067f1-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="067f1-112">Usare la risposta soltanto se si è certi che non sarà necessario rieseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="067f1-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="067f1-113">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="067f1-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="067f1-114">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="067f1-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="067f1-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="067f1-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="067f1-116">**Per specificare le risposte ai processi utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="067f1-116">**To specify job responses, using:**</span></span>  
  
     [<span data-ttu-id="067f1-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="067f1-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="067f1-118">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="067f1-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="067f1-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="067f1-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="067f1-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="067f1-120">Security</span></span>  
 <span data-ttu-id="067f1-121">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="067f1-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="067f1-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="067f1-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-automatically-delete-a-job"></a><span data-ttu-id="067f1-123">Per eliminare automaticamente un processo</span><span class="sxs-lookup"><span data-stu-id="067f1-123">To automatically delete a job</span></span>  
  
1.  <span data-ttu-id="067f1-124">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="067f1-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="067f1-125">Espandere **SQL Server Agent**, espandere **Processi**, fare clic con il pulsante destro del mouse sul processo da modificare e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="067f1-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="067f1-126">Scegliere la pagina **Notifiche** .</span><span class="sxs-lookup"><span data-stu-id="067f1-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="067f1-127">Selezionare **Elimina il processo automaticamente**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="067f1-127">Check **Automatically delete job**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="067f1-128">Selezionare **In caso di esito positivo processo** per eliminare lo stato del processo quando questo viene completato con esito positivo.</span><span class="sxs-lookup"><span data-stu-id="067f1-128">Click **When the job succeeds** to delete the job status when it has completed successfully.</span></span>  
  
    -   <span data-ttu-id="067f1-129">Selezionare **In caso di esito negativo processo** per eliminare il processo quando questo viene completato con esito negativo.</span><span class="sxs-lookup"><span data-stu-id="067f1-129">Click **When the job fails** to delete the job when it has completed unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="067f1-130">Selezionare **Al termine del processo** per eliminare il processo indipendentemente dall'esito con cui viene completato.</span><span class="sxs-lookup"><span data-stu-id="067f1-130">Click **When the job completes** to delete the job regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="067f1-131">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="067f1-131">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="067f1-132">**Per eliminare automaticamente un processo**</span><span class="sxs-lookup"><span data-stu-id="067f1-132">**To automatically delete a job**</span></span>  
  
 <span data-ttu-id="067f1-133">Utilizzare la proprietà `DeleteLevel` della classe `Job` tramite un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="067f1-133">Use the `DeleteLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="067f1-134">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="067f1-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
