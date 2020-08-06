---
title: Aggiungere, spostare o eliminare una casella di testo (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f042cf81-d933-4ac7-9287-c074a46bde98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd85415fd2f0bac2a37b3fbda06795e10f351b19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723463"
---
# <a name="add-move-or-delete-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="9a6e2-102">Aggiungere, spostare o eliminare una casella di testo (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9a6e2-102">Add, Move, or Delete a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9a6e2-103">Le caselle di testo costituiscono l'elemento utilizzato più di frequente nei report.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-103">Text boxes are the most commonly used report item in reports.</span></span> <span data-ttu-id="9a6e2-104">È possibile aggiungere una casella di testo al corpo del report per visualizzare informazioni diverse, ad esempio titoli, scelte di parametri, campi incorporati e date.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-104">You can add a text box to the report body to display information such as titles, parameter choices, built-in fields, and dates.</span></span>  
  
 <span data-ttu-id="9a6e2-105">Ogni cella in una tabella o una matrice è realmente una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-105">Every cell in a table or matrix is really a text box.</span></span> <span data-ttu-id="9a6e2-106">Quasi tutti i dati del report visualizzati in un report con tabelle e matrici rappresentano il risultato di Elaborazione report che valuta il contenuto di ogni casella di testo del report.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-106">Almost all report data displayed in a report with tables and matrices is the result of the report processor evaluating the contents of each text box in the report.</span></span> <span data-ttu-id="9a6e2-107">Di conseguenza, è possibile formattare le celle nella stessa modalità con cui si formatterebbero le altre caselle di testo all'esterno dell'area dati.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-107">As such, you can format cells in the same way you would format other text boxes outside the data region.</span></span>  
  
 <span data-ttu-id="9a6e2-108">Per aggiungere una casella di testo a un'area dati elenco, è necessario prima aggiungere la casella di testo e trascinarla nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-108">To add a text box to a list data region, you must first add the text box and then drag it into the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a6e2-109">Quando si fa clic su una casella di testo, è immediatamente possibile modificare il testo nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-109">When you click a text box, you're immediately editing the text in the text box.</span></span> <span data-ttu-id="9a6e2-110">Per selezionare la casella di testo e non il testo in essa contenuto, premere ESC.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-110">To select the text box itself, not the text in it, press ESC.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-text-box"></a><span data-ttu-id="9a6e2-111">Per aggiungere una casella di testo</span><span class="sxs-lookup"><span data-stu-id="9a6e2-111">To add a text box</span></span>  
  
1.  <span data-ttu-id="9a6e2-112">Nella visualizzazione Progettazione fare clic su **Casella di testo** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-112">On the **Insert** tab in Design view, click **Text Box**.</span></span>  
  
2.  <span data-ttu-id="9a6e2-113">Nell'area di progettazione fare clic su una casella, quindi trascinarla fino a raggiungere le dimensioni desiderate per la casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-113">On the design surface, click and then drag a box to the desired size of the text box.</span></span> <span data-ttu-id="9a6e2-114">In alternativa, fare clic nell'area di progettazione per creare una casella di testo di dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-114">Alternatively, click the design surface to create a text box of default size.</span></span>  
  
### <a name="to-add-a-text-box-in-a-list"></a><span data-ttu-id="9a6e2-115">Per aggiungere una casella di testo a un elenco</span><span class="sxs-lookup"><span data-stu-id="9a6e2-115">To add a text box in a list</span></span>  
  
1.  <span data-ttu-id="9a6e2-116">Nella visualizzazione Progettazione report fare clic su **Elenco** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-116">On the **Insert** tab in report design view, click **List**.</span></span>  
  
2.  <span data-ttu-id="9a6e2-117">Nell'area di progettazione fare clic su una casella, quindi trascinarla fino a raggiungere le dimensioni desiderate per l'elenco.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-117">On the design surface, click and then drag a box to the desired size of the list.</span></span> <span data-ttu-id="9a6e2-118">In alternativa, fare clic nell'area di progettazione per creare un elenco di dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-118">Alternatively, click the design surface to create a list of default size.</span></span>  
  
3.  <span data-ttu-id="9a6e2-119">Fare clic su **Casella testo** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-119">On the **Insert** tab, click **Text Box**.</span></span>  
  
4.  <span data-ttu-id="9a6e2-120">Nell'area di progettazione, fare clic su una casella, quindi trascinarla fino a raggiungere le dimensioni desiderate per la casella di testo all'interno dell'elenco aggiunto nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-120">On the design surface, click and then drag a box to the desired size of the text box inside the list you added in step 1.</span></span> <span data-ttu-id="9a6e2-121">In alternativa, fare clic nell'area di progettazione all'interno dell'elenco per creare una casella di testo di dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-121">Alternatively, click the design surface inside the list to create a text box of default size.</span></span>  
  
5.  <span data-ttu-id="9a6e2-122">Per verificare che la casella di testo sia nidificata correttamente nell'elenco, selezionarla.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-122">To confirm the text box is correctly nested inside the list, select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a6e2-123">Se facendo clic nella casella di testo è stata attivata la modalità di modifica, premere ESC per selezionare la casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-123">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
6.  <span data-ttu-id="9a6e2-124">Nel riquadro Proprietà verificare che la proprietà **Parent** sia costituita dal rettangolo aggiunto automaticamente all'area dati elenco.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-124">In the Properties pane, verify that the **Parent** property is the rectangle that was automatically added to the list data region.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a6e2-125">Se il riquadro Proprietà non è visualizzato, selezionare **Proprietà** nella scheda **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="9a6e2-125">If the Properties pane is not visible, check **Properties** on the **View** tab.</span></span>  
  
### <a name="to-move-a-text-box"></a><span data-ttu-id="9a6e2-126">Per spostare una casella di testo</span><span class="sxs-lookup"><span data-stu-id="9a6e2-126">To move a text box</span></span>  
  
1.  <span data-ttu-id="9a6e2-127">Nella visualizzazione Progettazione report fare clic in un punto vuoto qualsiasi all'interno della casella di testo per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-127">In report design view, click any empty space within the text box to select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a6e2-128">Se facendo clic nella casella di testo è stata attivata la modalità di modifica, premere ESC per selezionare la casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-128">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
2.  <span data-ttu-id="9a6e2-129">Fare clic sul quadratino della casella di testo e trascinare quest'ultima nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-129">Click the text box handle and drag the text box to the new location.</span></span> <span data-ttu-id="9a6e2-130">In alternativa, è possibile utilizzare i tasti di direzione per spostare orizzontalmente o verticalmente una casella di testo selezionata.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-130">Alternatively, you can use the arrow keys to move a selected text box horizontally or vertically.</span></span> <span data-ttu-id="9a6e2-131">Per spostare la casella di testo di piccoli incrementi nell'area di progettazione, tenere premuto il tasto CTRL contemporaneamente ai tasti direzione.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-131">To move the text box in smaller increments on the design surface, hold down CTRL plus the arrow keys.</span></span>  
  
### <a name="to-delete-a-text-box"></a><span data-ttu-id="9a6e2-132">Per eliminare una casella di testo</span><span class="sxs-lookup"><span data-stu-id="9a6e2-132">To delete a text box</span></span>  
  
1.  <span data-ttu-id="9a6e2-133">Nella visualizzazione Progettazione report fare clic con il pulsante destro del mouse in un punto vuoto all'interno della casella di testo per selezionarlo, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-133">In report design view, right-click any empty space within the text box to select it, and then click **Delete**.</span></span> <span data-ttu-id="9a6e2-134">In alternativa, fare clic in un punto vuoto all'interno della casella di testo e quindi premere CANC.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-134">Alternatively, click any empty space within the text box, and then press DELETE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a6e2-135">Se facendo clic nella casella di testo è stata attivata la modalità di modifica, premere ESC per selezionare la casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9a6e2-135">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6e2-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a6e2-136">See Also</span></span>  
 <span data-ttu-id="9a6e2-137">[Caselle di testo &#40;Generatore report e SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9a6e2-137">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9a6e2-138">[Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9a6e2-138">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9a6e2-139">Tasti di scelta rapida &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="9a6e2-139">Keyboard Shortcuts &#40;Report Builder&#41;</span></span>](../report-builder/keyboard-shortcuts-report-builder.md)  
  
  
