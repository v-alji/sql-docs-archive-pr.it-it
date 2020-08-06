---
title: Caricare i dati da MDS in Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: dd29389b-928c-4e50-995c-c6af27f97805
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 35672807d5bb108e9386f892aea1847d45ebeb33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715483"
---
# <a name="load-data-from-mds-into-excel"></a><span data-ttu-id="0d6b6-102">Caricare i dati da MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="0d6b6-102">Load Data from MDS into Excel</span></span>
  <span data-ttu-id="0d6b6-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] è necessario caricare i dati dal repository MDS per utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must load data from the MDS repository in order to work with it.</span></span>  
  
 <span data-ttu-id="0d6b6-104">Se si desidera filtrare il set di dati prima del caricamento, vedere [filtrare i dati prima di caricare &#40;Componente aggiuntivo MDS per Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) .</span><span class="sxs-lookup"><span data-stu-id="0d6b6-104">If you want to filter the dataset before loading, see [Filter Data before Loading &#40;MDS Add-in for Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) instead.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0d6b6-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0d6b6-105">Prerequisites</span></span>  
 <span data-ttu-id="0d6b6-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="0d6b6-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0d6b6-107">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="0d6b6-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-load-data-from-mds-into-excel"></a><span data-ttu-id="0d6b6-108">Per caricare i dati da MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="0d6b6-108">To load data from MDS into Excel</span></span>  
  
1.  <span data-ttu-id="0d6b6-109">Aprire Excel e nella scheda **Dati master** connettersi a un repository MDS.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-109">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="0d6b6-110">Per altre informazioni, vedere [Connettersi a un repository MDS &#40;componente aggiuntivo MDS per Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="0d6b6-110">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="0d6b6-111">Nel riquadro **Esplora dati master** selezionare un modello e una versione.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-111">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="0d6b6-112">L'elenco di entità viene popolato.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-112">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="0d6b6-113">Se il riquadro **Esplora dati master** non è visibile, nel gruppo **Connetti e carica** fare clic su **Esplora dati master**.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-113">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="0d6b6-114">Se il riquadro **Esplora dati master** è disabilitato, significa che il foglio esistente contiene già i dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-114">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="0d6b6-115">Per abilitare il riquadro, aprire un nuovo foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-115">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="0d6b6-116">Nel riquadro **Esplora dati master** nell'elenco di entità fare doppio clic sull'entità che si vuole caricare.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-116">In the **Master Data Explorer** pane, in the list of entities, double-click the entity you want to load.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="0d6b6-117">Solo il primo milione di membri viene caricato in Excel.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-117">Only the first one million members are loaded into Excel.</span></span> <span data-ttu-id="0d6b6-118">Per filtrare l'elenco prima di caricarlo, sulla barra multifunzione del gruppo **Connetti e carica** fare clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-118">To filter the list before loading, on the ribbon in the **Connect and Load** group, click **Filter**.</span></span>  
    > -   <span data-ttu-id="0d6b6-119">Nelle colonne che sono elenchi vincolati (attributi basati su dominio) vengono caricati solo i primi 25.000 valori.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-119">In columns that are constrained lists (domain-based attributes), only the first 25,000 values are loaded.</span></span> <span data-ttu-id="0d6b6-120">È possibile modificare questo numero nella proprietà MaximumDbaEntitySize nel file excelusersettings.config che si trova nel computer in cui è installato Excel.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-120">You can change this number in the MaximumDbaEntitySize property in the excelusersettings.config file located on the computer that Excel is installed on.</span></span> <span data-ttu-id="0d6b6-121">Questo file si trova in C:\Users \\<utente \> \AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices \\ .</span><span class="sxs-lookup"><span data-stu-id="0d6b6-121">This file is located in C:\Users\\<user\>\AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices\\.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d6b6-122">Quando si caricano dati delimitati da testo usando il componente aggiuntivo per Microsoft Excel con Excel a 32 bit e le impostazioni per le proprietà relative al **numero di celle da caricare** e al **numero di celle da pubblicare** sono entrambe impostate sul valore massimo 1000, si verificherà un errore di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-122">When you load text-delimited data using the Add-in for Microsoft Excel with 32-bit Excel, and the settings for the **Cell Count to Load** and **Cell Count to Publish** properties are both set to the maximum of 1000, an out-of-memory error will occur.</span></span> <span data-ttu-id="0d6b6-123">È necessario usare Excel a 64 bit per usare le impostazioni massime per le due proprietà relative al **numero di celle da caricare** e al **numero di celle da pubblicare**.</span><span class="sxs-lookup"><span data-stu-id="0d6b6-123">You have to use 64-bit Excel to use the maximum settings for **Cell Count to Load** and **Cell Count to Publish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0d6b6-124">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0d6b6-124">Next Steps</span></span>  
 [<span data-ttu-id="0d6b6-125">Pubblicare dati da Excel a MDS &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0d6b6-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="0d6b6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d6b6-126">See Also</span></span>  
 <span data-ttu-id="0d6b6-127">[Caricamento dei dati &#40;Componente aggiuntivo MDS per Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="0d6b6-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="0d6b6-128">[Finestra di dialogo filtro &#40;Componente aggiuntivo MDS per Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="0d6b6-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="0d6b6-129">Pubblicazione dei dati &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0d6b6-129">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
