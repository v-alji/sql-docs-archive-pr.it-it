---
title: Nascondere un elemento (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.visibility.f1
- "10503"
ms.assetid: 9d78f8de-959b-456f-8947-687fa6e2ba91
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56e834204698369687528c622cf6167a492766f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626542"
---
# <a name="hide-an-item-report-builder-and-ssrs"></a><span data-ttu-id="74bb3-102">Nascondere un elemento (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="74bb3-102">Hide an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="74bb3-103">Impostare la visibilità di un elemento del report quando si desidera nascondere in modo condizionale un elemento in base a un parametro del report o ad altre espressioni specificate.</span><span class="sxs-lookup"><span data-stu-id="74bb3-103">Set the visibility of a report item when you want to conditionally hide an item based on a report parameter or some other expression that you specify.</span></span>

 <span data-ttu-id="74bb3-104">È inoltre possibile progettare un report per consentire all'utente di attivare o disattivare la visualizzazione di elementi di report facendo clic su caselle di testo nel report, ad esempio per un report drill-down.</span><span class="sxs-lookup"><span data-stu-id="74bb3-104">You can also design a report to allow the user to toggle the visibility of report items based on clicking text boxes in the report, for example, for a drilldown report.</span></span> <span data-ttu-id="74bb3-105">Per altre informazioni, vedere [Aggiungere un'azione Espandi o Comprimi a un elemento &#40;Generatore report e SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="74bb3-105">For more information, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="74bb3-106">Le procedure descritte di seguito illustrano il modo in cui visualizzare o nascondere un elemento di report in un report di cui è stato eseguito il rendering in base a una costante oppure a un'espressione.</span><span class="sxs-lookup"><span data-stu-id="74bb3-106">The following procedures describe how to show or hide a report item in a rendered report based on a constant or an expression.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-hide-a-report-item"></a><span data-ttu-id="74bb3-107">Per nascondere un elemento di report</span><span class="sxs-lookup"><span data-stu-id="74bb3-107">To hide a report item</span></span>

1.  <span data-ttu-id="74bb3-108">Nella visualizzazione di progettazione report fare clic con il pulsante destro del mouse sull'elemento del report e aprire la relativa pagina **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="74bb3-108">In report design view, right-click the report item and open its **Properties** page.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="74bb3-109">Per selezionare un'intera tabella o un'area dati matrice, fare clic nell'area dati per selezionarla, fare clic con il pulsante destro del mouse su una riga, una colonna oppure sul punto di controllo in angolo e quindi scegliere **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="74bb3-109">To select an entire table or matrix data region, click in the data region to select it, right-click a row, column, or corner handle, and then click **Tablix Properties**.</span></span>

2.  <span data-ttu-id="74bb3-110">Fare clic su **visibilità.**</span><span class="sxs-lookup"><span data-stu-id="74bb3-110">Click **Visibility.**</span></span>

3.  <span data-ttu-id="74bb3-111">In **Quando il report viene eseguito inizialmente**specificare se nascondere l'elemento la prima volta che il report viene visualizzato:</span><span class="sxs-lookup"><span data-stu-id="74bb3-111">In **When the report is initially run**, specify whether to hide the item when you first view the report:</span></span>

    -   <span data-ttu-id="74bb3-112">Per visualizzare l'elemento, fare clic su **Mostra**.</span><span class="sxs-lookup"><span data-stu-id="74bb3-112">To display the item, click **Show**.</span></span>

    -   <span data-ttu-id="74bb3-113">Per nascondere l'elemento., fare clic su **Nascondi**.</span><span class="sxs-lookup"><span data-stu-id="74bb3-113">To hide the item, click **Hide**.</span></span>

    -   <span data-ttu-id="74bb3-114">Per specificare un'espressione valutata in fase di esecuzione, fare clic su **Mostra o nascondi in base a un'espressione**.</span><span class="sxs-lookup"><span data-stu-id="74bb3-114">To specify an expression that is evaluated at run-time, click **Show or hide based on an expression**.</span></span> <span data-ttu-id="74bb3-115">Digitare l'espressione oppure fare clic sul pulsante dell'espressione (**fx**) per creare l'espressione nella finestra di dialogo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="74bb3-115">Type the expression or click the expression (**fx**) button to create the expression in the **Expression** dialog box.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="74bb3-116">Quando si specifica un'espressione per la visibilità, viene impostata la proprietà Hidden dell'elemento di report, come mostrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="74bb3-116">When you specify an expression for visibility, you are setting the Hidden property of the report item, as shown in the following image.</span></span> <span data-ttu-id="74bb3-117">L'espressione valutata consente di mostrare l'elemento di report quando il valore è False e di nasconderlo quando il valore è True.</span><span class="sxs-lookup"><span data-stu-id="74bb3-117">The evaluated expression shows the report item when the value is False, and hides the report item when the value is True.</span></span> 
        > <span data-ttu-id="74bb3-118">![Finestra di dialogo Properties_Visibility e proprietà Hidden](../media/hiddenproperty-propertiesvisibility.png "Finestra di dialogo Properties_Visibility e proprietà Hidden")</span><span class="sxs-lookup"><span data-stu-id="74bb3-118">![Properties_Visibility dialog and Hidden property](../media/hiddenproperty-propertiesvisibility.png "Properties_Visibility dialog and Hidden property")</span></span>

4.  <span data-ttu-id="74bb3-119">Fare clic su **OK** due volte.</span><span class="sxs-lookup"><span data-stu-id="74bb3-119">Click **OK** twice.</span></span>

### <a name="to-hide-static-rows-in-a-table-matrix-or-list"></a><span data-ttu-id="74bb3-120">Per nascondere le righe statiche di una tabella, matrice o elenco</span><span class="sxs-lookup"><span data-stu-id="74bb3-120">To hide static rows in a table, matrix, or list</span></span>

1.  <span data-ttu-id="74bb3-121">In visualizzazione progettazione report fare clic sulla tabella, sulla matrice o sull'elenco per visualizzare gli handle di riga e di colonna.</span><span class="sxs-lookup"><span data-stu-id="74bb3-121">In report design view, click the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="74bb3-122">Fare clic con il pulsante destro del mouse sull'handle di riga e quindi scegliere **Visibilità righe**.</span><span class="sxs-lookup"><span data-stu-id="74bb3-122">Right-click the row handle, and then click **Row Visibility**.</span></span> <span data-ttu-id="74bb3-123">Verrà visualizzata la finestra di dialogo **Visibilità righe** .</span><span class="sxs-lookup"><span data-stu-id="74bb3-123">The **Row Visibility** dialog box opens.</span></span>

3.  <span data-ttu-id="74bb3-124">Per impostare la visibilità, eseguire i passaggi 3 e 4 della prima procedura.</span><span class="sxs-lookup"><span data-stu-id="74bb3-124">To set the visibility, follow steps 3 and 4 in the first procedure.</span></span>

### <a name="to-hide-static-columns-in-a-table-matrix-or-list"></a><span data-ttu-id="74bb3-125">Per nascondere colonne statiche in una tabella, in una matrice o in un elenco</span><span class="sxs-lookup"><span data-stu-id="74bb3-125">To hide static columns in a table, matrix, or list</span></span>

1.  <span data-ttu-id="74bb3-126">In visualizzazione Progettazione selezionare la tabella, la matrice o l'elenco per visualizzare gli handle di riga e di colonna.</span><span class="sxs-lookup"><span data-stu-id="74bb3-126">In Design view, select the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="74bb3-127">Fare clic con il pulsante destro del mouse sull'handle di colonna e quindi scegliere **Visibilità colonne**.</span><span class="sxs-lookup"><span data-stu-id="74bb3-127">Right-click the column handle, and then click **Column Visibility**.</span></span>

3.  <span data-ttu-id="74bb3-128">Nella finestra di dialogo **Visibilità colonne** eseguire i passaggi 3 e 4 della prima procedura.</span><span class="sxs-lookup"><span data-stu-id="74bb3-128">In the **Column Visibility** dialog box, follow steps 3 and 4 in the first procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="74bb3-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74bb3-129">See Also</span></span>
 <span data-ttu-id="74bb3-130">[Azione di drill-down &#40;Generatore report e ssrs&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [aggiungere un'azione Espandi o Comprimi a un elemento &#40;Generatore report e](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) SSRS&#41;espressione &#40;Generatore report [e SSRS](../report-design/expression-examples-report-builder-and-ssrs.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="74bb3-130">[Drilldown Action &#40;Report Builder and SSRS&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) [Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span></span>


