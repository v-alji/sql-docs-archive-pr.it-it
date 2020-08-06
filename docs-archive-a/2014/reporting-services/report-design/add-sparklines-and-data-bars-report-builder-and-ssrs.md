---
title: Aggiunta di grafici sparkline e barre dei dati (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0b297c2e-d48b-41b0-aabd-29680cdcdb05
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55ec15354cdc78dd9678b9466f30d2fca0a73adc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625159"
---
# <a name="add-sparklines-and-data-bars-report-builder-and-ssrs"></a><span data-ttu-id="a60d0-102">Aggiunta di grafici sparkline e barre dei dati (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a60d0-102">Add Sparklines and Data Bars (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a60d0-103">I grafici sparkline e le barre dei dati sono grafici di riserva di piccole dimensioni contenenti numerose informazioni poco dettagliate.</span><span class="sxs-lookup"><span data-stu-id="a60d0-103">Sparklines and data bars are small, spare charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="a60d0-104">Per altre informazioni, vedere [Grafici sparkline e barre dei dati &#40;Generatore report e SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a60d0-104">For more information about them, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="a60d0-105">I grafici sparkline e le barre dei dati vengono posizionati generalmente nelle celle di una tabella o di una matrice.</span><span class="sxs-lookup"><span data-stu-id="a60d0-105">Sparklines and data bars are most commonly placed in cells in a table or matrix.</span></span> <span data-ttu-id="a60d0-106">In ogni grafico sparkline di solito viene visualizzata una sola serie.</span><span class="sxs-lookup"><span data-stu-id="a60d0-106">Sparklines usually display only one series each.</span></span> <span data-ttu-id="a60d0-107">Le barre dei dati possono includere più punti dati.</span><span class="sxs-lookup"><span data-stu-id="a60d0-107">Data bars can contain one or more data points.</span></span> <span data-ttu-id="a60d0-108">L'influenza dei grafici sparkline e delle barre dei dati deriva dal ripetersi delle informazioni relative alla serie per ogni riga della tabella o matrice.</span><span class="sxs-lookup"><span data-stu-id="a60d0-108">Both sparklines and data bars derive their impact from repeating the series information for each row in the table or matrix.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-sparkline-or-data-bar-to-a-table-or-matrix"></a><span data-ttu-id="a60d0-109">Per aggiungere grafici sparkline o barre dei dati a una tabella o a una matrice</span><span class="sxs-lookup"><span data-stu-id="a60d0-109">To add a sparkline or data bar to a table or matrix</span></span>  
  
1.  <span data-ttu-id="a60d0-110">Se questa operazione non è già stata eseguita, creare una tabella o una matrice con i dati che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="a60d0-110">If you have not done so already, create a table or matrix with the data you want to display.</span></span> <span data-ttu-id="a60d0-111">Per altre informazioni, vedere [Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) o [Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a60d0-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="a60d0-112">Inserire una colonna nella tabella o nella matrice.</span><span class="sxs-lookup"><span data-stu-id="a60d0-112">Insert a column in your table or matrix.</span></span> <span data-ttu-id="a60d0-113">Per altre informazioni, vedere [Inserire o eliminare una colonna &#40;Generatore report e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a60d0-113">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="a60d0-114">Scegliere **Grafico sparkline** o **Barra dei dati** nella scheda **Inserisci**e fare clic in una cella della nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="a60d0-114">On the **Insert** tab, click **Sparkline** or **Data Bar**, and then click in a cell in the new column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a60d0-115">Non è possibile posizionare grafici sparkline in un gruppo di dettagli in una tabella.</span><span class="sxs-lookup"><span data-stu-id="a60d0-115">You cannot place sparklines in a detail group in a table.</span></span> <span data-ttu-id="a60d0-116">Devono essere inseriti in una cella associata a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="a60d0-116">They must go in a cell associated with a group.</span></span>  
  
4.  <span data-ttu-id="a60d0-117">Nella finestra di dialogo **Modifica tipo di grafico sparkline/barra dei dati** fare clic sul tipo di grafico sparkline o barra dei dati desiderato e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="a60d0-117">In the **Change Sparkline/Data Bar Type** dialog box, click the kind of sparkline or data bar you want, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="a60d0-118">Scegliere il grafico sparkline o la barra dei dati.</span><span class="sxs-lookup"><span data-stu-id="a60d0-118">Click the sparkline or data bar.</span></span>  
  
     <span data-ttu-id="a60d0-119">Viene visualizzato il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="a60d0-119">The **Chart Data** pane opens.</span></span>  
  
6.  <span data-ttu-id="a60d0-120">Nell'area **Valori** fare clic sul segno più ( **) di** Aggiungi campi**+** e selezionare il campo contenente i valori che si vuole inserire in formato grafico.</span><span class="sxs-lookup"><span data-stu-id="a60d0-120">In the **Values** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want charted.</span></span>  
  
7.  <span data-ttu-id="a60d0-121">Nell'area **Gruppi di categorie** fare clic sul segno più ( **) di** Aggiungi campi**+** e selezionare il campo contenente i valori in base ai quali si vuole raggruppare.</span><span class="sxs-lookup"><span data-stu-id="a60d0-121">In the **Category Groups** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want to group by.</span></span>  
  
     <span data-ttu-id="a60d0-122">In genere per i grafici sparkline e per le barre dei dati, non viene aggiunto un campo all'area **Gruppo serie** in quanto si desidera una sola serie per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="a60d0-122">Typically for sparklines and data bars, you will not add a field to the **Series Group** area because you only want one series for each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a60d0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a60d0-123">See Also</span></span>  
 <span data-ttu-id="a60d0-124">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a60d0-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a60d0-125">Allineare i dati in un grafico di una tabella o matrice &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a60d0-125">Align the Data in a Chart in a Table or Matrix &#40;Report Builder and SSRS&#41;</span></span>](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
  
