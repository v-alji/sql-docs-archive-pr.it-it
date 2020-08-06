---
title: Impostazione dati di training (creazione guidata modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytrainingdata.f1
ms.assetid: cb04deeb-0f89-4bba-b3f1-efccada16825
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87a802256d287a3e8e9e7fb65bbd91687cb71a4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635752"
---
# <a name="specify-the-training-data-data-mining-wizard"></a><span data-ttu-id="10c8a-102">Impostazione dati di training (Creazione guidata modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="10c8a-102">Specify the Training Data (Data Mining Wizard)</span></span>
  <span data-ttu-id="10c8a-103">Usare la pagina **Impostazione dati di training** per identificare le colonne da includere nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="10c8a-103">Use the **Specify the Training Data** page to identify which columns to include in the mining structure.</span></span> <span data-ttu-id="10c8a-104">È possibile selezionare le colonne da includere nella struttura anche se non vengono utilizzate in tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="10c8a-104">You can select columns to include in the structure even if you do not use them in all models.</span></span> <span data-ttu-id="10c8a-105">Ad esempio, se si vuole eseguire il drill-through delle colonne dal modello di data mining, è possibile includerle nella struttura ma non nel modello.</span><span class="sxs-lookup"><span data-stu-id="10c8a-105">For example, if you want to drill through to the columns from the mining model, you can include them in the structure but not in the model.</span></span>  
  
 <span data-ttu-id="10c8a-106">È necessaria almeno una colonna chiave per ogni tabella inclusa nella struttura.</span><span class="sxs-lookup"><span data-stu-id="10c8a-106">At least one key column is required for each table that is included in the structure.</span></span> <span data-ttu-id="10c8a-107">La colonna che si sceglie come chiave dipende dalla tabella (se tabella del case o tabella nidificata).</span><span class="sxs-lookup"><span data-stu-id="10c8a-107">The column that you pick as the key depends on whether the table is a case table or a nested table.</span></span> <span data-ttu-id="10c8a-108">Se è una tabella nidificata, la chiave è spesso anche la colonna stimabile, non la chiave esterna relazionale.</span><span class="sxs-lookup"><span data-stu-id="10c8a-108">If the table is a nested table, the key is often also the predictable column, not the relational foreign key.</span></span> <span data-ttu-id="10c8a-109">Per altre informazioni sulle tabelle annidate, vedere [Tabelle annidate &#40;Analysis Services - Data mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="10c8a-109">To learn about nested keys, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10c8a-110">Gli algoritmi di data mining differenti utilizzano le chiavi in modo differente.</span><span class="sxs-lookup"><span data-stu-id="10c8a-110">Different mining algorithms use keys differently.</span></span> <span data-ttu-id="10c8a-111">Per altre informazioni sui diversi tipi di chiavi, vedere [Tipi di contenuto &#40;Data mining&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="10c8a-111">To learn about the different kinds of keys, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="10c8a-112">**Per altre informazioni:** [Strutture di data mining &#40;Analysis Services - Data mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Colonne del modello di data mining](data-mining/mining-model-columns.md), [Creazione guidata modello di data mining &#40;Analysis Services - Data mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Creare una struttura di data mining relazionale](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="10c8a-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="10c8a-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="10c8a-113">Options</span></span>  
 <span data-ttu-id="10c8a-114">**Tabelle/Colonne**</span><span class="sxs-lookup"><span data-stu-id="10c8a-114">**Tables/Columns**</span></span>  
 <span data-ttu-id="10c8a-115">Consente di visualizzare le tabelle e le colonne selezionate nella pagina precedente della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="10c8a-115">Displays the tables and columns that you selected on the previous page of the wizard.</span></span>  
  
 **\<check box>**  
 <span data-ttu-id="10c8a-116">Consente di selezionare le colonne da includere nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="10c8a-116">Select the columns to include in the mining structure.</span></span>  
  
 <span data-ttu-id="10c8a-117">Se l'origine dati include tabelle nidificate o più viste, espandere l'elenco delle colonne per visualizzare le tabelle nidificate.</span><span class="sxs-lookup"><span data-stu-id="10c8a-117">If your data source includes nested tables or multiple views, expand the column list to view the nested tables.</span></span>  
  
 <span data-ttu-id="10c8a-118">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="10c8a-118">**Key**</span></span>  
 <span data-ttu-id="10c8a-119">Selezionare questa opzione per utilizzare la colonna come identificatore univoco per i dati.</span><span class="sxs-lookup"><span data-stu-id="10c8a-119">Select to use the column as a unique identifier for the data.</span></span>  
  
 <span data-ttu-id="10c8a-120">Per una tabella del case, la chiave è generalmente l'identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="10c8a-120">For a case table, the key is usually the unique identifier.</span></span>  
  
 <span data-ttu-id="10c8a-121">Per le tabelle annidate, **Key** indica l'identificatore di una riga nel contesto del case associato.</span><span class="sxs-lookup"><span data-stu-id="10c8a-121">For nested table, the **Key** indicates the identifier of a row in the context of the associated case.</span></span>  
  
 <span data-ttu-id="10c8a-122">**Input**</span><span class="sxs-lookup"><span data-stu-id="10c8a-122">**Input**</span></span>  
 <span data-ttu-id="10c8a-123">Selezionare questa opzione per utilizzare la colonna nella creazione di stime.</span><span class="sxs-lookup"><span data-stu-id="10c8a-123">Select to use the column in creating predictions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10c8a-124">Questa colonna è disponibile solo durante la creazione di un modello di data mining insieme alla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="10c8a-124">This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="10c8a-125">**Stimabile**</span><span class="sxs-lookup"><span data-stu-id="10c8a-125">**Predictable**</span></span>  
 <span data-ttu-id="10c8a-126">Selezionare questa opzione affinché la tabella o la colonna risulti stimabile sulla base di input futuri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="10c8a-126">Select to enable the table or column to be predicted based on additional future input.</span></span>  
  
 <span data-ttu-id="10c8a-127">Se inoltre si contrassegna tale colonna come stimabile, diventerà stimabile l'intera tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="10c8a-127">If you also mark a nested table as predictable, the whole nested table becomes predictable.</span></span> <span data-ttu-id="10c8a-128">Se nella tabella nidificata non è disponibile alcuna colonna contrassegnata come di input o stimabile, la tabella nidificata verrà visualizzata nella struttura di data mining, ma ignorata nel modello.</span><span class="sxs-lookup"><span data-stu-id="10c8a-128">If no columns in the nested table are marked as input or predictable, the nested table will appear in the mining structure, but will be ignored in the model.</span></span>  
  
 <span data-ttu-id="10c8a-129">**Nota** Questa colonna è disponibile solo quando si crea un modello di data mining insieme alla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="10c8a-129">**Note** This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="10c8a-130">**Suggerisci**</span><span class="sxs-lookup"><span data-stu-id="10c8a-130">**Suggest**</span></span>  
 <span data-ttu-id="10c8a-131">Fare clic su questo pulsante per aprire la finestra di dialogo **Suggerisci colonne correlate** , che esegue un'analisi di un campione di dati per identificare le colonne di input che in base al valore di entropia sono più strettamente in relazione con la colonna **Stimabile** selezionata.</span><span class="sxs-lookup"><span data-stu-id="10c8a-131">Click to open the **Suggest Related Columns** dialog box, which performs an analysis on a sample of data to identify input columns that show the greatest relationship to the selected **Predictable** column based on entropy.</span></span> <span data-ttu-id="10c8a-132">Questa analisi si applica inoltre alle colonne della tabella nidificata o alle strutture di data mining basate su origini OLAP.</span><span class="sxs-lookup"><span data-stu-id="10c8a-132">This analysis also applies to nested table columns or mining structures that are based on OLAP sources.</span></span>  
  
 <span data-ttu-id="10c8a-133">**Nota** Questa colonna è disponibile solo quando si crea un modello di data mining insieme alla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="10c8a-133">**Note** This column only available when you are creating a mining model together with the mining structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c8a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10c8a-134">See Also</span></span>  
 <span data-ttu-id="10c8a-135">[Guida sensibile al contesto della creazione guidata modello di data mining &#40;Analysis Services-&#41;di data mining](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="10c8a-135">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="10c8a-136">[Suggerisci colonne correlate &#40;creazione guidata modello di data mining&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="10c8a-136">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="10c8a-137">[Impostazione tipi di tabella &#40;creazione guidata modello di data mining&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="10c8a-137">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="10c8a-138">Specificare il tipo di dati e il contenuto della colonna &#40;creazione guidata modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="10c8a-138">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
