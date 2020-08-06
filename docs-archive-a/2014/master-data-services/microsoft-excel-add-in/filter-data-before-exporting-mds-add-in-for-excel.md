---
title: Filtrare i dati prima del caricamento (Componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9e30eae0-776b-4a09-aac3-0c0249d92ca5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6d0ccf667f37763326e27dcd8d0cfc005627ebc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715480"
---
# <a name="filter-data-before-loading-mds-add-in-for-excel"></a><span data-ttu-id="a8925-102">Filtrare i dati prima del caricamento (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="a8925-102">Filter Data before Loading (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="a8925-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] filtrare i dati quando si desidera limitare la dimensione o l'ambito dei dati da caricare in Excel.</span><span class="sxs-lookup"><span data-stu-id="a8925-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], filter data when you want to limit the size or scope of data that you are loading into Excel.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8925-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a8925-104">Prerequisites</span></span>  
 <span data-ttu-id="a8925-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="a8925-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a8925-106">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="a8925-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-filter-data-before-loading"></a><span data-ttu-id="a8925-107">Per filtrare i dati prima del caricamento</span><span class="sxs-lookup"><span data-stu-id="a8925-107">To filter data before loading</span></span>  
  
1.  <span data-ttu-id="a8925-108">Aprire Excel e nella scheda **Dati master** connettersi a un repository MDS.</span><span class="sxs-lookup"><span data-stu-id="a8925-108">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="a8925-109">Per altre informazioni, vedere [Connettersi a un repository MDS &#40;componente aggiuntivo MDS per Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="a8925-109">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="a8925-110">Nel riquadro **Esplora dati master** selezionare un modello e una versione.</span><span class="sxs-lookup"><span data-stu-id="a8925-110">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="a8925-111">L'elenco di entità viene popolato.</span><span class="sxs-lookup"><span data-stu-id="a8925-111">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="a8925-112">Se il riquadro **Esplora dati master** non è visibile, nel gruppo **Connetti e carica** fare clic su **Esplora dati master**.</span><span class="sxs-lookup"><span data-stu-id="a8925-112">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="a8925-113">Se il riquadro **Esplora dati master** è disabilitato, significa che il foglio esistente contiene già i dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="a8925-113">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="a8925-114">Per abilitare il riquadro, aprire un nuovo foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a8925-114">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="a8925-115">Nel riquadro **Esplora dati master** , nell'elenco di entità fare clic sull'entità che si desidera filtrare.</span><span class="sxs-lookup"><span data-stu-id="a8925-115">In the **Master Data Explorer** pane, in the list of entities, click the entity you want to filter.</span></span>  
  
4.  <span data-ttu-id="a8925-116">Sulla barra multifunzione, nel gruppo **Connetti e carica** fare clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="a8925-116">On the ribbon, in the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="a8925-117">Completare la finestra di dialogo **Filtro** selezionando gli attributi (colonne) da visualizzare, impostando l'ordine delle colonne e se necessario, filtrando i dati in modo che vengano restituite meno righe.</span><span class="sxs-lookup"><span data-stu-id="a8925-117">Complete the **Filter** dialog box by selecting the attributes (columns) to display, setting the order of the columns, and if needed, filtering the data so fewer rows are returned.</span></span> <span data-ttu-id="a8925-118">Visualizzare il riquadro **Riepilogo** per sapere quanti dati saranno restituiti.</span><span class="sxs-lookup"><span data-stu-id="a8925-118">View the **Summary** pane for how much data will be returned.</span></span> <span data-ttu-id="a8925-119">Per altre informazioni, vedere [Finestra di dialogo Filtro &#40;componente aggiuntivo MDS per Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="a8925-119">For more information, see [Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).</span></span>  
  
6.  <span data-ttu-id="a8925-120">Fare clic su **Carica dati**.</span><span class="sxs-lookup"><span data-stu-id="a8925-120">Click **Load Data**.</span></span> <span data-ttu-id="a8925-121">Il foglio viene popolato con i dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="a8925-121">The sheet is populated with MDS-managed data.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="a8925-122">Solo il primo milione di membri viene caricato in Excel.</span><span class="sxs-lookup"><span data-stu-id="a8925-122">Only the first one million members are loaded into Excel.</span></span>  
    > -   <span data-ttu-id="a8925-123">Nelle colonne che sono elenchi vincolati (attributi basati su dominio) vengono caricati solo i primi 1000 valori.</span><span class="sxs-lookup"><span data-stu-id="a8925-123">In columns that are constrained lists (domain-based attributes), only the first 1000 values are loaded.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a8925-124">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a8925-124">Next Steps</span></span>  
 [<span data-ttu-id="a8925-125">Pubblicare dati da Excel a MDS &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a8925-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="a8925-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8925-126">See Also</span></span>  
 <span data-ttu-id="a8925-127">[Caricamento dei dati &#40;Componente aggiuntivo MDS per Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="a8925-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="a8925-128">[Finestra di dialogo filtro &#40;Componente aggiuntivo MDS per Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="a8925-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="a8925-129">Riordinare le colonne &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a8925-129">Reorder Columns &#40;MDS Add-in for Excel&#41;</span></span>](reorder-columns-mds-add-in-for-excel.md)  
  
  
