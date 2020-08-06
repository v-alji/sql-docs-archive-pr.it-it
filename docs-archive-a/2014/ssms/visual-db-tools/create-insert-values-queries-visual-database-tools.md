---
title: Creare query di accodamento valori (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting values
- queries [SQL Server], types
- adding values
- row additions [SQL Server], Insert Values query
- inserting rows
- Insert Values query
- adding rows
- table values [SQL Server]
ms.assetid: 2d4b2f6d-cc09-434b-8a0e-ccce40628064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fc71b0148ee8a7e92c517fe75b56c329b3c88f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714963"
---
# <a name="create-insert-values-queries-visual-database-tools"></a><span data-ttu-id="4d385-102">Creazione di query di accodamento valori (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4d385-102">Create Insert Values Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="4d385-103">Per creare una nuova riga nella tabella corrente, è possibile utilizzare una query di accodamento valori.</span><span class="sxs-lookup"><span data-stu-id="4d385-103">You can create a new row in the current table using an Insert Values query.</span></span> <span data-ttu-id="4d385-104">Durante la creazione di una query di accodamento valori è necessario specificare:</span><span class="sxs-lookup"><span data-stu-id="4d385-104">When you create an Insert Values query, you specify:</span></span>  
  
-   <span data-ttu-id="4d385-105">la tabella di database a cui aggiungere la riga</span><span class="sxs-lookup"><span data-stu-id="4d385-105">The database table to add the row to.</span></span>  
  
-   <span data-ttu-id="4d385-106">le colonne di cui si desidera aggiungere il contenuto</span><span class="sxs-lookup"><span data-stu-id="4d385-106">The columns whose contents you want to add.</span></span>  
  
-   <span data-ttu-id="4d385-107">il valore o l'espressione da inserire nelle singole colonne.</span><span class="sxs-lookup"><span data-stu-id="4d385-107">The value or expression to insert into the individual columns.</span></span>  
  
 <span data-ttu-id="4d385-108">Ad esempio, la seguente query aggiunge una riga alla tabella `titles` , specificando i valori relativi al titolo, al tipo, all'editore e al prezzo:</span><span class="sxs-lookup"><span data-stu-id="4d385-108">For example, the following query adds a row to the `titles` table, specifying values for the title, type, publisher, and price:</span></span>  
  
```  
INSERT INTO titles  
         (title_id, title, type, pub_id, price)  
VALUES   ('BU9876', 'Creating Web Pages', 'business', '1389', '29.99')  
```  
  
 <span data-ttu-id="4d385-109">Quando si crea una query di accodamento valori, nel riquadro Criteri vengono visualizzate solo le opzioni disponibili per l'inserimento di una nuova riga, ovvero il nome della colonna e il valore da inserire.</span><span class="sxs-lookup"><span data-stu-id="4d385-109">When you create an Insert Values query, the Criteria pane changes to reflect the only options available for inserting a new row: the column name and the value to insert.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4d385-110">Una volta eseguita, la query di accodamento valori non potrà essere annullata.</span><span class="sxs-lookup"><span data-stu-id="4d385-110">You cannot undo the action of executing an Insert Values query.</span></span> <span data-ttu-id="4d385-111">È dunque opportuno eseguire una copia di backup dei dati prima di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="4d385-111">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-values-query"></a><span data-ttu-id="4d385-112">Per creare una query di accodamento valori</span><span class="sxs-lookup"><span data-stu-id="4d385-112">To create an Insert Values query</span></span>  
  
1.  <span data-ttu-id="4d385-113">Aggiungere al riquadro Diagramma la tabella da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="4d385-113">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="4d385-114">Scegliere **Modifica tipo** dal menu **Progettazione query**e **Accodamento valori**.</span><span class="sxs-lookup"><span data-stu-id="4d385-114">From the **Query Designer** menu point to **Change Type**, and then click **Insert Values**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d385-115">Se nel riquadro diagramma è visualizzata più di una tabella quando si avvia la query di accodamento valori, in Progettazione query e Progettazione viste verrà visualizzata la [finestra di dialogo Scegliere la tabella di destinazione per Accodamento valori](visual-database-tools.md) , in cui sarà possibile specificare il nome della tabella da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="4d385-115">If more than one table is displayed in the Diagram pane when you start the Insert Values query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="4d385-116">Nel riquadro Diagramma selezionare le caselle di controllo relative alle colonne per cui si desidera specificare nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="4d385-116">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="4d385-117">Queste colonne verranno visualizzate nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="4d385-117">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="4d385-118">Verranno aggiornate solo le colonne aggiunte alla query.</span><span class="sxs-lookup"><span data-stu-id="4d385-118">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="4d385-119">Nella colonna **Nuovo valore** del riquadro Criteri immettere il nuovo valore per la colonna.</span><span class="sxs-lookup"><span data-stu-id="4d385-119">In the **New Value** column of the Criteria pane, enter the new value for the column.</span></span> <span data-ttu-id="4d385-120">È possibile immettere valori letterali, nomi di colonna o espressioni.</span><span class="sxs-lookup"><span data-stu-id="4d385-120">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="4d385-121">Il valore deve corrispondere o essere compatibile con il tipo di dati della colonna da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="4d385-121">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="4d385-122">In Progettazione query e Progettazione viste non è possibile verificare la compatibilità di un valore rispetto alla lunghezza della colonna di inserimento.</span><span class="sxs-lookup"><span data-stu-id="4d385-122">The Query and View Designer cannot check that a value fits within the length of the column you are inserting.</span></span> <span data-ttu-id="4d385-123">Se il valore inserito è troppo lungo, è possibile che venga troncato senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="4d385-123">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="4d385-124">Ad esempio, se una colonna `name` è lunga 20 caratteri ma si specifica un valore di inserimento di 25 caratteri, è possibile che gli ultimi 5 caratteri vengano troncati.</span><span class="sxs-lookup"><span data-stu-id="4d385-124">For example, if a `name` column is 20 characters long but you specify an insert value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
 <span data-ttu-id="4d385-125">Quando si esegue una query di accodamento valori, non viene restituito alcun risultato nel [riquadro Risultati](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d385-125">When you execute an Insert Values query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="4d385-126">Viene invece visualizzato un messaggio che indica il numero di righe modificate.</span><span class="sxs-lookup"><span data-stu-id="4d385-126">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d385-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d385-127">See Also</span></span>  
 <span data-ttu-id="4d385-128">[Tipi di query supportati &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4d385-128">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="4d385-129">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4d385-129">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4d385-130">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4d385-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
