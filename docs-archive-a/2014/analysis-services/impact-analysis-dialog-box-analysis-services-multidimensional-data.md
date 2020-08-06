---
title: Finestra di dialogo analisi di incidenza (dati multidimensionali Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.impactanalysisdialog.f1
ms.assetid: 208268eb-4e14-44db-9c64-6f74b776adb6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e47ab806b9bd10afc812113b69fe0849437068b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712608"
---
# <a name="impact-analysis-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="dac9c-102">Finestra di dialogo Analisi di impatto (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="dac9c-102">Impact Analysis Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="dac9c-103">Utilizzare la finestra di dialogo **Analisi di impatto** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per identificare ed eventualmente elaborare gli oggetti dipendenti sui quali influisce l'elaborazione degli oggetti elencati nella finestra di dialogo **Elabora** .</span><span class="sxs-lookup"><span data-stu-id="dac9c-103">Use the **Impact Analysis** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to identify and optionally process dependent objects that are affected if the objects listed in the **Process** dialog box are processed.</span></span> <span data-ttu-id="dac9c-104">Per visualizzare la finestra di dialogo **Analisi di impatto** , è possibile fare clic su **Analisi di impatto** nella finestra di dialogo **Elabora** .</span><span class="sxs-lookup"><span data-stu-id="dac9c-104">You can display the **Impact Analysis** dialog box by clicking **Impact Analysis** from the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dac9c-105">Vengono visualizzate più occorrenze di uno stesso oggetto qualora quest'ultimo sia interessato da più eventi.</span><span class="sxs-lookup"><span data-stu-id="dac9c-105">An object appears more than once if it is affected in more than one way.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dac9c-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="dac9c-106">Options</span></span>  
 <span data-ttu-id="dac9c-107">**Elenco oggetti**</span><span class="sxs-lookup"><span data-stu-id="dac9c-107">**Object list**</span></span>  
 <span data-ttu-id="dac9c-108">Visualizza l'elenco degli oggetti dipendenti in una griglia.</span><span class="sxs-lookup"><span data-stu-id="dac9c-108">Displays a list of dependent objects in a grid.</span></span> <span data-ttu-id="dac9c-109">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="dac9c-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="dac9c-110">**nome oggetto**</span><span class="sxs-lookup"><span data-stu-id="dac9c-110">**Object Name**</span></span>  
 <span data-ttu-id="dac9c-111">Visualizza il nome dell'oggetto dipendente che può essere necessario elaborare.</span><span class="sxs-lookup"><span data-stu-id="dac9c-111">Displays the name of the dependent object that may need to be processed.</span></span> <span data-ttu-id="dac9c-112">L'icona a sinistra del nome indica il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="dac9c-112">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="dac9c-113">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dac9c-113">**Type**</span></span>  
 <span data-ttu-id="dac9c-114">Indica il tipo di oggetto dipendente che può essere necessario elaborare.</span><span class="sxs-lookup"><span data-stu-id="dac9c-114">Displays the type of dependent object that may need to be processed.</span></span>  
  
 <span data-ttu-id="dac9c-115">**Tipo impatto**</span><span class="sxs-lookup"><span data-stu-id="dac9c-115">**Impact Type**</span></span>  
 <span data-ttu-id="dac9c-116">Indica l'effetto che l'elaborazione degli oggetti elencati nella finestra di dialogo **Elabora** avrà sull'oggetto dipendente.</span><span class="sxs-lookup"><span data-stu-id="dac9c-116">Displays the effect that processing the objects in the **Process** dialog box has on the dependent object.</span></span> <span data-ttu-id="dac9c-117">Nella tabella seguente vengono elencati i possibili effetti dell'elaborazione, ognuno dei quali viene individuato come la causa di un avviso o di un errore.</span><span class="sxs-lookup"><span data-stu-id="dac9c-117">The following table lists the possible effects of processing and notes whether each one results in a warning or an error.</span></span>  
  
|<span data-ttu-id="dac9c-118">Impatto</span><span class="sxs-lookup"><span data-stu-id="dac9c-118">Impact</span></span>|<span data-ttu-id="dac9c-119">Message</span><span class="sxs-lookup"><span data-stu-id="dac9c-119">Message</span></span>|  
|------------|-------------|  
|<span data-ttu-id="dac9c-120">L'oggetto verrà cancellato (non elaborato)</span><span class="sxs-lookup"><span data-stu-id="dac9c-120">Object will be cleared (unprocessed)</span></span>|<span data-ttu-id="dac9c-121">Avviso</span><span class="sxs-lookup"><span data-stu-id="dac9c-121">Warning</span></span>|  
|<span data-ttu-id="dac9c-122">L'oggetto risulterà non valido</span><span class="sxs-lookup"><span data-stu-id="dac9c-122">Object would be invalid</span></span>|<span data-ttu-id="dac9c-123">Errore</span><span class="sxs-lookup"><span data-stu-id="dac9c-123">Error</span></span>|  
|<span data-ttu-id="dac9c-124">L'aggregazione verrà rimossa</span><span class="sxs-lookup"><span data-stu-id="dac9c-124">Aggregation would be dropped</span></span>|<span data-ttu-id="dac9c-125">Avviso</span><span class="sxs-lookup"><span data-stu-id="dac9c-125">Warning</span></span>|  
|<span data-ttu-id="dac9c-126">L'aggregazione flessibile verrà rimossa</span><span class="sxs-lookup"><span data-stu-id="dac9c-126">Flexible aggregation would be dropped</span></span>|<span data-ttu-id="dac9c-127">Avviso</span><span class="sxs-lookup"><span data-stu-id="dac9c-127">Warning</span></span>|  
|<span data-ttu-id="dac9c-128">Gli indici verranno rimossi</span><span class="sxs-lookup"><span data-stu-id="dac9c-128">Indexes will be dropped</span></span>|<span data-ttu-id="dac9c-129">Avviso</span><span class="sxs-lookup"><span data-stu-id="dac9c-129">Warning</span></span>|  
|<span data-ttu-id="dac9c-130">Gli oggetti che non sono figli verranno elaborati</span><span class="sxs-lookup"><span data-stu-id="dac9c-130">Non-child object will be processed</span></span>|<span data-ttu-id="dac9c-131">Avviso</span><span class="sxs-lookup"><span data-stu-id="dac9c-131">Warning</span></span>|  
  
 <span data-ttu-id="dac9c-132">**Elabora oggetto**</span><span class="sxs-lookup"><span data-stu-id="dac9c-132">**Process Object**</span></span>  
 <span data-ttu-id="dac9c-133">Consente di selezionare gli oggetti dipendenti che si desidera includere nell'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="dac9c-133">Select the dependent objects that you want to process with the processing operation.</span></span> <span data-ttu-id="dac9c-134">Sarà necessario elaborare gli oggetti dipendenti non selezionati al termine dell'operazione di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="dac9c-134">Dependent objects that are not selected must be processed after the processing operation is finished.</span></span> <span data-ttu-id="dac9c-135">In caso contrario, non sarà possibile utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="dac9c-135">Otherwise, they cannot be used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac9c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dac9c-136">See Also</span></span>  
 <span data-ttu-id="dac9c-137">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="dac9c-137">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="dac9c-138">Finestra di dialogo elabora &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="dac9c-138">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
