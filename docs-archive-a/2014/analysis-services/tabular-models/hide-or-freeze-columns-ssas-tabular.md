---
title: Nascondere o bloccare colonne (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.hideunhidecolumnsdb.f1
ms.assetid: 5407aee5-6a07-4559-a2ba-2ca00a242f02
author: minewiskan
ms.author: owend
ms.openlocfilehash: 71398eecbc342b4e3f9c2445fef3023132266dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712515"
---
# <a name="hide-or-freeze-columns-ssas-tabular"></a><span data-ttu-id="987b9-102">Nascondere o bloccare colonne (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="987b9-102">Hide or Freeze Columns (SSAS Tabular)</span></span>
  <span data-ttu-id="987b9-103">In Progettazione modelli, se in una tabella sono presenti colonne che non si desidera visualizzare, è possibile nasconderle temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="987b9-103">In the model designer, if there are columns that you don't want to display in a table, you can temporarily hide them.</span></span> <span data-ttu-id="987b9-104">Nascondendo una colonna si ottiene maggiore spazio sullo schermo per aggiungerne di nuove o per utilizzare solo le colonne di dati rilevanti.</span><span class="sxs-lookup"><span data-stu-id="987b9-104">Hiding a column gives you more room on the screen to add new columns or to work with only relevant columns of data.</span></span> <span data-ttu-id="987b9-105">È possibile nascondere e scoprire colonne dal menu **Colonna** in Progettazione modelli e dal menu di scelta rapida disponibile in ogni intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="987b9-105">You can hide and unhide columns from the **Column** menu in the model designer, and from the right-click menu available from each column header.</span></span> <span data-ttu-id="987b9-106">Per mantenere visibile un'area di un modello durante lo scorrimento a un'altra area del modello, è possibile bloccare colonne specifiche in un'area.</span><span class="sxs-lookup"><span data-stu-id="987b9-106">To keep an area of a model visible while you scroll to another area of the model, you can lock specific columns in one area by freezing them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="987b9-107">La possibilità di nascondere colonne non dovrebbe essere utilizzata per la sicurezza dei dati, ma solo per semplificare e abbreviare l'elenco di colonne visibili in Progettazione modelli o nei report.</span><span class="sxs-lookup"><span data-stu-id="987b9-107">The ability to hide columns is not intended to be used for data security, only to simplify and shorten the list of columns visible in the model designer or reports.</span></span> <span data-ttu-id="987b9-108">Per proteggere i dati, è possibile definire ruoli di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="987b9-108">To secure data, you can define security roles.</span></span> <span data-ttu-id="987b9-109">I ruoli possono limitare la visualizzazione di metadati e dati in base agli oggetti definiti nel ruolo.</span><span class="sxs-lookup"><span data-stu-id="987b9-109">Roles can limit viewable metadata and data to only those objects defined in the role.</span></span> <span data-ttu-id="987b9-110">Per altre informazioni, vedere [Ruoli &#40;SSAS tabulare&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="987b9-110">For more information, see [Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="987b9-111">Quando si nasconde una colonna, è possibile scegliere se nasconderla mentre si lavora in Progettazione modelli o nei report.</span><span class="sxs-lookup"><span data-stu-id="987b9-111">When you hide a column, you have the option to hide the column while you are working in the model designer or in reports.</span></span> <span data-ttu-id="987b9-112">Se si nascondono tutte le colonne, l'intera tabella appare vuota in Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="987b9-112">If you hide all columns, the entire table appears blank in the model designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="987b9-113">Se sono molte le colonne da nascondere, è possibile creare una prospettiva anziché nascondere e scoprire colonne.</span><span class="sxs-lookup"><span data-stu-id="987b9-113">If you have many columns to hide, you can create a perspective instead of hiding and unhiding columns.</span></span> <span data-ttu-id="987b9-114">Una prospettiva è una vista personalizzata dei dati tramite cui si semplifica l'utilizzo di un subset di dati correlati.</span><span class="sxs-lookup"><span data-stu-id="987b9-114">A perspective is a custom view of the data that makes it easier to work with subset of related data.</span></span> <span data-ttu-id="987b9-115">Per altre informazioni, vedere [Creare e gestire prospettive &#40;SSAS tabulare&#41;](perspectives-ssas-tabular.md)</span><span class="sxs-lookup"><span data-stu-id="987b9-115">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md)</span></span>  
  
### <a name="to-hide-an-individual-column"></a><span data-ttu-id="987b9-116">Per nascondere una singola colonna</span><span class="sxs-lookup"><span data-stu-id="987b9-116">To hide an individual column</span></span>  
  
1.  <span data-ttu-id="987b9-117">In Progettazione modelli selezionare la tabella contenente la colonna che si desidera nascondere.</span><span class="sxs-lookup"><span data-stu-id="987b9-117">In the model designer, select the table that contains the column that you want to hide.</span></span>  
  
2.  <span data-ttu-id="987b9-118">Fare clic con il pulsante destro del mouse sulla colonna, selezionare **Nascondi colonne**, quindi fare clic su **Da finestra progettazione e report**, **Da report**oppure su **Da finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="987b9-118">Right-click the column, then click **Hide Columns**, and then click **From Designer and Reports**, **From Reports**, or **From Designer**.</span></span>  
  
### <a name="to-hide-multiple-columns"></a><span data-ttu-id="987b9-119">Per nascondere più colonne</span><span class="sxs-lookup"><span data-stu-id="987b9-119">To hide multiple columns</span></span>  
  
1.  <span data-ttu-id="987b9-120">In Progettazione modelli selezionare la tabella contenente le colonne che si desidera nascondere.</span><span class="sxs-lookup"><span data-stu-id="987b9-120">In the model designer, select the table that contains the columns that you want to hide.</span></span>  
  
2.  <span data-ttu-id="987b9-121">Fare clic sul menu **Colonne** , quindi scegliere **Nascondi e scopri**.</span><span class="sxs-lookup"><span data-stu-id="987b9-121">Click on the **Columns** menu, and then click **Hide and Unhide**.</span></span>  
  
3.  <span data-ttu-id="987b9-122">Nella finestra di dialogo **Nascondi e scopri colonne** individuare ogni colonna che si desidera nascondere, quindi deselezionare una o entrambe le opzioni **In Designer** (Nella finestra di progettazione) e **In Reports**(Nei report).</span><span class="sxs-lookup"><span data-stu-id="987b9-122">In the **Hide and Unhide Columns** dialog box, locate each column that you want to hide, and then deselect one or both of **In Designer** and **In Reports**.</span></span>  
  
4.  <span data-ttu-id="987b9-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="987b9-123">Click **OK**.</span></span>  
  
### <a name="to-freeze-columns"></a><span data-ttu-id="987b9-124">Per bloccare le colonne</span><span class="sxs-lookup"><span data-stu-id="987b9-124">To freeze columns</span></span>  
  
1.  <span data-ttu-id="987b9-125">In Progettazione modelli selezionare la tabella contenente le colonne che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="987b9-125">In the model designer, select the table that contains the columns that you want to freeze.</span></span>  
  
2.  <span data-ttu-id="987b9-126">Selezionare una o più colonne da bloccare.</span><span class="sxs-lookup"><span data-stu-id="987b9-126">Select one or more columns to freeze.</span></span>  
  
3.  <span data-ttu-id="987b9-127">Fare clic sul menu **Colonne** , quindi scegliere **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="987b9-127">Click on the **Columns** menu, and then click **Freeze**..</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="987b9-128">Quando una colonna viene bloccata, viene spostata a sinistra della tabella (o davanti) nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="987b9-128">When a column(s) is frozen, it is moved to left (or front) of the table in the designer.</span></span> <span data-ttu-id="987b9-129">Se sbloccata, la colonna non torna nella relativa posizione originale.</span><span class="sxs-lookup"><span data-stu-id="987b9-129">Unfreezing the column does not move it back to its original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987b9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="987b9-130">See Also</span></span>  
 <span data-ttu-id="987b9-131">[Tabelle e colonne &#40;SSAS tabulare&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="987b9-131">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="987b9-132">[Prospettive &#40;SSAS tabulare&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="987b9-132">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="987b9-133">Ruoli &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="987b9-133">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
