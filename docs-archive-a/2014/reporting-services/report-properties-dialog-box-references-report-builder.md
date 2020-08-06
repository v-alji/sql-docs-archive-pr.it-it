---
title: Finestra di dialogo Proprietà report, riferimenti (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c28e9053a1c13f8d0e0b7b44f3b1a037976c318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717393"
---
# <a name="report-properties-dialog-box-references-report-builder"></a><span data-ttu-id="0286f-102">Finestra di dialogo Proprietà report, Riferimenti (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="0286f-102">Report Properties Dialog Box, References (Report Builder)</span></span>
  <span data-ttu-id="0286f-103">Selezionare **Riferimenti** nella finestra di dialogo **Proprietà report** per aggiungere o rimuovere riferimenti ad assembly personalizzati o altri assembly esterni e a istanze di classe personalizzate utilizzate da espressioni nella definizione del report.</span><span class="sxs-lookup"><span data-stu-id="0286f-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span> <span data-ttu-id="0286f-104">Gli assembly personalizzati non sono supportati in modalità locale in Generatore report.</span><span class="sxs-lookup"><span data-stu-id="0286f-104">Custom assemblies are not supported in local mode in Report Builder.</span></span> <span data-ttu-id="0286f-105">Per creare report che utilizzano assembly personalizzati, utilizzare Progettazione report in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0286f-105">To author reports that use custom assemblies, use Report Designer in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="0286f-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0286f-106">Options</span></span>  
 <span data-ttu-id="0286f-107">**Aggiungi o rimuovi assembly**</span><span class="sxs-lookup"><span data-stu-id="0286f-107">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="0286f-108">Consente di visualizzare l'elenco degli assembly a cui il report fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="0286f-108">Lists the assemblies that the report references.</span></span> <span data-ttu-id="0286f-109">È necessario che l'assembly sia disponibile sia nel computer in cui è installato lo strumento utilizzato per progettare il report, sia nel server di report.</span><span class="sxs-lookup"><span data-stu-id="0286f-109">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="0286f-110">Il nome del riferimento deve corrispondere esattamente al contenuto dei **\<CodeModule>** tag nel file di report Definition Language (con estensione rdl).</span><span class="sxs-lookup"><span data-stu-id="0286f-110">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="0286f-111">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="0286f-111">**Add**</span></span>  
 <span data-ttu-id="0286f-112">Fare clic per aggiungere un assembly.</span><span class="sxs-lookup"><span data-stu-id="0286f-112">Click to add an assembly.</span></span> <span data-ttu-id="0286f-113">Fare clic sul pulsante con i puntini di sospensione (...) per aprire la finestra di dialogo **Apri** e selezionare gli assembly necessari per completare l'elaborazione del report e la valutazione dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="0286f-113">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="0286f-114">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="0286f-114">**Remove**</span></span>  
 <span data-ttu-id="0286f-115">Per rimuovere un riferimento all'assembly dall'elenco, selezionare il nome dell'assembly e fare clic sul pulsante **Rimuovi** .</span><span class="sxs-lookup"><span data-stu-id="0286f-115">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="0286f-116">**Aggiungi o rimuovi classi**</span><span class="sxs-lookup"><span data-stu-id="0286f-116">**Add or remove classes**</span></span>  
 <span data-ttu-id="0286f-117">Consente di visualizzare l'elenco delle istanze di classe utilizzate dal report.</span><span class="sxs-lookup"><span data-stu-id="0286f-117">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="0286f-118">L'elenco delle classi viene utilizzato solo dai membri basati sull'istanza e non dai membri statici.</span><span class="sxs-lookup"><span data-stu-id="0286f-118">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="0286f-119">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="0286f-119">**Add**</span></span>  
 <span data-ttu-id="0286f-120">Fare clic per aggiungere un riferimento alle classi.</span><span class="sxs-lookup"><span data-stu-id="0286f-120">Click to add a class reference.</span></span> <span data-ttu-id="0286f-121">Fare clic sul pulsante con i puntini di sospensione (...) per aprire la finestra di dialogo **Apri** e selezionare le classi necessarie per completare l'elaborazione del report e la valutazione dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="0286f-121">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="0286f-122">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="0286f-122">**Remove**</span></span>  
 <span data-ttu-id="0286f-123">Per eliminare l'istanza di classe, selezionarla e fare clic sul pulsante **Rimuovi** .</span><span class="sxs-lookup"><span data-stu-id="0286f-123">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="0286f-124">**Fino**</span><span class="sxs-lookup"><span data-stu-id="0286f-124">**Up**</span></span>  
 <span data-ttu-id="0286f-125">Per le classi con dipendenze, è possibile spostare il riferimento in un livello superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0286f-125">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="0286f-126">**Giù**</span><span class="sxs-lookup"><span data-stu-id="0286f-126">**Down**</span></span>  
 <span data-ttu-id="0286f-127">Per le classi con dipendenze, è possibile spostare il riferimento in un livello inferiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0286f-127">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0286f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0286f-128">See Also</span></span>  
 <span data-ttu-id="0286f-129">[Guida Generatore report per finestre di dialogo, riquadri e procedure guidate](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="0286f-129">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="0286f-130">Espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0286f-130">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
