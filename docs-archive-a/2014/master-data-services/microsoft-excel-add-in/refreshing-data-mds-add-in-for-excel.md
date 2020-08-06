---
title: Aggiornamento dei dati (Componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 58dbe99a-288d-4f1c-9cd5-704d6836c945
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 49b6e7bc19c41911c626965b9d1de132796367f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724792"
---
# <a name="refreshing-data-mds-add-in-for-excel"></a><span data-ttu-id="0dbda-102">Aggiornamento dei dati (Componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="0dbda-102">Refreshing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="0dbda-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]aggiornare i dati quando si vuole ottenere le ultime informazioni dal repository MDS senza aprire un nuovo foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0dbda-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], refresh data when you want to get the latest information from the MDS repository without opening a new worksheet.</span></span> <span data-ttu-id="0dbda-104">È possibile aggiornare tutte le celle o una selezione di celle.</span><span class="sxs-lookup"><span data-stu-id="0dbda-104">You can refresh either all cells or a selection of cells.</span></span> <span data-ttu-id="0dbda-105">Questo può essere utile quando sono state inserite colonne con formule personalizzate o altri dati che non sono gestiti in MDS e che si desidera mantenere.</span><span class="sxs-lookup"><span data-stu-id="0dbda-105">This can be useful when you have inserted columns with custom formulas or other data that is not managed in MDS and you want to preserve it.</span></span>  
  
## <a name="when-you-can-refresh-mds-managed-data"></a><span data-ttu-id="0dbda-106">Quando è possibile aggiornare i dati gestiti da MDS</span><span class="sxs-lookup"><span data-stu-id="0dbda-106">When You Can Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="0dbda-107">È possibile aggiornare i dati gestiti da MDS in un foglio di lavoro attivo se il foglio di lavoro attivo già contiene i dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="0dbda-107">You can refresh MDS-managed data in an active worksheet if the active worksheet already contains MDS-managed data.</span></span> <span data-ttu-id="0dbda-108">Se sono stati modificati valori di attributo o aggiunti membri al foglio di lavoro, è necessario pubblicare le modifiche prima di eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0dbda-108">If you have changed attribute values or added members to the worksheet, you must publish your changes before you can refresh.</span></span>  
  
## <a name="refreshing-a-selection"></a><span data-ttu-id="0dbda-109">Aggiornamento di una selezione</span><span class="sxs-lookup"><span data-stu-id="0dbda-109">Refreshing a Selection</span></span>  
 <span data-ttu-id="0dbda-110">È possibile aggiornare tutte le celle o solo le celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="0dbda-110">You have the choice of refreshing all cells or refreshing only selected cells.</span></span> <span data-ttu-id="0dbda-111">Le celle selezionate devono essere contigue.</span><span class="sxs-lookup"><span data-stu-id="0dbda-111">The selected cells must be contiguous.</span></span> <span data-ttu-id="0dbda-112">Se viene selezionato un set di celle contigue, tutte le celle gestite da MDS nel set verranno aggiornate per visualizzare i valori attualmente archiviati nel server.</span><span class="sxs-lookup"><span data-stu-id="0dbda-112">If a set of contiguous cells is selected, all MDS managed cells in that set will be updated to display the values currently stored on the server.</span></span> <span data-ttu-id="0dbda-113">L'operazione non ha alcun effetto su righe e colonne non modificate che non sono gestite da MDS.</span><span class="sxs-lookup"><span data-stu-id="0dbda-113">Unchanged rows and columns that are not managed by MDS are not affected in any way.</span></span>  
  
## <a name="what-happens-when-you-refresh-mds-managed-data"></a><span data-ttu-id="0dbda-114">Cosa accade quando si aggiornano i dati gestiti da MDS</span><span class="sxs-lookup"><span data-stu-id="0dbda-114">What Happens When You Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="0dbda-115">Quando si aggiornano dati in [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], ciò che accade ai dati gestiti da MDS nel foglio dipende da quale modifica è stata apportata nel repository MDS dall'ultimo caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="0dbda-115">When you refresh data in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], what happens to the MDS-managed data in the sheet depends on what has changed in the MDS repository since you last loaded the data.</span></span>  
  
-   <span data-ttu-id="0dbda-116">Se i nuovi membri sono stati aggiunti al repository, vengono aggiunti alla fine del foglio di lavoro e sono evidenziati in verde.</span><span class="sxs-lookup"><span data-stu-id="0dbda-116">If new members have been added to repository, they are added to the end of the worksheet and are highlighted in green.</span></span>  
  
-   <span data-ttu-id="0dbda-117">Se i membri sono eliminati dal repository, vengono eliminati dal foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0dbda-117">If members were deleted from the repository, they are deleted from the worksheet.</span></span>  
  
-   <span data-ttu-id="0dbda-118">Se un valore dell'attributo è stato modificato nel repository MDS, il valore nel foglio di lavoro viene aggiornato con il valore presente nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="0dbda-118">If an attribute value has changed in the MDS repository, the value in the worksheet is updated with value from the MDS repository.</span></span> <span data-ttu-id="0dbda-119">Il colore della cella non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="0dbda-119">The cell color does not change.</span></span>  
  
> [!WARNING]
>  -   <span data-ttu-id="0dbda-120">Nel foglio di lavoro attivo, se esistono dati non gestiti nelle righe al di sotto dei dati gestiti da MDS, è possibile che i dati non gestiti vengano sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="0dbda-120">In the active worksheet, if non-managed data exists in rows beneath the MDS-managed data, the non-managed data may be overwritten.</span></span> <span data-ttu-id="0dbda-121">Ciò si verifica quando si aggiorna il foglio e vengono aggiunte nuove righe dei dati gestiti da MDS, che si sovrappongono ai dati non gestiti.</span><span class="sxs-lookup"><span data-stu-id="0dbda-121">This occurs when you refresh the sheet and new rows of MDS-managed data, which overlap with the non-managed data, are added.</span></span>  
> -   <span data-ttu-id="0dbda-122">Quando si effettua l'aggiornamento, vengono eliminati i commenti sulle celle gestite da MDS.</span><span class="sxs-lookup"><span data-stu-id="0dbda-122">When you refresh, comments on MDS-managed cells are deleted.</span></span>  
  
## <a name="how-to-refresh-mds-managed-data"></a><span data-ttu-id="0dbda-123">Come aggiornare i dati gestiti da MDS</span><span class="sxs-lookup"><span data-stu-id="0dbda-123">How to Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="0dbda-124">Nel gruppo **Connetti e carica** sulla barra multifunzione il pulsante **Aggiorna** ha due opzioni **Aggiorna tutto** e **Aggiorna selezione**.</span><span class="sxs-lookup"><span data-stu-id="0dbda-124">In the **Connect and Load** group on the ribbon, the **Refresh** button has two options, **Refresh All** and **Refresh Selection**.</span></span> <span data-ttu-id="0dbda-125">L'azione predefinita del pulsante della barra multifunzione è **Aggiorna tutto**.</span><span class="sxs-lookup"><span data-stu-id="0dbda-125">The default action of the ribbon button is **Refresh All**.</span></span> <span data-ttu-id="0dbda-126">Per aggiornare l'intero foglio con i valori dal server, fare clic sul pulsante **Aggiorna** o scegliere l'opzione **Aggiorna tutto** .</span><span class="sxs-lookup"><span data-stu-id="0dbda-126">To refresh the entire sheet with values from the server, click the **Refresh** button or choose the **Refresh All** option.</span></span> <span data-ttu-id="0dbda-127">Per aggiornare solo alcune delle celle in un foglio, selezionare le celle eseguendo una selezione contigua e scegliere l'opzione **Aggiorna selezione** .</span><span class="sxs-lookup"><span data-stu-id="0dbda-127">To refresh only some of the cells in a sheet, select the cells (must be one contiguous selection) and choose the **Refresh Selection** option.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0dbda-128">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0dbda-128">Related Tasks</span></span>  
  
|<span data-ttu-id="0dbda-129">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="0dbda-129">Task Description</span></span>|<span data-ttu-id="0dbda-130">Argomento</span><span class="sxs-lookup"><span data-stu-id="0dbda-130">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="0dbda-131">Creare una connessione a un database [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0dbda-131">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="0dbda-132">Connettersi a un repository MDS &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0dbda-132">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="0dbda-133">Caricare dati MDS in Excel.</span><span class="sxs-lookup"><span data-stu-id="0dbda-133">Load MDS data into Excel.</span></span>|[<span data-ttu-id="0dbda-134">Caricare i dati da MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="0dbda-134">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="0dbda-135">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="0dbda-135">Related Content</span></span>  
  
-   [<span data-ttu-id="0dbda-136">Connessioni &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0dbda-136">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="0dbda-137">Caricamento dei dati &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0dbda-137">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="0dbda-138">Componente aggiuntivo Master Data Services per Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="0dbda-138">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
