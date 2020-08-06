---
title: Log degli errori di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- messages [SQL Server], SQL Server Agent
- errors [SQL Server], logs
- SQL Server Agent, errors
ms.assetid: 0b2d6e6e-cd2d-4b8b-9fa2-2bbd2fc0da41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea9a723695c6993f4f07897f49d8014a86ce78b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714999"
---
# <a name="sql-server-agent-error-log"></a><span data-ttu-id="71c41-102">Log degli errori di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="71c41-102">SQL Server Agent Error Log</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="71c41-103">Agent crea un log degli errori nel quale vengono registrati avvisi ed errori per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="71c41-103">Agent creates an error log that records warnings and errors by default.</span></span> <span data-ttu-id="71c41-104">Nel log vengono visualizzati gli avvisi e gli errori seguenti:</span><span class="sxs-lookup"><span data-stu-id="71c41-104">The following warnings and errors are displayed in the log:</span></span>  
  
-   <span data-ttu-id="71c41-105">Messaggi di avviso che forniscono informazioni sui potenziali problemi, ad esempio "il processo \<*job_name*> è stato eliminato mentre era in esecuzione".</span><span class="sxs-lookup"><span data-stu-id="71c41-105">Warning messages that provide information about potential problems, such as "Job \<*job_name*> was deleted while it was running."</span></span>  
  
-   <span data-ttu-id="71c41-106">Messaggi di errore che richiedono in genere l'intervento dell'amministratore di sistema, quali "Impossibile avviare la sessione di posta elettronica".</span><span class="sxs-lookup"><span data-stu-id="71c41-106">Error messages that usually require intervention by a system administrator, such as "Unable to start mail session."</span></span> <span data-ttu-id="71c41-107">I messaggi di errore possono essere trasmessi a un utente o un computer specifico con **net send**.</span><span class="sxs-lookup"><span data-stu-id="71c41-107">Error messages can be sent to a specific user or computer by **net send**.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="71c41-108">gestisce fino a nove registri errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="71c41-108">maintains up to nine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs.</span></span> <span data-ttu-id="71c41-109">A ogni log degli errori archiviato viene assegnata un'estensione che indica la posizione cronologica del log stesso.</span><span class="sxs-lookup"><span data-stu-id="71c41-109">Each archived log has an extension that indicates the relative age of the log.</span></span> <span data-ttu-id="71c41-110">Ad esempio l'estensione 1 indica il log degli errori più recente e l'estensione 9 indica il log degli errori meno recente.</span><span class="sxs-lookup"><span data-stu-id="71c41-110">For example, an extension of .1 indicates the newest archived error log and an extension of .9 indicates the oldest archived error log.</span></span>  
  
 <span data-ttu-id="71c41-111">Per impostazione predefinita, i messaggi di traccia dell'esecuzione non vengono scritti nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in quanto potrebbero occuparlo interamente,</span><span class="sxs-lookup"><span data-stu-id="71c41-111">By default, execution trace messages are not written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log, because they can fill it.</span></span> <span data-ttu-id="71c41-112">rendendo complicata la selezione e la consultazione di messaggi di errore più gravi.</span><span class="sxs-lookup"><span data-stu-id="71c41-112">When the error log is full, your ability to select and analyze more difficult errors is reduced.</span></span> <span data-ttu-id="71c41-113">Poiché il log incrementa il carico di elaborazione del server, è importante valutare attentamente la rilevanza dell'acquisizione di messaggi di traccia dell'esecuzione nel log degli errori.</span><span class="sxs-lookup"><span data-stu-id="71c41-113">Because the log adds to the server's processing load, it is important to consider carefully what value you obtain by capturing execution trace messages to the error log.</span></span> <span data-ttu-id="71c41-114">In genere l'acquisizione di tutti i messaggi è opportuna soltanto durante il debug di un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="71c41-114">Generally, it is best to capture all messages only when you are debugging a specific problem.</span></span>  
  
 <span data-ttu-id="71c41-115">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non è in esecuzione, è possibile modificare la posizione del log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="71c41-115">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is stopped, you can modify the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log.</span></span> <span data-ttu-id="71c41-116">Quando il log degli errori è vuoto, non sarà possibile aprirlo.</span><span class="sxs-lookup"><span data-stu-id="71c41-116">When the error log is empty, the log cannot be opened.</span></span> <span data-ttu-id="71c41-117">È possibile scorrere il log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in qualunque momento, senza arrestare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="71c41-117">You can cycle the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent log at any time without stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="71c41-118">**Per visualizzare il log degli errori di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="71c41-118">**To view the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="71c41-119">Visualizzare il log degli errori di SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="71c41-119">View SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](view-sql-server-agent-error-log-sql-server-management-studio.md) 
  
 <span data-ttu-id="71c41-120">**Per rinominare un log degli errori di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="71c41-120">**To rename a SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="71c41-121">Rinominare un log degli errori di SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="71c41-121">Rename a SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](rename-a-sql-server-agent-error-log-sql-server-management-studio.md)  
  
 <span data-ttu-id="71c41-122">**Per inviare messaggi di errore di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="71c41-122">**To send SQL Server Agent error messages**</span></span>  
  
-   [<span data-ttu-id="71c41-123">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="71c41-123">Send SQL Server Agent Error Messages</span></span>](send-sql-server-agent-error-messages.md)  
  
 <span data-ttu-id="71c41-124">**Per scrivere messaggi di traccia esecuzione nel log degli errori di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="71c41-124">**To write execution trace messages to the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="71c41-125">Scrivere messaggi di traccia esecuzione nel log degli errori di SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="71c41-125">Write Execution Trace Messages to the SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](write-execution-trace-messages-to-sql-server-agent-log-ssms.md)  
  
  
