---
title: Limitazione righe (creazione guidata partizione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.typefilterexpression.f1
ms.assetid: eec8da8f-eab4-4ac4-a81d-995c814f88ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b0acc9ab24cfe92877d9abcd86353c85b4f8905
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625646"
---
# <a name="restrict-rows-partition-wizard"></a><span data-ttu-id="b0715-102">Limitazione righe (Creazione guidata partizione)</span><span class="sxs-lookup"><span data-stu-id="b0715-102">Restrict Rows (Partition Wizard)</span></span>
  <span data-ttu-id="b0715-103">La pagina **Limitazione righe** consente di limitare le righe che verranno recuperate dalla tabella specificata e quindi aggregate e incluse nella partizione.</span><span class="sxs-lookup"><span data-stu-id="b0715-103">Use the **Restrict Rows** page to restrict the rows that will be retrieved from the specified table and will be aggregated and included in the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0715-104"> Questa pagina viene visualizzata solo se è stata selezionata un'unica tabella nella pagina **Impostazione informazioni origine** .</span><span class="sxs-lookup"><span data-stu-id="b0715-104">This page is appears only if you selected a single table in the **Specify Source Information** page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b0715-105"> Se in **Tabelle disponibili** nella pagina **Impostazione informazioni origine** è stata specificata una tabella utilizzata da un'altra partizione, sarà necessario inserire una query nella pagina **Limitazione righe** o si rischia la duplicazione dei dati nel cubo.</span><span class="sxs-lookup"><span data-stu-id="b0715-105">If you specified a table in **Available Tables** on the **Specify Source Information** page that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b0715-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b0715-106">Options</span></span>  
 <span data-ttu-id="b0715-107">**Specificare una query per limitare le righe**</span><span class="sxs-lookup"><span data-stu-id="b0715-107">**Specify a query to restrict rows**</span></span>  
 <span data-ttu-id="b0715-108">Selezionare questa opzione per immettere nella casella **Query** una query che limiti le righe.</span><span class="sxs-lookup"><span data-stu-id="b0715-108">Select to enter a query that restricts rows into the **Query** box.</span></span>  
  
 <span data-ttu-id="b0715-109">Se la casella **Query** è vuota quando viene selezionata l'opzione, tale opzione verrà popolata con un'istruzione SQL che recupera tutte le colonne e le righe dalla tabella precedentemente selezionata.</span><span class="sxs-lookup"><span data-stu-id="b0715-109">If **Supply a WHERE clause** is empty when this option is selected, that option is populated with an SQL statement that retrieves all columns and all rows from the previously selected table.</span></span>  
  
 <span data-ttu-id="b0715-110">**Query**</span><span class="sxs-lookup"><span data-stu-id="b0715-110">**Query**</span></span>  
 <span data-ttu-id="b0715-111">Consente di digitare o modificare l'istruzione SQL utilizzata quando vengono recuperate le righe dalla tabella durante l'elaborazione della partizione.</span><span class="sxs-lookup"><span data-stu-id="b0715-111">Type or modify the SQL statement used when retrieving rows from the table when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b0715-112">è possibile specificare una clausola WHERE per utilizzare un subset di record per questa partizione.</span><span class="sxs-lookup"><span data-stu-id="b0715-112">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="b0715-113">Quando più partizioni si basano su un'unica tabella dei fatti è essenziale evitare la duplicazione di dati.</span><span class="sxs-lookup"><span data-stu-id="b0715-113">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span>  
  
 <span data-ttu-id="b0715-114">**Controllo**</span><span class="sxs-lookup"><span data-stu-id="b0715-114">**Check**</span></span>  
 <span data-ttu-id="b0715-115">Verifica che l'istruzione presente in **Query** sia un'istruzione SQL valida.</span><span class="sxs-lookup"><span data-stu-id="b0715-115">Verifies that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0715-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0715-116">See Also</span></span>  
 [<span data-ttu-id="b0715-117">Partizioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="b0715-117">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
