---
title: Monitoraggio per le esecuzioni di pacchetti e altre operazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cbbcd79f-ab9b-46ec-84cb-4821c1d16b99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 628b62d9c8e01d0dc0bf641551de67c3838a4504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637986"
---
# <a name="monitoring-for-package-executions-and-other-operations"></a><span data-ttu-id="207e1-102">Monitoraggio per le esecuzioni di pacchetti e altre operazioni</span><span class="sxs-lookup"><span data-stu-id="207e1-102">Monitoring for Package Executions and Other Operations</span></span>
  <span data-ttu-id="207e1-103">È possibile monitorare esecuzioni di pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , convalide di progetto e altre operazioni di usando uno o più strumenti tra quelli indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="207e1-103">You can monitor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package executions, project validations, and other operations by using one of more of the following tools.</span></span> <span data-ttu-id="207e1-104">Alcuni strumenti, tra cui le scelte dei dati, sono disponibili solo per i progetti distribuiti nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="207e1-104">Certain tools such as data taps are available only for projects that are deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="207e1-105">Log</span><span class="sxs-lookup"><span data-stu-id="207e1-105">Logs</span></span>  
  
     <span data-ttu-id="207e1-106">Per altre informazioni, vedere [registrazione di Integration Services &#40;SSIS&#41;](integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="207e1-106">For more information, see [Integration Services &#40;SSIS&#41; Logging](integration-services-ssis-logging.md).</span></span>  
  
-   <span data-ttu-id="207e1-107">Report</span><span class="sxs-lookup"><span data-stu-id="207e1-107">Reports</span></span>  
  
     <span data-ttu-id="207e1-108">Per altre informazioni, vedere [report per il server Integration Services](../reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="207e1-108">For more information, see [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span></span>  
  
-   <span data-ttu-id="207e1-109">Viste</span><span class="sxs-lookup"><span data-stu-id="207e1-109">Views</span></span>  
  
     <span data-ttu-id="207e1-110">Per altre informazioni, vedere [viste &#40;Catalogo di Integration Services&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span><span class="sxs-lookup"><span data-stu-id="207e1-110">For more information, see [Views &#40;Integration Services Catalog&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span></span>  
  
-   <span data-ttu-id="207e1-111">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="207e1-111">Performance counters</span></span>  
  
     <span data-ttu-id="207e1-112">Per altre informazioni, vedere [i contatori delle prestazioni](performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="207e1-112">For more information, see [Performance Counters](performance-counters.md).</span></span>  
  
-   <span data-ttu-id="207e1-113">Scelte dei dati</span><span class="sxs-lookup"><span data-stu-id="207e1-113">Data taps</span></span>  
  
## <a name="operation-types"></a><span data-ttu-id="207e1-114">Tipi di operazione</span><span class="sxs-lookup"><span data-stu-id="207e1-114">Operation Types</span></span>  
 <span data-ttu-id="207e1-115">Nel catalogo `SSISDB` vengono monitorati numerosi tipi diversi di operazioni nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="207e1-115">Several different types of operations are monitored in the `SSISDB` catalog, on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="207e1-116">A ogni operazione possono essere associati più messaggi.</span><span class="sxs-lookup"><span data-stu-id="207e1-116">Each operation can have multiple messages associated with it.</span></span> <span data-ttu-id="207e1-117">Ogni messaggio può essere classificato in uno dei molti tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="207e1-117">Each message can be classified into one of several different types.</span></span> <span data-ttu-id="207e1-118">Ad esempio, un messaggio può essere informativo, di avviso o di errore.</span><span class="sxs-lookup"><span data-stu-id="207e1-118">For example, a message can be of type Information, Warning, or Error.</span></span> <span data-ttu-id="207e1-119">Per l'elenco completo dei tipi di messaggi, vedere la documentazione relativa alla vista Transact-SQL [catalog.operation_messages &#40;Database SSISDB&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="207e1-119">For the full list of message types, see the documentation for the Transact-SQL [catalog.operation_messages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database) view.</span></span> <span data-ttu-id="207e1-120">Per l'elenco completo dei tipi di operazioni, vedere [catalog.operations &#40;Database SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="207e1-120">For a full list of the operations types, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span></span>  
  
 <span data-ttu-id="207e1-121">Nove diversi tipi di stato consentono di indicare lo stato di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="207e1-121">Nine different status types are used to indicate the status of an operation.</span></span> <span data-ttu-id="207e1-122">Per l'elenco completo dei tipi di stato, vedere la vista [catalog.operations &#40;Database SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="207e1-122">For a full list of the status types, see the [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database) view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="207e1-123">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="207e1-123">Related Content</span></span>  
 <span data-ttu-id="207e1-124">Intervento nel blog relativo alla [panoramica dell'API T-SQL SSIS](https://go.microsoft.com/fwlink/?LinkId=249051)su blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="207e1-124">Blog entry, [SSIS T-SQL API Overview](https://go.microsoft.com/fwlink/?LinkId=249051), on blogs.msdn.com.</span></span>  
  
  
