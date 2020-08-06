---
title: Piano di manutenzione (pagina Report e registrazione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reportinglogging.f1
ms.assetid: 3a30b17a-3deb-446f-900a-62f88934a90f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c7a95a7092ce2cdac4aa0540a5cb57d86b48497
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627233"
---
# <a name="maintenance-plan-reporting-and-logging-page"></a><span data-ttu-id="a1b36-102">Piano di manutenzione (pagina Report e registrazione)</span><span class="sxs-lookup"><span data-stu-id="a1b36-102">Maintenance Plan (Reporting and Logging Page)</span></span>
  <span data-ttu-id="a1b36-103">Utilizzare la finestra di dialogo **Report e registrazione** per configurare i report e i log generati durante l'esecuzione dei piani di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a1b36-103">Use the **Reporting and Logging** dialog box to configure the reports and logs that are generated when maintenance plans are executed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a1b36-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a1b36-104">Options</span></span>  
 <span data-ttu-id="a1b36-105">**Genera report in un file di testo**</span><span class="sxs-lookup"><span data-stu-id="a1b36-105">**Generate a text file report**</span></span>  
 <span data-ttu-id="a1b36-106">Consente di specificare se si vuole che [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crei un report in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="a1b36-106">Specify if you want [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to write a text file report.</span></span>  
  
 <span data-ttu-id="a1b36-107">**Crea nuovo file**</span><span class="sxs-lookup"><span data-stu-id="a1b36-107">**Create a new file**</span></span>  
 <span data-ttu-id="a1b36-108">Consente di creare un nuovo file di report per ogni esecuzione del piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a1b36-108">Create a new report file for each execution of the maintenance plan.</span></span> <span data-ttu-id="a1b36-109">Per impostazione predefinita, i file di report vengono creati nel computer sul quale viene eseguita l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contenente il piano di manutenzione corrente, nella cartella specificata come cartella dei log predefinita durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1b36-109">By default, the report files are written to the computer hosting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains this maintenance plan, in the folder established as the default log folder during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup.</span></span> <span data-ttu-id="a1b36-110">Per specificare una cartella diversa, immettere il percorso completo nella casella di testo **Cartella** oppure fare clic sul pulsante " **...** " e selezionare la cartella desiderata.</span><span class="sxs-lookup"><span data-stu-id="a1b36-110">To specify a different folder, enter the full path of the folder in the **Folder** text box, or click the browse button (**...**) and navigate to the desired folder.</span></span>  
  
 <span data-ttu-id="a1b36-111">**Accoda a file**</span><span class="sxs-lookup"><span data-stu-id="a1b36-111">**Append to file**</span></span>  
 <span data-ttu-id="a1b36-112">Consente di accodare il report generato da ogni esecuzione del piano al file specificato nella casella di testo **Nome file** .</span><span class="sxs-lookup"><span data-stu-id="a1b36-112">Append the report from each plan execution to the file specified in the **File name** text box.</span></span> <span data-ttu-id="a1b36-113">È inoltre possibile specificare un file facendo clic sul pulsante Sfoglia (...) e selezionando un file nella finestra di dialogo visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a1b36-113">You may also specify a file by clicking the browse button and selecting a file from the dialog box.</span></span>  
  
 <span data-ttu-id="a1b36-114">**Invia report a destinatario di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="a1b36-114">**Send report to an e-mail recipient**</span></span>  
 <span data-ttu-id="a1b36-115">Consente di trasmettere tramite posta elettronica il risultato dell'esecuzione di un piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a1b36-115">Transmit the outcome of a maintenance plan execution via e-mail.</span></span> <span data-ttu-id="a1b36-116">Questa opzione è disponibile solo se l'opzione Posta elettronica database è abilitata e configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a1b36-116">This option is only available if Database Mail is enabled and properly configured.</span></span>  
  
 <span data-ttu-id="a1b36-117">**Operatore agente**</span><span class="sxs-lookup"><span data-stu-id="a1b36-117">**Agent operator**</span></span>  
 <span data-ttu-id="a1b36-118">Consente di selezionare un operatore agente nell'elenco come destinatario del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a1b36-118">Select an agent operator from the list who will be the recipient of the e-mail.</span></span> <span data-ttu-id="a1b36-119">Questa opzione è disponibile solo se la posta elettronica è abilitata e configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a1b36-119">This option is only available if mail is enabled and properly</span></span>  
  
 <span data-ttu-id="a1b36-120">**Registra informazioni estese**</span><span class="sxs-lookup"><span data-stu-id="a1b36-120">**Log extended information**</span></span>  
 <span data-ttu-id="a1b36-121">Consente di includere maggiori informazioni nel log.</span><span class="sxs-lookup"><span data-stu-id="a1b36-121">Include more information in the log.</span></span> <span data-ttu-id="a1b36-122">Se questa opzione viene selezionata, le dimensioni della cronologia del piano di manutenzione archiviato risulteranno maggiori.</span><span class="sxs-lookup"><span data-stu-id="a1b36-122">Including this option will increase the size of the stored maintenance plan history.</span></span>  
  
 <span data-ttu-id="a1b36-123">**Accedi a server remoto**</span><span class="sxs-lookup"><span data-stu-id="a1b36-123">**Log to remote server**</span></span>  
 <span data-ttu-id="a1b36-124">Consente di registrare la cronologia del piano di manutenzione in un server remoto.</span><span class="sxs-lookup"><span data-stu-id="a1b36-124">Logs maintenance plan history to a remote server.</span></span>  
  
 <span data-ttu-id="a1b36-125">**Connection**</span><span class="sxs-lookup"><span data-stu-id="a1b36-125">**Connection**</span></span>  
 <span data-ttu-id="a1b36-126">Consente di specificare le informazioni di connessione da utilizzare per la registrazione in un server remoto.</span><span class="sxs-lookup"><span data-stu-id="a1b36-126">Specifies the connection information to use when logging to a remote server.</span></span>  
  
 <span data-ttu-id="a1b36-127">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="a1b36-127">**New**</span></span>  
 <span data-ttu-id="a1b36-128">Consente di visualizzare la finestra di dialogo **Proprietà connessione** .</span><span class="sxs-lookup"><span data-stu-id="a1b36-128">Displays the **Connection Properties** dialog box.</span></span> <span data-ttu-id="a1b36-129">utilizzata per configurare le informazioni per una nuova connessione per la registrazione in un server remoto.</span><span class="sxs-lookup"><span data-stu-id="a1b36-129">Used to configure new connection information for logging to a remote server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b36-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1b36-130">See Also</span></span>  
 <span data-ttu-id="a1b36-131">[Piani di manutenzione](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="a1b36-131">[Maintenance Plans](maintenance-plans.md) </span></span>  
 [<span data-ttu-id="a1b36-132">Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="a1b36-132">Database Mail</span></span>](../database-mail/database-mail.md)  
  
  
