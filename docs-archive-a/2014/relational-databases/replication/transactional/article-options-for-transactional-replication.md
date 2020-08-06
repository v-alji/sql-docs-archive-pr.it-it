---
title: Opzioni degli articoli per la replica transazionale | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], transactional replication options
- transactional replication, article options
ms.assetid: 3469b185-0ea5-4690-a71c-717230d886b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1cc13a3d11e35ed47eac4ff401fb8b7cb607b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629343"
---
# <a name="article-options-for-transactional-replication"></a><span data-ttu-id="2452e-102">Opzioni degli articoli per la replica transazionale</span><span class="sxs-lookup"><span data-stu-id="2452e-102">Article Options for Transactional Replication</span></span>
  <span data-ttu-id="2452e-103">Sono disponibili svariate opzioni per gli articoli delle repliche transazionali.</span><span class="sxs-lookup"><span data-stu-id="2452e-103">There are a number of options for articles in transactional publications.</span></span> <span data-ttu-id="2452e-104">La replica transazionale consente infatti di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2452e-104">With transactional replication, you can do the following:</span></span>  
  
-   <span data-ttu-id="2452e-105">Specificare le modalità di propagazione delle modifiche dal server di pubblicazione ai Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="2452e-105">Specify how changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="2452e-106">Per altre informazioni, vedere [Specificare la modalità di propagazione delle modifiche per gli articoli transazionali](transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="2452e-106">For more information, see [Specify How Changes Are Propagated for Transactional Articles](transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
-   <span data-ttu-id="2452e-107">Specificare che l'esecuzione di una stored procedure deve essere replicata.</span><span class="sxs-lookup"><span data-stu-id="2452e-107">Specify that the execution of a stored procedure be replicated.</span></span> <span data-ttu-id="2452e-108">Ciò risulta utile per la replica dei risultati di stored procedure orientate alla manutenzione che influiscono su ingenti quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="2452e-108">This is useful in replicating the results of maintenance-oriented stored procedures that affect large amounts of data.</span></span> <span data-ttu-id="2452e-109">Per altre informazioni, vedere [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="2452e-109">For more information, see [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="2452e-110">Specificare le opzioni di schema, ad esempio se i vincoli e i trigger vengono copiati nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="2452e-110">Specify schema options, such as whether constraints and triggers are copied to the Subscriber.</span></span> <span data-ttu-id="2452e-111">Per altre informazioni, vedere [Specificare le opzioni dello schema](../publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="2452e-111">For more information, see [Specify Schema Options](../publish/specify-schema-options.md).</span></span>  
  
-   <span data-ttu-id="2452e-112">Utilizzare i filtri di righe e di colonne.</span><span class="sxs-lookup"><span data-stu-id="2452e-112">Use row filters and column filters.</span></span> <span data-ttu-id="2452e-113">L'applicazione di filtri agli articoli di una tabella consente di creare partizioni di dati da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="2452e-113">Filtering table articles enables you to create partitions of data to be published.</span></span> <span data-ttu-id="2452e-114">Per altre informazioni, vedere [Filtrare i dati pubblicati](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="2452e-114">For more information, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2452e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2452e-115">See Also</span></span>  
 [<span data-ttu-id="2452e-116">Pubblicare dati e oggetti di database</span><span class="sxs-lookup"><span data-stu-id="2452e-116">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  
