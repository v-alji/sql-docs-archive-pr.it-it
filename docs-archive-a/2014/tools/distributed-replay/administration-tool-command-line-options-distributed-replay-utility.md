---
title: Opzioni della riga di comando dello strumento di amministrazione (utilità Riesecuzione distribuita) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: c01b0ed3-67e4-4561-92d2-a8fbb086aca8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 506be071f44937d82902585e5a0621212083dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629664"
---
# <a name="administration-tool-command-line-options-distributed-replay-utility"></a><span data-ttu-id="a38a0-102">Opzioni della riga di comando dello strumento di amministrazione (Distributed Replay Utility)</span><span class="sxs-lookup"><span data-stu-id="a38a0-102">Administration Tool Command-line Options (Distributed Replay Utility)</span></span>
  <span data-ttu-id="a38a0-103">Lo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] strumento di amministrazione riesecuzione distribuita, `DReplay.exe` , è uno strumento da riga di comando che è possibile utilizzare per comunicare con il controller di riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="a38a0-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="a38a0-104">Usare lo strumento di amministrazione per avviare, monitorare e annullare operazioni nel controller.</span><span class="sxs-lookup"><span data-stu-id="a38a0-104">Use the administration tool to initiate, monitor, and cancel operations on the controller.</span></span>  
  
 <span data-ttu-id="a38a0-105">![Icona di collegamento all'argomento](../../database-engine/media/topic-link.gif "Icona di collegamento a un argomento") Per altre informazioni sulle convenzioni relative alla sintassi dello strumento di amministrazione, vedere [Convenzioni della sintassi Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a38a0-105">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a38a0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a38a0-106">Syntax</span></span>  
  
```  
  
      dreplay {preprocess|replay|status|cancel} [options] [-?]}  
  
Usage:  
  
  dreplay preprocess [-mcontroller] -iinput_trace_file  
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]  
  
  dreplay replay [-mcontroller] -dcontroller_working_dir [-o]  
    [-starget_server] -wclients [-cconfig_file]  
    [-fstatus_interval]  
  
  dreplay status [-mcontroller] [-fstatus_interval]  
  
  dreplay cancel [-mcontroller] [-q]   
```  
  
## <a name="remarks"></a><span data-ttu-id="a38a0-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a38a0-107">Remarks</span></span>  
 <span data-ttu-id="a38a0-108">È possibile eseguire le seguenti opzioni della riga di comando con `DReplay.exe`:</span><span class="sxs-lookup"><span data-stu-id="a38a0-108">You can issue the following command-line options with `DReplay.exe`:</span></span>  
  
 <span data-ttu-id="a38a0-109">**preprocess**</span><span class="sxs-lookup"><span data-stu-id="a38a0-109">**preprocess**</span></span>  
 <span data-ttu-id="a38a0-110">Avvia la fase di pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="a38a0-110">Initiates the preprocess stage.</span></span> <span data-ttu-id="a38a0-111">Il controller prepara i dati di traccia di input, acquisiti dall'ambiente di produzione, per la riproduzione sul server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a38a0-111">The controller prepares the input trace data, which you captured from the production environment, for replay against the target server.</span></span>  
  
 <span data-ttu-id="a38a0-112">**replay**</span><span class="sxs-lookup"><span data-stu-id="a38a0-112">**replay**</span></span>  
 <span data-ttu-id="a38a0-113">Avvia la fase di riproduzione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a38a0-113">Initiates the event replay stage.</span></span> <span data-ttu-id="a38a0-114">Il controller recapita i dati di riproduzione ai client specificati, avvia la riproduzione distribuita e sincronizza i client.</span><span class="sxs-lookup"><span data-stu-id="a38a0-114">The controller dispatches replay data to the specified clients, launches the distributed replay, and synchronizes the clients.</span></span> <span data-ttu-id="a38a0-115">Ogni client selezionato può eventualmente registrare l'attività di riproduzione e salvare in locale i file di traccia dei risultati.</span><span class="sxs-lookup"><span data-stu-id="a38a0-115">Optionally, each client that was selected records the replay activity and saves result trace files locally.</span></span>  
  
 <span data-ttu-id="a38a0-116">**Stato**</span><span class="sxs-lookup"><span data-stu-id="a38a0-116">**status**</span></span>  
 <span data-ttu-id="a38a0-117">Viene eseguita una query sul controller e viene visualizzato lo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="a38a0-117">Queries the controller and displays the current status.</span></span>  
  
 <span data-ttu-id="a38a0-118">**cancel**</span><span class="sxs-lookup"><span data-stu-id="a38a0-118">**cancel**</span></span>  
 <span data-ttu-id="a38a0-119">Viene annullata l'operazione corrente eseguita nel controller.</span><span class="sxs-lookup"><span data-stu-id="a38a0-119">Cancels the current operation that is running on the controller.</span></span>  
  
 <span data-ttu-id="a38a0-120">Per informazioni dettagliate sulla sintassi, inclusi gli argomenti dei comandi e gli esempi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a0-120">For detailed syntax information that includes the command arguments and examples, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a38a0-121">Opzione preprocess &#40;strumento di amministrazione Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="a38a0-121">Preprocess Option &#40;Distributed Replay Administration Tool&#41;</span></span>](preprocess-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="a38a0-122">Opzione replay &#40;strumento di amministrazione Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="a38a0-122">Replay Option &#40;Distributed Replay Administration Tool&#41;</span></span>](replay-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="a38a0-123">Opzione status &#40;strumento di amministrazione Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="a38a0-123">Status Option &#40;Distributed Replay Administration Tool&#41;</span></span>](status-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="a38a0-124">Opzione cancel &#40;strumento di amministrazione Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="a38a0-124">Cancel Option &#40;Distributed Replay Administration Tool&#41;</span></span>](cancel-option-distributed-replay-administration-tool.md)  
  
 <span data-ttu-id="a38a0-125">Le chiamate RPC vengono riprodotte come RPC e non come eventi di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="a38a0-125">RPCs are replayed as RPCs and not as language events.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="a38a0-126">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a38a0-126">Permissions</span></span>  
 <span data-ttu-id="a38a0-127">È necessario eseguire lo strumento di amministrazione come utente interattivo, scegliendo tra utente locale e account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="a38a0-127">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="a38a0-128">Per utilizzare un account utente locale, lo strumento di amministrazione e il controller devono essere eseguiti nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="a38a0-128">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>  
  
 <span data-ttu-id="a38a0-129">Per altre informazioni, vedere [Sicurezza di Distributed Replay](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="a38a0-129">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38a0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a38a0-130">See Also</span></span>  
 [<span data-ttu-id="a38a0-131">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="a38a0-131">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)  
  
  
