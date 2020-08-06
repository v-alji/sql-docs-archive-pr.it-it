---
title: Corrispondenza Data Quality nel componente aggiuntivo MDS per Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: be78d051-0d56-46d3-bb89-327e218dadd6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 037e535452e7f19644837e0cbcfd02efec5422b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636247"
---
# <a name="data-quality-matching-in-the-mds-add-in-for-excel"></a><span data-ttu-id="6beff-102">Corrispondenza Data Quality nel componente aggiuntivo MDS per Excel</span><span class="sxs-lookup"><span data-stu-id="6beff-102">Data Quality Matching in the MDS Add-in for Excel</span></span>
  <span data-ttu-id="6beff-103">Con il tempo, sarà necessario aggiungere ulteriori dati al repository MDS.</span><span class="sxs-lookup"><span data-stu-id="6beff-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="6beff-104">Prima di aggiungere i dati, può essere utile confrontare i nuovi dati con quelli già gestiti in MDS, per verificare che non si stiano aggiungendo dati duplicati o non accurati.</span><span class="sxs-lookup"><span data-stu-id="6beff-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure you are not adding duplicate or inaccurate data.</span></span>  
  
 <span data-ttu-id="6beff-105">In [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] MDS viene usata la funzionalità Data Quality Services (DQS) di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per mettere in corrispondenza i dati simili.</span><span class="sxs-lookup"><span data-stu-id="6beff-105">The MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] uses the Data Quality Services (DQS) feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to match data that's similar.</span></span> <span data-ttu-id="6beff-106">Quando si utilizza la funzionalità di ricerca di corrispondenza nel componente aggiuntivo, i record simili vengono raggruppati e viene visualizzato un punteggio che rappresenta l'accuratezza del risultato.</span><span class="sxs-lookup"><span data-stu-id="6beff-106">When you use the matching functionality in the Add-in, similar records are grouped together and a score that represents the accuracy of the result is displayed.</span></span> <span data-ttu-id="6beff-107">Per altre informazioni sulla funzionalità di ricerca di corrispondenza fornita da DQS, vedere [Corrispondenza di dati](../../data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="6beff-107">For more information about the matching functionality provided by DQS, see [Data Matching](../../data-quality-services/data-matching.md).</span></span>  
  
## <a name="workflow-for-data-quality-matching"></a><span data-ttu-id="6beff-108">Flusso di lavoro per la corrispondenza Data Quality</span><span class="sxs-lookup"><span data-stu-id="6beff-108">Workflow for Data Quality Matching</span></span>  
 <span data-ttu-id="6beff-109">Quando si usa DQS con [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]MDS, usare il flusso di lavoro seguente:</span><span class="sxs-lookup"><span data-stu-id="6beff-109">When using DQS with the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use the following workflow:</span></span>  
  
1.  <span data-ttu-id="6beff-110">Recuperare un elenco di dati gestiti da MDS e combinarlo con un elenco non gestito in MDS.</span><span class="sxs-lookup"><span data-stu-id="6beff-110">Retrieve a list of MDS-managed data and combine it with a list that is not managed in MDS.</span></span> <span data-ttu-id="6beff-111">Per altre informazioni, vedere [Combinare i dati &#40;componente aggiuntivo MDS per Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="6beff-111">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="6beff-112">Utilizzare la Knowledge Base DQS per confrontare i dati nell'elenco combinato.</span><span class="sxs-lookup"><span data-stu-id="6beff-112">Use DQS knowledge to compare the data in the combined list.</span></span> <span data-ttu-id="6beff-113">Per altre informazioni, vedere [Cercare la corrispondenza tra dati simili &#40;componente aggiuntivo MDS per Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="6beff-113">For more information, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
3.  <span data-ttu-id="6beff-114">Per visualizzare ulteriori dettagli sulle analogie trovate da DQS, mostrare le colonne dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="6beff-114">To view more details about the similarities found by DQS, show the detail columns.</span></span>  
  
4.  <span data-ttu-id="6beff-115">Analizzare i risultati e determinare quali dati devono essere aggiunti al repository MDS e quali dati sono duplicati.</span><span class="sxs-lookup"><span data-stu-id="6beff-115">Go through the results and determine which data should be added to the MDS repository and which data is duplicated.</span></span>  
  
5.  <span data-ttu-id="6beff-116">Pubblicare i dati nuovi e/o aggiornati nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="6beff-116">Publish the new and/or updated data to the MDS repository.</span></span>  
  
## <a name="knowledge-bases"></a><span data-ttu-id="6beff-117">Knowledge base</span><span class="sxs-lookup"><span data-stu-id="6beff-117">Knowledge Bases</span></span>  
 <span data-ttu-id="6beff-118">I risultati della corrispondenza forniti nel componente aggiuntivo sono basati su una Knowledge Base DQS.</span><span class="sxs-lookup"><span data-stu-id="6beff-118">The matching results provided in the Add-in are based on a DQS knowledge base.</span></span>  
  
-   <span data-ttu-id="6beff-119">La Knowledge Base predefinita (DQS Data) viene creata al momento dell'installazione di DQS.</span><span class="sxs-lookup"><span data-stu-id="6beff-119">The default knowledge base (DQS Data) is created when DQS is installed.</span></span> <span data-ttu-id="6beff-120">Se si sceglie din utilizzare la Knowledge Base predefinita, senza aggiungere i criteri di corrispondenza alla Knowledge Base predefinita nel client Data Quality, è necessario eseguire il mapping delle colonne nel foglio di lavoro ai domini nella Knowledge Base, quindi assegnare un valore di peso ai domini scelti.</span><span class="sxs-lookup"><span data-stu-id="6beff-120">If you choose to use the default knowledge base (without adding a matching policy to the default knowledge base in the Data Quality Client), you must map columns in the worksheet to domains in the knowledge base, and then assign a weight value to the domains you choose.</span></span>  
  
-   <span data-ttu-id="6beff-121">È possibile utilizzare il client Data Quality per creare una nuova Knowledge Base con criteri di corrispondenza o per aggiungere i criteri di corrispondenza alla Knowledge Base predefinita.</span><span class="sxs-lookup"><span data-stu-id="6beff-121">You can use the Data Quality Client to create a new knowledge base with a matching policy, or to add a matching policy to the default knowledge base.</span></span> <span data-ttu-id="6beff-122">In questo caso, i valori di peso sono determinati dai criteri di corrispondenza già creati ed è necessario solo eseguire il mapping delle colonne ai domini.</span><span class="sxs-lookup"><span data-stu-id="6beff-122">In this case, the weight values are determined by the matching policy you already created and you need only to map the columns to the domains.</span></span> <span data-ttu-id="6beff-123">Per altre informazioni, vedere [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="6beff-123">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
 <span data-ttu-id="6beff-124">Per altre informazioni sulle Knowledge Base, vedere [Knowledge Base e domini DQS](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="6beff-124">For more information about knowledge bases, see [DQS Knowledge Bases and Domains](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6beff-125">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="6beff-125">Related Tasks</span></span>  
  
|<span data-ttu-id="6beff-126">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="6beff-126">Task Description</span></span>|<span data-ttu-id="6beff-127">Argomento</span><span class="sxs-lookup"><span data-stu-id="6beff-127">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="6beff-128">Combinare dati esterni con i dati gestiti da MDS in preparazione a un confronto.</span><span class="sxs-lookup"><span data-stu-id="6beff-128">Combine external data with MDS-managed data in preparation to compare it.</span></span>|[<span data-ttu-id="6beff-129">Combinare i dati &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6beff-129">Combine Data &#40;MDS Add-in for Excel&#41;</span></span>](combine-data-mds-add-in-for-excel.md)|  
|<span data-ttu-id="6beff-130">Utilizzare la Knowledge Base DQS per trovare analogie nei dati.</span><span class="sxs-lookup"><span data-stu-id="6beff-130">Use DQS knowledge to find similarities in your data.</span></span>|[<span data-ttu-id="6beff-131">Cercare la corrispondenza tra dati simili &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6beff-131">Match Similar Data &#40;MDS Add-in for Excel&#41;</span></span>](match-similar-data-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="6beff-132">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="6beff-132">Related Content</span></span>  
  
-   [<span data-ttu-id="6beff-133">Pubblicazione dei dati &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6beff-133">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="6beff-134">Corrispondenza di dati</span><span class="sxs-lookup"><span data-stu-id="6beff-134">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
