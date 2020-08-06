---
title: Aggiungere nuove righe nel riquadro Risultati (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- inserting rows
- Query Designer [SQL Server], Results pane
- Results pane
- adding rows
- row additions [SQL Server], Results pane
ms.assetid: 59891c84-3f54-4ab9-8b86-72c59627b480
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3137da106279e09305261c6c7cb7fd06d254b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626469"
---
# <a name="add-new-rows-in-the-results-pane-visual-database-tools"></a><span data-ttu-id="b443e-102">Aggiunta di nuove righe nel riquadro Risultati (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b443e-102">Add New Rows in the Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="b443e-103">Per aggiungere nuovi dati, è possibile digitarli o incollarli da un altro programma, ad esempio il Blocco note o Excel.</span><span class="sxs-lookup"><span data-stu-id="b443e-103">You can add new data either by typing it in or by pasting it from another program such as Notepad or Excel.</span></span> <span data-ttu-id="b443e-104">Per incollare una riga è necessario che presenti esattamente lo stesso numero e tipo di colonne della tabella in cui la si desidera incollare.</span><span class="sxs-lookup"><span data-stu-id="b443e-104">A row to be pasted must have exactly the same number and types of columns as the table into which you are pasting.</span></span> <span data-ttu-id="b443e-105">È possibile incollare nel riquadro Risultati più righe contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b443e-105">You can paste multiple rows into the Results pane at once.</span></span>  
  
 <span data-ttu-id="b443e-106">Per informazioni su come immettere dati, vedere [Regole per l'aggiornamento dei risultati & #40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b443e-106">For information about how to enter data see [Rules for Updating Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-add-a-new-data-row"></a><span data-ttu-id="b443e-107">Per aggiungere una nuova riga di dati</span><span class="sxs-lookup"><span data-stu-id="b443e-107">To add a new data row</span></span>  
  
1.  <span data-ttu-id="b443e-108">Spostarsi nella parte inferiore del riquadro Risultati, dove è disponibile una riga vuota per l'aggiunta di una nuova riga di dati.</span><span class="sxs-lookup"><span data-stu-id="b443e-108">Navigate to the bottom of the Results pane, where a blank row is available for adding a new data row.</span></span>  
  
     <span data-ttu-id="b443e-109">I valori iniziali per tutte le colonne saranno di tipo *NULL*.</span><span class="sxs-lookup"><span data-stu-id="b443e-109">The initial values for all columns will be *NULL*.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="b443e-110">Per spostarsi direttamente sulla prima riga vuota, utilizzare la barra di navigazione nella parte inferiore del riquadro Risultati.</span><span class="sxs-lookup"><span data-stu-id="b443e-110">To go directly to the first empty row use the navigation bar at the bottom of the Results pane.</span></span>  
  
2.  <span data-ttu-id="b443e-111">Se si incollano righe dagli Appunti, selezionare la nuova riga facendo clic sul pulsante alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="b443e-111">If you are pasting rows from the Clipboard, select the new row by clicking the button to its left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b443e-112">Qualora non sia possibile eseguire il commit nel database di una o più righe incollate, verrà visualizzato un messaggio che indicherà quali sono le righe di cui non è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="b443e-112">If one or more of the rows you're pasting can't be committed to the database you will receive a message telling you which row(s) couldn't be committed.</span></span>  
  
3.  <span data-ttu-id="b443e-113">Immettere i dati per la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="b443e-113">Enter the data for the new row.</span></span> <span data-ttu-id="b443e-114">Se si incollano i dati, scegliere **Incolla** dal menu **Modifica** .</span><span class="sxs-lookup"><span data-stu-id="b443e-114">If you are pasting, choose **Paste** from the **Edit** menu.</span></span>  
  
4.  <span data-ttu-id="b443e-115">Uscire dalla riga in modo che ne venga eseguito il commit nel database.</span><span class="sxs-lookup"><span data-stu-id="b443e-115">Leave that row to commit it to the database.</span></span>  
  
 <span data-ttu-id="b443e-116">Se si verifica un errore quando si salva la riga, in Progettazione query e Progettazione viste verrà visualizzato un messaggio e l'utente verrà posizionato nuovamente sulla riga che stava modificando.</span><span class="sxs-lookup"><span data-stu-id="b443e-116">If an error occurs when you save the row the Query and View Designer displays a message and then returns you to the row you were editing.</span></span> <span data-ttu-id="b443e-117">Sarà quindi possibile:</span><span class="sxs-lookup"><span data-stu-id="b443e-117">You can then:</span></span>  
  
-   <span data-ttu-id="b443e-118">Risolvere l'errore apportando ulteriori modifiche alla riga.</span><span class="sxs-lookup"><span data-stu-id="b443e-118">Resolve the error by making further edits in the row.</span></span>  
  
-   <span data-ttu-id="b443e-119">Annullare la modifica premendo ESC.</span><span class="sxs-lookup"><span data-stu-id="b443e-119">Cancel the edit by pressing ESC.</span></span> <span data-ttu-id="b443e-120">Se si preme ESC mentre si è posizionati in una cella cui sono state apportate modifiche, tali modifiche verranno annullate.</span><span class="sxs-lookup"><span data-stu-id="b443e-120">If you press ESC while in a cell that you changed, the changes for that cell are canceled.</span></span> <span data-ttu-id="b443e-121">Se si preme ESC mentre si è posizionati in una cella cui non è stata apportata alcuna modifica, verranno annullate le modifiche apportate all'intera riga.</span><span class="sxs-lookup"><span data-stu-id="b443e-121">If you press ESC while in a cell you have not changed, the changes for the entire row are canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b443e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b443e-122">See Also</span></span>  
 <span data-ttu-id="b443e-123">[Utilizzare i dati nel riquadro risultati &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b443e-123">[Work with Data in the Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b443e-124">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b443e-124">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
