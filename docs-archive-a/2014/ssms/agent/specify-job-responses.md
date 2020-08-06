---
title: Specificare le risposte ai processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], responses
- SQL Server Agent jobs, responses
- actions [SQL Server Agent jobs]
- responding to jobs
ms.assetid: 050242e1-9b79-4ade-91a9-580707b9d2d9
author: stevestein
ms.author: sstein
ms.openlocfilehash: d41c5e1552a1ff16343bdb2c4e9feaafb51c5783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711575"
---
# <a name="specify-job-responses"></a><span data-ttu-id="f0dbe-102">Specifica delle risposte ai processi</span><span class="sxs-lookup"><span data-stu-id="f0dbe-102">Specify Job Responses</span></span>
  <span data-ttu-id="f0dbe-103">Le risposte ai processi specificano azioni che verranno eseguite dal servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent al termine di un processo.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-103">Job responses specify actions that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service will take after a job completes.</span></span> <span data-ttu-id="f0dbe-104">Tramite le risposte ai processi gli amministratori del database vengono informati in merito al completamento e alla frequenza di esecuzione dei processi.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="f0dbe-105">Le risposte ai processi tipiche includono:</span><span class="sxs-lookup"><span data-stu-id="f0dbe-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="f0dbe-106">Notifica all'operatore tramite posta elettronica, trasmissione di messaggi su cercapersone o messaggi **Net Send** .</span><span class="sxs-lookup"><span data-stu-id="f0dbe-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="f0dbe-107">Usare uno di questi metodi di risposta al processo se l'operatore dovrà eseguire operazioni basate sull'esito.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="f0dbe-108">Ad esempio, se un processo di backup viene completato, l'operatore dovrà ricevere una notifica per rimuovere il nastro di backup e riporlo in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="f0dbe-109">Scrittura di un messaggio di evento nel registro delle applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="f0dbe-110">Questa risposta può essere usata esclusivamente per i processi non riusciti.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="f0dbe-111">Eliminazione automatica del processo.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="f0dbe-112">Usare la risposta soltanto se si è certi che non sarà necessario rieseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f0dbe-113">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="f0dbe-113">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0dbe-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f0dbe-114">**Description**</span></span>|<span data-ttu-id="f0dbe-115">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="f0dbe-115">**Topic**</span></span>|  
|<span data-ttu-id="f0dbe-116">Viene descritto come notificare lo stato del processo a un operatore.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-116">Describes how to notify an operator of job status.</span></span>|[<span data-ttu-id="f0dbe-117">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="f0dbe-117">Notify an Operator of Job Status</span></span>](notify-an-operator-of-job-status.md)|  
|<span data-ttu-id="f0dbe-118">Viene descritto come scrivere lo stato del processo nel registro applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="f0dbe-118">Describes how to write job status to the Windows application log.</span></span>|[<span data-ttu-id="f0dbe-119">Registrare lo stato del processo nel registro applicazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="f0dbe-119">Write the Job Status to the Windows Application Log</span></span>](../../reporting-services/report-server/windows-application-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f0dbe-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0dbe-120">See Also</span></span>  
 [<span data-ttu-id="f0dbe-121">Monitoraggio e risposta agli eventi</span><span class="sxs-lookup"><span data-stu-id="f0dbe-121">Monitor and Respond to Events</span></span>](monitor-and-respond-to-events.md)  
  
  
