---
title: Colonne corrispondenti Data Quality (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f683fdc6-0d4c-4793-8143-567616cb2094
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 939ec9727cc81ce3b206b8bc7ca3ed8dd62c3877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623368"
---
# <a name="data-quality-matching-columns-mds-add-in-for-excel"></a><span data-ttu-id="c173c-102">Colonne corrispondenti Data Quality (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="c173c-102">Data Quality Matching Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="c173c-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]dopo avere verificato la corrispondenza dei dati, nel gruppo **Data Quality** sulla barra multifunzione è possibile fare clic su **Mostra dettagli** per visualizzare le colonne con informazioni dettagliate sulla corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="c173c-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], after you match data, in the **Data Quality** group on the ribbon, you can click **Show Details** to display columns that provide matching details.</span></span>  
  
 <span data-ttu-id="c173c-104">Nella tabella seguente vengono illustrate le colonne visualizzate quando si verifica la corrispondenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="c173c-104">The following table shows the columns that are displayed when matching data.</span></span>  
  
|<span data-ttu-id="c173c-105">Nome</span><span class="sxs-lookup"><span data-stu-id="c173c-105">Name</span></span>|<span data-ttu-id="c173c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c173c-106">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="c173c-107">**CLUSTER_ID**</span><span class="sxs-lookup"><span data-stu-id="c173c-107">**CLUSTER_ID**</span></span>|<span data-ttu-id="c173c-108">Identificatore univoco utilizzato per raggruppare record simili.</span><span class="sxs-lookup"><span data-stu-id="c173c-108">A unique identifier used to group similar records.</span></span> <span data-ttu-id="c173c-109">Il valore di **CLUSTER_ID**è lo stesso per tutte le righe simili.</span><span class="sxs-lookup"><span data-stu-id="c173c-109">All rows that are similar have the same **CLUSTER_ID**.</span></span> <span data-ttu-id="c173c-110">Se non è visualizzato alcun valore **CLUSTER_ID** per una riga, non sono stati trovati record simili.</span><span class="sxs-lookup"><span data-stu-id="c173c-110">If no **CLUSTER_ID** is displayed for a row, then no similar records were found.</span></span>|  
|<span data-ttu-id="c173c-111">**RECORD_ID**</span><span class="sxs-lookup"><span data-stu-id="c173c-111">**RECORD_ID**</span></span>|<span data-ttu-id="c173c-112">Identificatore univoco utilizzato per identificare i record.</span><span class="sxs-lookup"><span data-stu-id="c173c-112">A unique identifier used to identify records.</span></span> <span data-ttu-id="c173c-113">Simile al valore Codice archiviato nel repository MDS, è un valore utilizzato per identificare un record.</span><span class="sxs-lookup"><span data-stu-id="c173c-113">Similar to the Code value stored in the MDS repository, it is a value used to identify a record.</span></span> <span data-ttu-id="c173c-114">Viene generato automaticamente ogni volta che viene eseguita la ricerca della corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="c173c-114">It is generated automatically each time matching takes place.</span></span>|  
|<span data-ttu-id="c173c-115">**PIVOT_MARK**</span><span class="sxs-lookup"><span data-stu-id="c173c-115">**PIVOT_MARK**</span></span>|<span data-ttu-id="c173c-116">Record arbitrario con cui vengono confrontati gli altri record. Non dispone di un valore di punteggio.</span><span class="sxs-lookup"><span data-stu-id="c173c-116">An arbitrary record that other records are compared to; it does not have a score value.</span></span>|  
|<span data-ttu-id="c173c-117">**Punteggio**</span><span class="sxs-lookup"><span data-stu-id="c173c-117">**SCORE**</span></span>|<span data-ttu-id="c173c-118">Rappresenta il livello di analogia dei record del gruppo con il record pivot.</span><span class="sxs-lookup"><span data-stu-id="c173c-118">Represents how similar the records in the group are to the pivot record.</span></span> <span data-ttu-id="c173c-119">Il punteggio è determinato da DQS.</span><span class="sxs-lookup"><span data-stu-id="c173c-119">This score is determined by DQS.</span></span> <span data-ttu-id="c173c-120">Se non viene visualizzato alcun punteggio, il record rappresenta il pivot per gli altri record oppure non è stata trovata alcuna corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="c173c-120">If no score is displayed, either the record is the pivot for other records, or no matches were found.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c173c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c173c-121">See Also</span></span>  
 <span data-ttu-id="c173c-122">[Corrispondenza Data Quality nel Componente aggiuntivo MDS per Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="c173c-122">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="c173c-123">[Corrisponde a dati simili &#40;Componente aggiuntivo MDS per Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="c173c-123">[Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="c173c-124">Corrispondenza di dati</span><span class="sxs-lookup"><span data-stu-id="c173c-124">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
