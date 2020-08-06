---
title: Combinare i dati (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: a867dc15-5a0d-457c-8304-ac323bcf9377
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bc2d5bffb6d7a12164a8643e9a790b32538f8979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714479"
---
# <a name="combine-data-mds-add-in-for-excel"></a><span data-ttu-id="5d2ee-102">Combinare i dati (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="5d2ee-102">Combine Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="5d2ee-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]è possibile combinare i dati di due fogli di lavoro quando si desidera confrontare i dati prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], combine data from two worksheets when you want to compare data before publishing.</span></span> <span data-ttu-id="5d2ee-104">In questa procedura verranno combinati i dati di due fogli di lavoro in un unico foglio.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-104">In this procedure, you combine data from a two worksheets into one.</span></span> <span data-ttu-id="5d2ee-105">Sarà quindi possibile eseguire ulteriori confronti e determinare quali dati eventualmente pubblicare nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-105">Then you can perform further comparisons and determine which data, if any, to publish to the MDS repository.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5d2ee-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5d2ee-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="5d2ee-107">È necessario disporre di un foglio di lavoro contenente dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-107">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="5d2ee-108">Per altre informazioni, vedere [caricare i dati da MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5d2ee-108">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="5d2ee-109">È necessario disporre di un foglio di lavoro contenente i dati che si desidera combinare con i dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-109">You must have a worksheet that contains data you want to combine with MDS-managed data.</span></span> <span data-ttu-id="5d2ee-110">In questo foglio deve essere presente una riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-110">This sheet must have a header row.</span></span>  
  
### <a name="to-combine-non-managed-data-into-an-mds-managed-sheet"></a><span data-ttu-id="5d2ee-111">Per combinare dati non gestiti in un foglio gestito da MDS</span><span class="sxs-lookup"><span data-stu-id="5d2ee-111">To combine non-managed data into an MDS-managed sheet</span></span>  
  
1.  <span data-ttu-id="5d2ee-112">Nel foglio contenente i dati gestiti da MDS fare clic su **Combina dati** nel gruppo **Pubblica e convalida**.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-112">On the sheet that contains MDS-managed data, in the **Publish and Validate** group, click **Combine Data**.</span></span>  
  
2.  <span data-ttu-id="5d2ee-113">Nella finestra di dialogo **Combina dati** fare clic sull'icona accanto alla casella di testo **Intervallo da combinare con dati MDS** .</span><span class="sxs-lookup"><span data-stu-id="5d2ee-113">In the **Combine Data** dialog box, next to the **Range to combine with MDS data** text box, click the icon.</span></span> <span data-ttu-id="5d2ee-114">La finestra di dialogo verrà ridotta.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-114">The dialog box contracts.</span></span>  
  
3.  <span data-ttu-id="5d2ee-115">Fare clic sul foglio contenente i dati che si desidera combinare.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-115">Click the sheet that contains the data you want to combine.</span></span>  
  
4.  <span data-ttu-id="5d2ee-116">Evidenziare tutte le celle nel foglio che si desidera combinare, inclusa la riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-116">Highlight all cells on the sheet that you want to combine, including the header row.</span></span>  
  
5.  <span data-ttu-id="5d2ee-117">Nella finestra di dialogo **Combina dati** fare clic sull'icona.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-117">In the **Combine Data** dialog box, click the icon.</span></span> <span data-ttu-id="5d2ee-118">La finestra di dialogo verrà espansa.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-118">The dialog box expands.</span></span>  
  
6.  <span data-ttu-id="5d2ee-119">Per una colonna elencata per l'entità MDS, selezionare una colonna in **Colonna corrispondente**.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-119">For a column listed for the MDS entity, select a column under **Corresponding Column**.</span></span> <span data-ttu-id="5d2ee-120">Tutte le colonne MDS non necessitano di colonne corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-120">All MDS columns do not need corresponding columns.</span></span>  
  
7.  <span data-ttu-id="5d2ee-121">Fare clic su **Combina**.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-121">Click **Combine**.</span></span> <span data-ttu-id="5d2ee-122">Verrà visualizzata una colonna **ORIGINE** , che indica se i dati provengono da MDS o da un'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="5d2ee-122">A **SOURCE** column is displayed, indicating whether the data is from MDS or an external source.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5d2ee-123">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5d2ee-123">Next Steps</span></span>  
  
-   <span data-ttu-id="5d2ee-124">Per trovare le analogie tra i dati gestiti da MDS e i dati esterni, vedere [Cercare la corrispondenza tra dati simili &#40;componente aggiuntivo MDS per Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5d2ee-124">To find similarities between the MDS-managed and external data, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2ee-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d2ee-125">See Also</span></span>  
 <span data-ttu-id="5d2ee-126">[Caricamento dei dati &#40;Componente aggiuntivo MDS per Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="5d2ee-126">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="5d2ee-127">Corrispondenza Data Quality nel componente aggiuntivo MDS per Excel</span><span class="sxs-lookup"><span data-stu-id="5d2ee-127">Data Quality Matching in the MDS Add-in for Excel</span></span>](data-quality-matching-in-the-mds-add-in-for-excel.md)  
  
  
