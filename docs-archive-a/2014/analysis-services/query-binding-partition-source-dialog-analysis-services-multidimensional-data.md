---
title: Dettagli dell'associazione di query (finestra di dialogo origine partizione) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitionfilterexpression.f1
ms.assetid: 697874d4-3f7a-4126-96f5-37cc8e2ee306
author: minewiskan
ms.author: owend
ms.openlocfilehash: 59d2ae1fed9d22366786e21a287a621f08418a5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628998"
---
# <a name="query-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="0ad6d-102">Dettagli dell'associazione di query (finestra di dialogo Origine partizione) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="0ad6d-102">Query Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="0ad6d-103">Usare l'opzione **Associazione di query** della finestra di dialogo **Origine partizione** per specificare la query che restituisce i dati per la partizione.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-103">Use the **Query Binding** option in the **Partition Source** dialog box to specify the query that provides the data for the partition.</span></span> <span data-ttu-id="0ad6d-104">Per visualizzare questo riquadro è possibile selezionare **Associazione di query** nell'opzione **Tipo di associazione** della finestra di dialogo **Origine partizione** .</span><span class="sxs-lookup"><span data-stu-id="0ad6d-104">You can display this pane by selecting **Query Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ad6d-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0ad6d-105">Options</span></span>  
 <span data-ttu-id="0ad6d-106">**Origine dati**</span><span class="sxs-lookup"><span data-stu-id="0ad6d-106">**Data source**</span></span>  
 <span data-ttu-id="0ad6d-107">Consente di selezionare l'origine dei dati su cui viene eseguita la query per fornire i dati di fatto per la partizione.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-107">Select the data source on which the query is executed to provide fact data for the partition.</span></span>  
  
 <span data-ttu-id="0ad6d-108">**Query**</span><span class="sxs-lookup"><span data-stu-id="0ad6d-108">**Query**</span></span>  
 <span data-ttu-id="0ad6d-109">Consente di digitare o modificare l'istruzione SQL utilizzata per recuperare i dati dei fatti relativi al momento in cui è stata elaborata la partizione.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-109">Type or modify the SQL statement used when retrieving fact data when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ad6d-110">è possibile specificare una clausola WHERE per utilizzare un subset di record per questa partizione.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-110">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="0ad6d-111">Quando più partizioni si basano su un'unica tabella dei fatti è essenziale evitare la duplicazione di dati.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-111">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span> <span data-ttu-id="0ad6d-112">Per altre informazioni, vedere [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="0ad6d-112">For more information, see [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="0ad6d-113">**Controllo**</span><span class="sxs-lookup"><span data-stu-id="0ad6d-113">**Check**</span></span>  
 <span data-ttu-id="0ad6d-114">Fare clic per verificare che l'istruzione contenuta in **Query** sia un'istruzione SQL valida.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-114">Click to verify that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad6d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ad6d-115">See Also</span></span>  
 [<span data-ttu-id="0ad6d-116">Finestra di dialogo origine partizione &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="0ad6d-116">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
