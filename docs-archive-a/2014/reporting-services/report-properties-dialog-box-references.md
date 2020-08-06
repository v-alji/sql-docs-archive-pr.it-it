---
title: Finestra di dialogo Proprietà report, riferimenti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10530"
- sql12.rtp.rptdesigner.reportproperties.references.f1
ms.assetid: 4639d368-9918-4bb1-9953-7a724ca78dea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b28ea0865d37bdc56054d6b23dc8c82d9279b08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717382"
---
# <a name="report-properties-dialog-box-references"></a><span data-ttu-id="54419-102">Finestra di dialogo Proprietà report, Riferimenti</span><span class="sxs-lookup"><span data-stu-id="54419-102">Report Properties Dialog Box, References</span></span>
  <span data-ttu-id="54419-103">Selezionare **Riferimenti** nella finestra di dialogo **Proprietà report** per aggiungere o rimuovere riferimenti ad assembly personalizzati o altri assembly esterni e a istanze di classe personalizzate utilizzate da espressioni nella definizione del report.</span><span class="sxs-lookup"><span data-stu-id="54419-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="54419-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="54419-104">Options</span></span>  
 <span data-ttu-id="54419-105">**Aggiungi o rimuovi assembly**</span><span class="sxs-lookup"><span data-stu-id="54419-105">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="54419-106">Consente di visualizzare l'elenco degli assembly a cui il report fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="54419-106">Lists the assemblies that the report references.</span></span> <span data-ttu-id="54419-107">È necessario che l'assembly sia disponibile sia nel computer in cui è installato lo strumento utilizzato per progettare il report, sia nel server di report.</span><span class="sxs-lookup"><span data-stu-id="54419-107">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="54419-108">Il nome del riferimento deve corrispondere esattamente al contenuto dei **\<CodeModule>** tag nel file di report Definition Language (con estensione rdl).</span><span class="sxs-lookup"><span data-stu-id="54419-108">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="54419-109">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="54419-109">**Add**</span></span>  
 <span data-ttu-id="54419-110">Fare clic per aggiungere un assembly.</span><span class="sxs-lookup"><span data-stu-id="54419-110">Click to add an assembly.</span></span> <span data-ttu-id="54419-111">Fare clic sul pulsante con i puntini di sospensione (...) per aprire la finestra di dialogo **Apri** e selezionare gli assembly necessari per completare l'elaborazione del report e la valutazione dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="54419-111">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="54419-112">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="54419-112">**Delete**</span></span>  
 <span data-ttu-id="54419-113">Per rimuovere un riferimento all'assembly dall'elenco, selezionare il nome dell'assembly e fare clic sul pulsante **Rimuovi** .</span><span class="sxs-lookup"><span data-stu-id="54419-113">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="54419-114">**Aggiungi o rimuovi classi**</span><span class="sxs-lookup"><span data-stu-id="54419-114">**Add or remove classes**</span></span>  
 <span data-ttu-id="54419-115">Consente di visualizzare l'elenco delle istanze di classe utilizzate dal report.</span><span class="sxs-lookup"><span data-stu-id="54419-115">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="54419-116">L'elenco delle classi viene utilizzato solo dai membri basati sull'istanza e non dai membri statici.</span><span class="sxs-lookup"><span data-stu-id="54419-116">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="54419-117">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="54419-117">**Add**</span></span>  
 <span data-ttu-id="54419-118">Fare clic per aggiungere un riferimento alle classi.</span><span class="sxs-lookup"><span data-stu-id="54419-118">Click to add a class reference.</span></span> <span data-ttu-id="54419-119">Fare clic sul pulsante con i puntini di sospensione (...) per aprire la finestra di dialogo **Apri** e selezionare le classi necessarie per completare l'elaborazione del report e la valutazione dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="54419-119">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="54419-120">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="54419-120">**Delete**</span></span>  
 <span data-ttu-id="54419-121">Per eliminare l'istanza di classe, selezionarla e fare clic sul pulsante **Rimuovi** .</span><span class="sxs-lookup"><span data-stu-id="54419-121">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="54419-122">**Fino**</span><span class="sxs-lookup"><span data-stu-id="54419-122">**Up**</span></span>  
 <span data-ttu-id="54419-123">Per le classi con dipendenze, è possibile spostare il riferimento in un livello superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="54419-123">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="54419-124">**Giù**</span><span class="sxs-lookup"><span data-stu-id="54419-124">**Down**</span></span>  
 <span data-ttu-id="54419-125">Per le classi con dipendenze, è possibile spostare il riferimento in un livello inferiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="54419-125">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54419-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54419-126">See Also</span></span>  
 <span data-ttu-id="54419-127">[Riferimenti a codice personalizzato e ad assembly in espressioni in Progettazione report &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="54419-127">[Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span></span>  
 <span data-ttu-id="54419-128">[Riferimenti a raccolte di variabili di report e di gruppo &#40;Generatore report e SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="54419-128">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 [<span data-ttu-id="54419-129">Esempi di espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="54419-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](report-design/expression-examples-report-builder-and-ssrs.md)  
  
  
