---
title: Aggirare la limitazione delle righe di Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a4c8700b-bef5-4440-a99c-bba5dcc46bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128f65cf09833d23234da10bf7744c6ce30065ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626018"
---
# <a name="work-around-the-excel-row-limitation"></a><span data-ttu-id="01708-102">Soluzione alternativa per il limite di righe in Excel</span><span class="sxs-lookup"><span data-stu-id="01708-102">Work Around the Excel Row Limitation</span></span>
  <span data-ttu-id="01708-103">In questo argomento viene illustrato come risolvere il limite di righe di Excel 2003 quando si esportano i report in Excel.</span><span class="sxs-lookup"><span data-stu-id="01708-103">This topic explains how to work around the Excel 2003 row limitation when you export reports to Excel.</span></span> <span data-ttu-id="01708-104">La soluzione alternativa consiste in un report contenente una sola tabella.</span><span class="sxs-lookup"><span data-stu-id="01708-104">The workaround is for a report that contains only a table.</span></span>  
  
 <span data-ttu-id="01708-105">Excel 2003 supporta un massimo di 65.536 righe per foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="01708-105">Excel 2003 supports a maximum of 65,536 rows per worksheet.</span></span> <span data-ttu-id="01708-106">È possibile risolvere questo limite forzando un'interruzione di pagina esplicita dopo un determinato numero di righe.</span><span class="sxs-lookup"><span data-stu-id="01708-106">You can work around this limitation by forcing an explicit page break after a certain number of rows.</span></span> <span data-ttu-id="01708-107">Tramite il renderer Excel viene creato un nuovo foglio di lavoro per ogni interruzione di pagina esplicita.</span><span class="sxs-lookup"><span data-stu-id="01708-107">The Excel renderer creates a new worksheet for each explicit page break.</span></span>  
  
### <a name="to-create-an-explicit-page-break"></a><span data-ttu-id="01708-108">Per creare un'interruzione di pagina esplicita</span><span class="sxs-lookup"><span data-stu-id="01708-108">To create an explicit page break</span></span>  
  
1.  <span data-ttu-id="01708-109">Aprire il report in [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] o Gestione report.</span><span class="sxs-lookup"><span data-stu-id="01708-109">Open the report in [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] or Report Manager.</span></span>  
  
2.  <span data-ttu-id="01708-110">Fare clic con il pulsante destro del mouse sulla riga di dati nella tabella e quindi scegliere **Aggiungi**gruppo  >  **padre** gruppo per aggiungere un gruppo di tabelle esterno.</span><span class="sxs-lookup"><span data-stu-id="01708-110">Right click the Data row in the table, and then click **Add Group** > **Parent Group** to add an outer table group.</span></span>  
  
     <span data-ttu-id="01708-111">![Selezionare il gruppo padre](../media/datarow-selectparentgroup.png "Selezionare il gruppo padre")</span><span class="sxs-lookup"><span data-stu-id="01708-111">![Select the Parent Group](../media/datarow-selectparentgroup.png "Select the Parent Group")</span></span>  
  
3.  <span data-ttu-id="01708-112">Immettere la formula seguente nella casella dell'espressione **Raggruppa per** , quindi fare clic su **OK** per aggiungere il gruppo padre.</span><span class="sxs-lookup"><span data-stu-id="01708-112">Enter the following formula in the **Group by** expression box, and then click **OK** to add the parent group.</span></span>  
  
     <span data-ttu-id="01708-113">=Int((RowNumber(Nothing)-1)/65000)</span><span class="sxs-lookup"><span data-stu-id="01708-113">=Int((RowNumber(Nothing)-1)/65000)</span></span>  
  
     <span data-ttu-id="01708-114">La formula assegna un numero a ogni set di 65000 righe nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="01708-114">The formula assigns a number to each set of 65000 rows in the dataset.</span></span> <span data-ttu-id="01708-115">Se si definisce un'interruzione di pagina per il gruppo, si ottiene un'interruzione di pagina ogni 65000 righe.</span><span class="sxs-lookup"><span data-stu-id="01708-115">When a page break is defined for the group, the expression results in a page break every 65000 rows.</span></span>  
  
     <span data-ttu-id="01708-116">Con l'aggiunta del gruppo di tabelle esterno viene aggiunta una colonna di gruppo al report.</span><span class="sxs-lookup"><span data-stu-id="01708-116">Adding the outer table group adds a group column to the report.</span></span>  
  
4.  <span data-ttu-id="01708-117">Per eliminare la colonna di gruppo, fare clic con il pulsante destro del mouse sull'intestazione di colonna, fare clic su **Elimina colonne**, selezionare **Elimina solo colonne**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="01708-117">Delete the group column by right-clicking on the column header, clicking **Delete Columns**, selecting **Delete columns only**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="01708-118">![Eliminare una colonna di gruppo](../media/groupcolumn-delete-updated.png "Eliminare una colonna di gruppo")</span><span class="sxs-lookup"><span data-stu-id="01708-118">![Delete a group column](../media/groupcolumn-delete-updated.png "Delete a group column")</span></span>  
  
5.  <span data-ttu-id="01708-119">Fare clic con il pulsante destro del mouse su **Gruppo 1** nella sezione **Gruppi di righe** , quindi scegliere **Proprietà gruppo**.</span><span class="sxs-lookup"><span data-stu-id="01708-119">Right click **Group 1** in the **Row Groups** section, and then click **Group Properties**.</span></span>  
  
     <span data-ttu-id="01708-120">![Visualizzare le proprietà del gruppo](../media/groupproperties-updated.png "Visualizzare le proprietà del gruppo")</span><span class="sxs-lookup"><span data-stu-id="01708-120">![View group properties](../media/groupproperties-updated.png "View group properties")</span></span>  
  
6.  <span data-ttu-id="01708-121">Nella pagina **Ordinamento** della finestra di dialogo **Proprietà gruppo** selezionare l'opzione di ordinamento predefinita e fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="01708-121">On the **Sorting** page of the **Group Properties** dialog box, select the default sorting option and click **Delete**.</span></span>  
  
     <span data-ttu-id="01708-122">![Eliminare l'ordinamento predefinito](../media/groupproperties-sorting-updated.png "Eliminare l'ordinamento predefinito")</span><span class="sxs-lookup"><span data-stu-id="01708-122">![Delete default sorting](../media/groupproperties-sorting-updated.png "Delete default sorting")</span></span>  
  
7.  <span data-ttu-id="01708-123">Nella pagina **Interruzioni di pagina** fare clic su **Tra ogni istanza di un gruppo** , quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="01708-123">On the **Page Breaks** page, click **Between each instance of a group** and then click **OK**.</span></span>  
  
     <span data-ttu-id="01708-124">![Impostare le interruzioni di pagina](../media/groupproperties-pagebreaks-updated.png "Impostare le interruzioni di pagina")</span><span class="sxs-lookup"><span data-stu-id="01708-124">![Set page breaks](../media/groupproperties-pagebreaks-updated.png "Set page breaks")</span></span>  
  
8.  <span data-ttu-id="01708-125">Salvare il report.</span><span class="sxs-lookup"><span data-stu-id="01708-125">Save the report.</span></span> <span data-ttu-id="01708-126">Quando lo si esporta in Excel, viene esportato in più fogli di lavoro, ognuno con un massimo di 65000 righe.</span><span class="sxs-lookup"><span data-stu-id="01708-126">When you export it to Excel, it exports to multiple worksheets and each worksheet contains a maximum of 65000 rows.</span></span>  
  
  
