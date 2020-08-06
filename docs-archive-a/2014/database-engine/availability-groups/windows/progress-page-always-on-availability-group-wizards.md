---
title: Pagina stato (procedure guidate gruppi di disponibilità AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.progress.f1
- sql12.swb.newagwizard.progress.f1
- sql11.swb.failoverwizard.progress.f1
- sql11.swb.adddatabasewizard.progress.f1
- sql11.swb.addreplicawizard.progress.f1
- sql11.swb.newagwizard.progress.f1
- sql12.swb.adddatabasewizard.progress.f1
- sql12.swb.failoverwixard.progress.f1
ms.assetid: bd3b0306-8384-4120-a1c9-03825f0ae26a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7de8df6906d930215d71a0adc562bd7cef961ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724224"
---
# <a name="progress-page-alwayson-availability-group-wizards"></a><span data-ttu-id="b2d79-102">Pagina Stato installazione (procedure guidate gruppi di disponibilità AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="b2d79-102">Progress Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="b2d79-103">Utilizzare questa finestra di dialogo per visualizzare lo stato di avanzamento di una procedura guidata [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] eseguita in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2d79-103">Use this dialog box to view the progress of a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] wizard that you are running in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b2d79-104">L'indicatore di stato segnala lo stato di avanzamento relativo dei passaggi eseguiti dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b2d79-104">The progress bar indicates the relative progress of the steps that the wizard is performing.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b2d79-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b2d79-105">UI element list</span></span>  
 <span data-ttu-id="b2d79-106">**Altri dettagli**</span><span class="sxs-lookup"><span data-stu-id="b2d79-106">**More details**</span></span>  
 <span data-ttu-id="b2d79-107">Fare clic sulla freccia GIÙ per visualizzare una griglia dello stato di avanzamento in cui sono elencati i passaggi completati, seguiti dall'attuale operazione in corso.</span><span class="sxs-lookup"><span data-stu-id="b2d79-107">Click the down arrow to display a progress grid that lists any completed steps, in order, followed by the current in-progress operation.</span></span> <span data-ttu-id="b2d79-108">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2d79-108">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="b2d79-109">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b2d79-109">**Name**</span></span>  
 <span data-ttu-id="b2d79-110">Visualizza una frase che descrive un passaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="b2d79-110">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="b2d79-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="b2d79-111">**Status**</span></span>  
 <span data-ttu-id="b2d79-112">Indica il risultato dei passaggi completati e la percentuale di completamento del passaggio corrente, come segue:</span><span class="sxs-lookup"><span data-stu-id="b2d79-112">Indicates the outcome of completed steps and the percentage of completion of the current step, as follows:</span></span>  
  
|<span data-ttu-id="b2d79-113">Risultato</span><span class="sxs-lookup"><span data-stu-id="b2d79-113">Result</span></span>|<span data-ttu-id="b2d79-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2d79-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b2d79-115">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="b2d79-115">**Error**</span></span>|<span data-ttu-id="b2d79-116">Indica che si è verificato un errore nell'operazione relativa a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b2d79-116">Indicates the operation for this step experienced an error.</span></span> <span data-ttu-id="b2d79-117">Fare clic sul collegamento per visualizzare una finestra di dialogo del messaggio in cui viene descritto l'errore.</span><span class="sxs-lookup"><span data-stu-id="b2d79-117">Click the link to display a message dialog box that describes the error.</span></span>|  
|<span data-ttu-id="b2d79-118">**In corso (** *percentuale di completamento* **)**</span><span class="sxs-lookup"><span data-stu-id="b2d79-118">**In Progress (** *percentage-completed* **)**</span></span>|<span data-ttu-id="b2d79-119">Indica che l'operazione è in corso e stima la percentuale di completamento di questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b2d79-119">Indicates that the operation is occurring now and estimates the percentage of this step that has completed.</span></span>|  
|<span data-ttu-id="b2d79-120">**Success**</span><span class="sxs-lookup"><span data-stu-id="b2d79-120">**Success**</span></span>|<span data-ttu-id="b2d79-121">Indica che l'operazione per questo passaggio è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b2d79-121">Indicates the operation for this step completed successfully.</span></span>|  
  
 <span data-ttu-id="b2d79-122">**Meno dettagli**</span><span class="sxs-lookup"><span data-stu-id="b2d79-122">**Fewer Details**</span></span>  
 <span data-ttu-id="b2d79-123">Fare clic per nascondere la griglia dello stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="b2d79-123">Click to hide the progress grid.</span></span>  
  
 <span data-ttu-id="b2d79-124">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="b2d79-124">**Cancel**</span></span>  
 <span data-ttu-id="b2d79-125">Fare clic per ignorare eventuali operazioni rimanenti e uscire dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b2d79-125">Click to skip any remaining operations and then exit the wizard.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b2d79-126">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="b2d79-126">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b2d79-127">Utilizzare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b2d79-127">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b2d79-128">Usare la procedura guidata Aggiungi replica a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b2d79-128">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b2d79-129">Usare la procedura guidata Aggiungi database a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b2d79-129">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
-   [<span data-ttu-id="b2d79-130">Usare la Procedura guidata Failover del gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b2d79-130">Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2d79-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2d79-131">See Also</span></span>  
 [<span data-ttu-id="b2d79-132">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b2d79-132">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
