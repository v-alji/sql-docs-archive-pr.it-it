---
title: Modificare un'origine della partizione per utilizzare una tabella dei fatti diversa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact tables [Analysis Services]
- partitions [Analysis Services], fact tables
ms.assetid: 5508312f-8e46-4802-9362-6688ca03d098
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0063a6023d769dc6dccd616655d10e0bd3c65a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721999"
---
# <a name="change-a-partition-source-to-use-a-different-fact-table"></a><span data-ttu-id="75823-102">Modificare l'origine di una partizione in modo da utilizzare una tabella dei fatti diversa</span><span class="sxs-lookup"><span data-stu-id="75823-102">Change a partition source to use a different fact table</span></span>
  <span data-ttu-id="75823-103">Durante la creazione di una partizione per un cubo, è possibile scegliere di utilizzare una tabella dei fatti diversa.</span><span class="sxs-lookup"><span data-stu-id="75823-103">When you create a partition for a cube, you can choose to use a different fact table.</span></span> <span data-ttu-id="75823-104">Le tabelle diverse possono derivare da una singola vista origine dati, da più viste origine dati diverse o da origini dei dati diverse.</span><span class="sxs-lookup"><span data-stu-id="75823-104">Different tables may be from a single data source view, from different data source views, or from different data sources.</span></span> <span data-ttu-id="75823-105">Una vista origine dati può inoltre contenere tabelle diverse derivate da più origini dei dati.</span><span class="sxs-lookup"><span data-stu-id="75823-105">A data source view may also contain different tables from more than one data source.</span></span>  
  
 <span data-ttu-id="75823-106">Tutte le tabelle dei fatti e le dimensioni delle partizioni di un cubo devono avere la stessa struttura della tabella dei fatti e delle dimensioni del cubo.</span><span class="sxs-lookup"><span data-stu-id="75823-106">All fact tables and dimensions for a cube's partitions must have the same structure as the fact table and dimensions of the cube.</span></span> <span data-ttu-id="75823-107">Ad esempio, tabelle dei fatti diverse possono avere la stessa struttura ma contenere dati relativi a linee di prodotto o anni diversi.</span><span class="sxs-lookup"><span data-stu-id="75823-107">For example, different fact tables can have the same structure but contain data for different years or different product lines.</span></span>  
  
 <span data-ttu-id="75823-108">È possibile specificare una tabella dei fatti nella pagina **Impostazione informazioni origine** della Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="75823-108">You specify a fact table on the **Specify Source Information** page of the Partition Wizard.</span></span> <span data-ttu-id="75823-109">In questa pagina, nel gruppo Origine partizione accanto a **Cerca in**specificare un'origine dei dati o una vista origine dati in cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="75823-109">On this page, in the Partition Source group next to **Look in**, specify a data source or data source view in which to look.</span></span> <span data-ttu-id="75823-110">Successivamente, fare clic su **Trova tabelle**e quindi selezionare la tabella da usare in **Tabelle disponibili**.</span><span class="sxs-lookup"><span data-stu-id="75823-110">Next, click **Find Tables**, and then, under **Available Tables**, select the table you want to use.</span></span>  
  
 <span data-ttu-id="75823-111">Se si utilizzano tabelle dei fatti diverse, verificare che non esistano dati duplicati nelle partizioni.</span><span class="sxs-lookup"><span data-stu-id="75823-111">When you use different fact tables, ensure that no data is duplicated among the partitions.</span></span> <span data-ttu-id="75823-112">Se ad esempio una tabella dei fatti contiene solo le transazioni relative al 2012 e un'altra tabella dei fatti solo quelle relative al 2013, i dati delle due tabelle saranno indipendenti.</span><span class="sxs-lookup"><span data-stu-id="75823-112">For example, if one fact table contains transactions for 2012 only, and another fact table contains transactions for 2013 only, these tables contain independent data.</span></span> <span data-ttu-id="75823-113">Analogamente, le tabelle dei fatti relative a linee di prodotti diverse o ad aree geografiche distinte sono indipendenti.</span><span class="sxs-lookup"><span data-stu-id="75823-113">Similarly, fact tables for distinct product lines or distinct geographical areas are independent.</span></span>  
  
 <span data-ttu-id="75823-114">È possibile, ma non consigliabile, utilizzare tabelle dei fatti diverse contenenti dati duplicati.</span><span class="sxs-lookup"><span data-stu-id="75823-114">It is possible, but not recommended, to use different fact tables that contain duplicated data.</span></span> <span data-ttu-id="75823-115">In questo caso, è necessario applicare filtri alle partizioni per garantire che i dati utilizzati da una partizione non vengano utilizzati dalle altre.</span><span class="sxs-lookup"><span data-stu-id="75823-115">In this case, you must use filters in the partitions to ensure that data used by one partition is not used by any other partition.</span></span> <span data-ttu-id="75823-116">Per altre informazioni, vedere [Creare e gestire una partizione locale &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="75823-116">For more information, see [Create and Manage a Local Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75823-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75823-117">See Also</span></span>  
 [<span data-ttu-id="75823-118">Creare e gestire una partizione locale &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="75823-118">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](create-and-manage-a-local-partition-analysis-services.md)  
  
  
