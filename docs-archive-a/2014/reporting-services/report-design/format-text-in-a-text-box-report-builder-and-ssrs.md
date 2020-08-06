---
title: Formattare il testo in una casella di testo (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df0794b5-96b0-4034-bd17-1be7f31e29db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 522bc420f77b2e5e9d2163c28d3d688b7c47883c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627091"
---
# <a name="format-text-in-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="ec60a-102">Formattare il testo in una casella di testo (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ec60a-102">Format Text in a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ec60a-103">È possibile formattare qualsiasi parte del testo all'interno di una casella di testo in modo indipendente e combinare testo segnaposto e testo statico in un'unica casella di testo.</span><span class="sxs-lookup"><span data-stu-id="ec60a-103">You can format any part of the text within a text box independently, and mix placeholder text and static text in one text box.</span></span> <span data-ttu-id="ec60a-104">La possibilità di combinare i formati e aggiungere testo segnaposto consente di creare stampe unione o modelli per il testo nel report.</span><span class="sxs-lookup"><span data-stu-id="ec60a-104">This ability to mix formats and add placeholder text enables you to create mail merges or templates for text in your report.</span></span> <span data-ttu-id="ec60a-105">Qualsiasi espressione può essere definita e formattata separatamente utilizzando un segnaposto.</span><span class="sxs-lookup"><span data-stu-id="ec60a-105">Any expression can be defined and formatted separately using a placeholder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-combine-multiple-formats-in-a-text-box"></a><span data-ttu-id="ec60a-106">Per combinare più formati in una casella di testo</span><span class="sxs-lookup"><span data-stu-id="ec60a-106">To combine multiple formats in a text box</span></span>  
  
1.  <span data-ttu-id="ec60a-107">Fare clic su **Casella testo** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="ec60a-107">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="ec60a-108">Fare clic nell'area di progettazione, quindi trascinare il mouse per creare una casella delle dimensioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="ec60a-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
2.  <span data-ttu-id="ec60a-109">All'interno della casella di testo selezionare il testo che si desidera formattare.</span><span class="sxs-lookup"><span data-stu-id="ec60a-109">Inside the text box, select the text you want to format.</span></span>  
  
3.  <span data-ttu-id="ec60a-110">Fare clic con il pulsante destro del mouse sul testo selezionato, quindi scegliere **Proprietà testo**.</span><span class="sxs-lookup"><span data-stu-id="ec60a-110">Right-click the selected text, and click **Text Properties**.</span></span>  
  
4.  <span data-ttu-id="ec60a-111">Impostare le opzioni di formattazione.</span><span class="sxs-lookup"><span data-stu-id="ec60a-111">Set formatting options.</span></span> <span data-ttu-id="ec60a-112">Ad esempio, nella scheda **Generale** :</span><span class="sxs-lookup"><span data-stu-id="ec60a-112">For example, on the **General** tab:</span></span>  
  
    -   <span data-ttu-id="ec60a-113">**Descrizione comando** Digitare un testo o un'espressione che restituisca una descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="ec60a-113">**Tooltip** Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="ec60a-114">La descrizione comando viene visualizzata quando l'utente posiziona il puntatore del mouse su un elemento nel report.</span><span class="sxs-lookup"><span data-stu-id="ec60a-114">The ToolTip appears when the user pauses the pointer over the item in a report</span></span>  
  
    -   <span data-ttu-id="ec60a-115">**Tipo di markup** Selezionare un'opzione per indicare come verrà visualizzato il testo selezionato:</span><span class="sxs-lookup"><span data-stu-id="ec60a-115">**Markup type** Select an option to indicate how the selected text will be rendered:</span></span>  
  
         <span data-ttu-id="ec60a-116">**Testo normale** Il testo selezionato viene visualizzato come testo normale.</span><span class="sxs-lookup"><span data-stu-id="ec60a-116">**Plain Text** Display the selected text as simple text.</span></span> <span data-ttu-id="ec60a-117">Il testo in formato HTML verrà gestito come testo letterale.</span><span class="sxs-lookup"><span data-stu-id="ec60a-117">HTML will be treated as literal text.</span></span>  
  
         <span data-ttu-id="ec60a-118">**HTML**  Il testo selezionato viene visualizzato in formato HTML.</span><span class="sxs-lookup"><span data-stu-id="ec60a-118">**HTML**  Display the selected text as HTML.</span></span> <span data-ttu-id="ec60a-119">Se il valore dell'espressione del segnaposto contiene tag HTML validi, questi verranno visualizzati in formato HTML.</span><span class="sxs-lookup"><span data-stu-id="ec60a-119">If the expression value of the placeholder contains valid HTML tags, these tags will be rendered as HTML.</span></span> <span data-ttu-id="ec60a-120">Per altre informazioni, vedere [Importazione di codice HTML in un report &#40;Generatore report e SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ec60a-120">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="ec60a-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec60a-121">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="ec60a-122">Ripetere i passaggi da 2 a 5 per la parte di testo rimanente che si desidera formattare.</span><span class="sxs-lookup"><span data-stu-id="ec60a-122">Repeat steps 2 through 5 for the remaining text you want to format.</span></span>  
  
### <a name="to-format-text-and-placeholders-differently-in-the-same-text-box"></a><span data-ttu-id="ec60a-123">Per formattare in modo diverso testo e segnaposti presenti nella stessa casella di testo</span><span class="sxs-lookup"><span data-stu-id="ec60a-123">To format text and placeholders differently in the same text box</span></span>  
  
1.  <span data-ttu-id="ec60a-124">Fare clic su **Elenco** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="ec60a-124">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="ec60a-125">Fare clic nell'area di progettazione, quindi trascinare il mouse per creare una casella delle dimensioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="ec60a-125">Click the design surface, and then drag to create a box that is the size you want.</span></span> <span data-ttu-id="ec60a-126">Verrà visualizzata la finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="ec60a-126">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="ec60a-127">È possibile utilizzare un set di dati condiviso o un set di dati incorporato nel report.</span><span class="sxs-lookup"><span data-stu-id="ec60a-127">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="ec60a-128">Per altre informazioni, fare clic su [Finestra di dialogo Proprietà set di dati, Query &#40;Generatore report&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) o [Finestra di dialogo Proprietà set di dati, Query](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="ec60a-128">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="ec60a-129">Fare clic su **Casella testo** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="ec60a-129">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="ec60a-130">Fare clic nell'elenco, quindi trascinare il mouse per creare una casella con le dimensioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="ec60a-130">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="ec60a-131">Digitare un'etichetta nella casella di testo, ad esempio **Mio campo**:.</span><span class="sxs-lookup"><span data-stu-id="ec60a-131">Type a label in the text box - for example, **My Field**:.</span></span>  
  
4.  <span data-ttu-id="ec60a-132">Trascinare un campo dal set di dati nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="ec60a-132">Drag a field from your dataset into the text box.</span></span> <span data-ttu-id="ec60a-133">Verrà creato un segnaposto per il campo.</span><span class="sxs-lookup"><span data-stu-id="ec60a-133">A placeholder is created for your field.</span></span>  
  
5.  <span data-ttu-id="ec60a-134">Per una formattazione di base, selezionare il testo segnaposto, quindi fare clic su una delle opzioni di formattazione nel gruppo **Carattere** della scheda **Home** . Fare clic, ad esempio, sul pulsante **Grassetto**.</span><span class="sxs-lookup"><span data-stu-id="ec60a-134">For basic formatting, select the placeholder text and then click one of the formatting options in the **Font** group on the **Home** tab. For example, click the **Bold** button.</span></span>  
  
     <span data-ttu-id="ec60a-135">Per applicare più opzioni di formattazione, fare clic con il pulsante destro del mouse sul testo segnaposto, quindi fare clic su **Proprietà segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="ec60a-135">For more formatting options, right-click the placeholder text, and then click **Placeholder Properties**.</span></span>  
  
6.  <span data-ttu-id="ec60a-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec60a-136">Click **OK**.</span></span> <span data-ttu-id="ec60a-137">Nella visualizzazione Progettazione report, la casella di testo conterrà "**Mio campo**: [*NomeCampo*]", dove *NomeCampo* è il nome del campo.</span><span class="sxs-lookup"><span data-stu-id="ec60a-137">In report design view, the text box should contain "**My Field**: [*FieldName*]", where *FieldName* is the name of your field.</span></span>  
  
7.  <span data-ttu-id="ec60a-138">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ec60a-138">Click **Run**.</span></span>  
  
 <span data-ttu-id="ec60a-139">L'elenco viene ripetuto una volta per ogni valore nel campo e il segnaposto *NomeCampo* viene sostituito ogni volta dal valore di quel campo nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="ec60a-139">The list repeats one time for every value in the field, and the *FieldName* placeholder is replaced each time by the value of that field in the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec60a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec60a-140">See Also</span></span>  
 <span data-ttu-id="ec60a-141">[Caselle di testo &#40;Generatore report e SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec60a-141">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ec60a-142">[Formattazione di testo e segnaposto &#40;Generatore report e SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec60a-142">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ec60a-143">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec60a-143">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ec60a-144">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec60a-144">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ec60a-145">[Aggiungere il codice HTML a un report &#40;Generatore report e SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec60a-145">[Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ec60a-146">[Elenca &#40;Generatore report e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec60a-146">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ec60a-147">[Formattazione di numeri e date &#40;Generatore report e SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ec60a-147">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ec60a-148">Finestra di dialogo Proprietà segnaposto, Generale &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ec60a-148">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
