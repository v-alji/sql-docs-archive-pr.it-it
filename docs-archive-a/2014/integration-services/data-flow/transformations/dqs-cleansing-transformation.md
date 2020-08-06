---
title: Trasformazione DQS Cleansing | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data correction
- correct data
ms.assetid: d2ec1b1a-c745-4741-b57c-6fdb524a154c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e980497905b8fa96a73516916af17f934221992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624271"
---
# <a name="dqs-cleansing-transformation"></a><span data-ttu-id="f801d-102">Trasformazione DQS Cleansing</span><span class="sxs-lookup"><span data-stu-id="f801d-102">DQS Cleansing Transformation</span></span>
  <span data-ttu-id="f801d-103">La trasformazione DQS Cleansing utilizza Data Quality Services (DQS) per correggere i dati da un'origine dati connessa, applicando le regole approvate create per l'origine dati connessa o un'origine dati simile.</span><span class="sxs-lookup"><span data-stu-id="f801d-103">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data from a connected data source, by applying approved rules that were created for the connected data source or a similar data source.</span></span> <span data-ttu-id="f801d-104">Per ulteriori informazioni sulle regole di correzione dei dati, vedere [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="f801d-104">For more information about data correction rules, see [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span> <span data-ttu-id="f801d-105">Per ulteriori informazioni su DQS, vedere [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="f801d-105">For more information DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="f801d-106">Per determinare se è necessario correggere i dati, la trasformazione DQS Cleansing elabora i dati da una colonna di input quando le condizioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="f801d-106">To determine whether the data has to be corrected, the DQS Cleansing transformation processes data from an input column when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="f801d-107">La colonna è selezionata per la correzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="f801d-107">The column is selected for data correction.</span></span>  
  
-   <span data-ttu-id="f801d-108">Il tipo di dati della colonna è supportato per la correzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="f801d-108">The column data type is supported for data correction.</span></span>  
  
-   <span data-ttu-id="f801d-109">È stato eseguito il mapping della colonna a un dominio con un tipo di dati compatibile.</span><span class="sxs-lookup"><span data-stu-id="f801d-109">The column is mapped a domain that has a compatible data type.</span></span>  
  
 <span data-ttu-id="f801d-110">La trasformazione include inoltre un output degli errori da configurare per gestire gli errori a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="f801d-110">The transformation also includes an error output that you configure to handle row-level errors.</span></span> <span data-ttu-id="f801d-111">Per configurare l'output degli errori, utilizzare **Editor trasformazione DQS Cleansing**.</span><span class="sxs-lookup"><span data-stu-id="f801d-111">To configure the error output, use the **DQS Cleansing Transformation Editor**.</span></span>  
  
 <span data-ttu-id="f801d-112">È possibile includere [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) nel flusso di dati per identificare righe di dati che probabilmente sono duplicati.</span><span class="sxs-lookup"><span data-stu-id="f801d-112">You can include the [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) in the data flow to identify rows of data that are likely to be duplicates.</span></span>  
  
## <a name="data-quality-projects-and-values"></a><span data-ttu-id="f801d-113">Progetti Data Quality e valori</span><span class="sxs-lookup"><span data-stu-id="f801d-113">Data Quality Projects and Values</span></span>  
 <span data-ttu-id="f801d-114">Quando si elaborano i dati con la trasformazione DQS Cleansing, viene creato un progetto di pulizia nel server Data Quality.</span><span class="sxs-lookup"><span data-stu-id="f801d-114">When you process data with the DQS Cleansing transformation, a cleansing project is created on the Data Quality Server.</span></span> <span data-ttu-id="f801d-115">È possibile utilizzare il client Data Quality per gestire il progetto.</span><span class="sxs-lookup"><span data-stu-id="f801d-115">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="f801d-116">Inoltre, è possibile utilizzare il client Data Quality per importare i valori del progetto in un dominio di una Knowledge Base in DQS.</span><span class="sxs-lookup"><span data-stu-id="f801d-116">In addition, you can use the Data Quality Client to import the project values into a DQS knowledge base domain.</span></span> <span data-ttu-id="f801d-117">È possibile importare i valori solo in un dominio (o dominio collegato) configurato per l'utilizzo dalla trasformazione DQS Cleansing.</span><span class="sxs-lookup"><span data-stu-id="f801d-117">You can import the values only to a domain (or linked domain) that the DQS Cleansing transformation was configured to use.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f801d-118">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="f801d-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f801d-119">Aprire progetti di Integration Services in Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="f801d-119">Open Integration Services Projects in Data Quality Client</span></span>](../../../data-quality-services/open-integration-services-projects-in-data-quality-client.md)  
  
-   [<span data-ttu-id="f801d-120">Importare i valori di un progetto di pulizia in un dominio</span><span class="sxs-lookup"><span data-stu-id="f801d-120">Import Cleansing Project Values into a Domain</span></span>](../../../data-quality-services/import-cleansing-project-values-into-a-domain.md)  
  
-   [<span data-ttu-id="f801d-121">Applicare le regole relative alla qualità dei dati all'origine dati</span><span class="sxs-lookup"><span data-stu-id="f801d-121">Apply Data Quality Rules to Data Source</span></span>](apply-data-quality-rules-to-data-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="f801d-122">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="f801d-122">Related Content</span></span>  
  
-   [<span data-ttu-id="f801d-123">Gestire &#40;aprire, sbloccare, rinominare ed eliminare&#41; un progetto Data Quality</span><span class="sxs-lookup"><span data-stu-id="f801d-123">Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project</span></span>](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md)  
  
-   <span data-ttu-id="f801d-124">Articolo relativo alla [pulizia dei dati complessi utilizzando domini compositi](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx)su social.technet.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f801d-124">Article, [Cleansing complex data using composite domains](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx), on social.technet.microsoft.com.</span></span>  
  
  
