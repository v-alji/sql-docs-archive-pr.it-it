---
title: Pagina convalida (procedure guidate gruppi di disponibilità AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.newagwizard.validation.f1
- sql12.swb.addreplicawizard.validation.f1
- sql12.swb.adddatabasewizard.validation.f1
helpviewer_keywords:
- ', listeners'
ms.assetid: c8971556-240c-491a-bc86-9cc72f71a3dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f2010074a357932f8af7358a05ee6ed16f5c0881
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624368"
---
# <a name="validation-page-alwayson-availability-group-wizards"></a><span data-ttu-id="e96a8-102">Pagina Convalida (procedure guidate gruppi di disponibilità AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="e96a8-102">Validation Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="e96a8-103">Questo argomento della Guida descrive le opzioni della pagina **Convalida** .</span><span class="sxs-lookup"><span data-stu-id="e96a8-103">This help topic describes the options of the **Validation** page.</span></span> <span data-ttu-id="e96a8-104">Questo argomento si applica alla [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], alla [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)], alla [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e96a8-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)], and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="e96a8-105">Utilizzare questa pagina per verificare che l'ambiente supporta tutte le scelte di configurazione effettuate nelle pagine precedenti della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e96a8-105">Use this page to validate that your environment supports all the configuration choices you made on previous pages of the wizard.</span></span>  
  
##  <a name="validation-page-options"></a><a name="PageOptions"></a><span data-ttu-id="e96a8-106">Opzioni della pagina di convalida</span><span class="sxs-lookup"><span data-stu-id="e96a8-106">Validation Page Options</span></span>  
 <span data-ttu-id="e96a8-107">**Risultati della convalida del gruppo di disponibilità.**</span><span class="sxs-lookup"><span data-stu-id="e96a8-107">**Results of availability group validation.**</span></span>  
 <span data-ttu-id="e96a8-108">In questa griglia vengono visualizzati i risultati di ogni passaggio di convalida completato.</span><span class="sxs-lookup"><span data-stu-id="e96a8-108">This grid displays the results of each completed validation step.</span></span> <span data-ttu-id="e96a8-109">Le colonne della griglia sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="e96a8-109">The grid columns are as follows:</span></span>  
  
 <span data-ttu-id="e96a8-110">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e96a8-110">**Name**</span></span>  
 <span data-ttu-id="e96a8-111">Visualizza una frase che descrive un passaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="e96a8-111">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="e96a8-112">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="e96a8-112">**Result**</span></span>  
 <span data-ttu-id="e96a8-113">Visualizza uno dei seguenti testi di collegamenti ipertestuali.</span><span class="sxs-lookup"><span data-stu-id="e96a8-113">Displays one of the following hyperlink texts.</span></span> <span data-ttu-id="e96a8-114">Per ulteriori informazioni sul risultato del passaggio di convalida specificato, fare clic sul collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="e96a8-114">For more information about the result of given validation step, click the hyperlink.</span></span>  
  
|<span data-ttu-id="e96a8-115">Risultato</span><span class="sxs-lookup"><span data-stu-id="e96a8-115">Result</span></span>|<span data-ttu-id="e96a8-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e96a8-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e96a8-117">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="e96a8-117">**Error**</span></span>|<span data-ttu-id="e96a8-118">Indica che il passaggio di convalida non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="e96a8-118">Indicates that the validation step failed.</span></span> <span data-ttu-id="e96a8-119">Fare clic sul collegamento per visualizzare il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="e96a8-119">Click the link to view the error message.</span></span>|  
|<span data-ttu-id="e96a8-120">**Ignorato**</span><span class="sxs-lookup"><span data-stu-id="e96a8-120">**Skipped**</span></span>|<span data-ttu-id="e96a8-121">Indica che il passaggio di convalida è stato ignorato perché non è necessario in base alle selezioni.</span><span class="sxs-lookup"><span data-stu-id="e96a8-121">Indicates that the validation step was skipped because it is not required by your selections.</span></span> <span data-ttu-id="e96a8-122">Fare clic sul collegamento per visualizzare il motivo per cui un passaggio è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="e96a8-122">Click the link to view the reason that a step was skipped.</span></span>|  
|<span data-ttu-id="e96a8-123">**Success**</span><span class="sxs-lookup"><span data-stu-id="e96a8-123">**Success**</span></span>|<span data-ttu-id="e96a8-124">Indica che il passaggio di convalida è riuscito.</span><span class="sxs-lookup"><span data-stu-id="e96a8-124">Indicates that the validation step completed successfully</span></span>|  
|<span data-ttu-id="e96a8-125">**Warning**</span><span class="sxs-lookup"><span data-stu-id="e96a8-125">**Warning**</span></span>|<span data-ttu-id="e96a8-126">Indica un potenziale problema con la configurazione del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="e96a8-126">Indicates a potential issue with the availability group configuration.</span></span>  <span data-ttu-id="e96a8-127">Fare clic sul collegamento per visualizzare il messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="e96a8-127">Click the link to view the warning message.</span></span>|  
  
 <span data-ttu-id="e96a8-128">**Ripeti convalida**</span><span class="sxs-lookup"><span data-stu-id="e96a8-128">**Re-run Validation**</span></span>  
 <span data-ttu-id="e96a8-129">Fare clic per ripetere i passaggi di convalida se si apporta una modifica al di fuori della procedura guidata in risposta a un errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="e96a8-129">Click to repeat the validation steps if you make a change outside of the wizard in response to a validation error.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e96a8-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="e96a8-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e96a8-131">Utilizzare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e96a8-131">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="e96a8-132">Usare la procedura guidata Aggiungi replica a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e96a8-132">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="e96a8-133">Usare la procedura guidata Aggiungi database a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e96a8-133">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="e96a8-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e96a8-134">See Also</span></span>  
 [<span data-ttu-id="e96a8-135">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e96a8-135">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
