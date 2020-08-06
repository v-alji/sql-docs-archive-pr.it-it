---
title: Creare una colonna calcolata (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.as.daxref.CreataCalculatedColumn.f1
ms.assetid: 59440510-2d76-41dc-9b55-edc15259f9da
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdb56ffb2b42aa8225b7eff76b11315ea511fd81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711035"
---
# <a name="create-a-calculated-column-ssas-tabular"></a><span data-ttu-id="c01d5-102">Creare una colonna calcolata (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="c01d5-102">Create a Calculated Column (SSAS Tabular)</span></span>
  <span data-ttu-id="c01d5-103">Le colonne calcolate consentono di aggiungere nuovi dati al modello.</span><span class="sxs-lookup"><span data-stu-id="c01d5-103">Calculated columns allow you to add new data to your model.</span></span> <span data-ttu-id="c01d5-104">Anziché incollare o importare i valori nella colonna, viene creata una formula DAX che definisce i valori a livello di riga della colonna.</span><span class="sxs-lookup"><span data-stu-id="c01d5-104">Instead of pasting or importing values into the column, you create a DAX formula that defines the column's row level values.</span></span> <span data-ttu-id="c01d5-105">I valori in ogni riga di una colonna calcolata vengono calcolati e popolati quando si crea una formula valida e si fa clic su INVIO.</span><span class="sxs-lookup"><span data-stu-id="c01d5-105">The values in each row of a calculated column are calculated and populated when you create a valid formula and then click ENTER.</span></span> <span data-ttu-id="c01d5-106">La colonna calcolata può essere aggiunta a un'applicazione di analisi o di creazione di report come qualsiasi altra colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="c01d5-106">The calculated column can then be added to a reporting or analysis application just as would any other column of data.</span></span> <span data-ttu-id="c01d5-107">In questo argomento viene descritto come creare una nuova colonna calcolata tramite la barra della formula DAX in Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="c01d5-107">This topic describes how to create a new calculated column by using the DAX formula bar in the model designer.</span></span>  
  
#### <a name="to-create-a-new-calculated-column"></a><span data-ttu-id="c01d5-108">Per creare una nuova colonna calcolata</span><span class="sxs-lookup"><span data-stu-id="c01d5-108">To create a new calculated column</span></span>  
  
1.  <span data-ttu-id="c01d5-109">In Vista dati di Progettazione modelli selezionare la tabella a cui si desidera aggiungere una colonna calcolata, fare clic sul menu **Colonna** , quindi scegliere **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="c01d5-109">In the model designer, in Data View, select the table to which you want to add a calculated column, then click the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="c01d5-110">L'opzione**Aggiungi colonna** viene evidenziata nella colonna vuota più a destra e il cursore si sposta nella barra della formula.</span><span class="sxs-lookup"><span data-stu-id="c01d5-110">**Add Column** is highlighted over the empty rightmost column, and the cursor moves to the formula bar.</span></span>  
  
     <span data-ttu-id="c01d5-111">Per creare una nuova colonna tra due colonne esistenti, fare clic con il pulsante destro del mouse su una colonna esistente e quindi scegliere **Inserisci colonna**.</span><span class="sxs-lookup"><span data-stu-id="c01d5-111">To create a new column between two existing columns, right-click an existing column, and then click **Insert Column**.</span></span>  
  
2.  <span data-ttu-id="c01d5-112">Nella barra della formula effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c01d5-112">In the formula bar, do one of the following:</span></span>  
  
    -   <span data-ttu-id="c01d5-113">Digitare un segno di uguale seguito da una formula.</span><span class="sxs-lookup"><span data-stu-id="c01d5-113">Type an equal sign followed by a formula.</span></span>  
  
    -   <span data-ttu-id="c01d5-114">Digitare un segno di uguale, seguito da una funzione DAX e dagli argomenti e dai parametri come richiesto dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="c01d5-114">Type an equal sign, followed by a DAX function, followed by arguments and parameters as required by the function.</span></span>  
  
    -   <span data-ttu-id="c01d5-115">Fare clic sul pulsante della funzione (**fx**) e quindi nella finestra di dialogo **Inserisci funzione** selezionare una categoria e una funzione e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c01d5-115">Click the function button (**fx**), then in the **Insert Function** dialog box, select a category and function, and then click **OK**.</span></span> <span data-ttu-id="c01d5-116">Nella barra della formula digitare gli argomenti e i parametri restanti come richiesto dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="c01d5-116">In the formula bar, type the remaining arguments and parameters as required by the function.</span></span>  
  
3.  <span data-ttu-id="c01d5-117">Premere INVIO per accettare la formula.</span><span class="sxs-lookup"><span data-stu-id="c01d5-117">Press ENTER to accept the formula.</span></span>  
  
     <span data-ttu-id="c01d5-118">L'intera colonna viene popolata con la formula e viene calcolato un valore per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="c01d5-118">The entire column is populated with the formula, and a value is calculated for each row.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="c01d5-119">È possibile utilizzare Completamento automatico formule DAX in una formula esistente con funzioni nidificate.</span><span class="sxs-lookup"><span data-stu-id="c01d5-119">You can use DAX Formula AutoComplete in the middle of an existing formula with nested functions.</span></span> <span data-ttu-id="c01d5-120">Il testo immediatamente prima del punto di inserimento viene utilizzato per visualizzare i valori nell'elenco a discesa mentre tutto il testo dopo tale punto rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="c01d5-120">The text immediately before the insertion point is used to display values in the drop-down list, and all of the text after the insertion point remains unchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c01d5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c01d5-121">See Also</span></span>  
 <span data-ttu-id="c01d5-122">[Colonne calcolate &#40;SSAS tabulare&#41;](ssas-calculated-columns.md) </span><span class="sxs-lookup"><span data-stu-id="c01d5-122">[Calculated Columns &#40;SSAS Tabular&#41;](ssas-calculated-columns.md) </span></span>  
 [<span data-ttu-id="c01d5-123">Misure &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="c01d5-123">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
