---
title: Editor origine OData (pagina connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- Sql12.dts.designer.odatasource.connection.f1
ms.assetid: 20bcd347-4547-4fad-b182-9571030101df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ecd0d060ea2197ae7174325b654645fefa23505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629907"
---
# <a name="odata-source-editor-connection-page"></a><span data-ttu-id="0a7f0-102">Editor origine OData (pagina Connessione)</span><span class="sxs-lookup"><span data-stu-id="0a7f0-102">OData Source Editor (Connection Page)</span></span>
  <span data-ttu-id="0a7f0-103">Usare la pagina **Connessione** della finestra di dialogo **Editor origine OData** per selezionare la gestione connessione OData per l'origine OData.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-103">Use the **Connection** page of the **OData Source Editor** dialog box to select the OData connection manager for the OData source.</span></span> <span data-ttu-id="0a7f0-104">In questa pagina è inoltre possibile specificare una raccolta o un percorso della risorsa, nonché tutte le opzioni query per scegliere i dati che devono essere recuperati dall'origine OData.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-104">This page also lets you specify a collection or a resource path and any query options to indicate what data needs to be retrieved from the OData source.</span></span> <span data-ttu-id="0a7f0-105">Per altre informazioni sull'origine OData, vedere [Origine OData](data-flow/odata-source.md).</span><span class="sxs-lookup"><span data-stu-id="0a7f0-105">To learn more about the OData source, see [OData Source](data-flow/odata-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="0a7f0-106">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="0a7f0-106">Static Options</span></span>  
 <span data-ttu-id="0a7f0-107">**Gestione connessione OData**</span><span class="sxs-lookup"><span data-stu-id="0a7f0-107">**OData connection manager**</span></span>  
 <span data-ttu-id="0a7f0-108">Selezionare una gestione connessione esistente nell'elenco o crearne una nuova facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-108">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="0a7f0-109">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="0a7f0-109">**New**</span></span>  
 <span data-ttu-id="0a7f0-110">Creare una nuova gestione connessione usando la finestra di dialogo **Editor gestione connessione OData** .</span><span class="sxs-lookup"><span data-stu-id="0a7f0-110">Create a new connection manager by using the **OData Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="0a7f0-111">**Usa percorso risorsa o raccolta**</span><span class="sxs-lookup"><span data-stu-id="0a7f0-111">**Use collection or resource path**</span></span>  
 <span data-ttu-id="0a7f0-112">Consente di specificare il metodo per la selezione dei dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-112">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="0a7f0-113">Opzione</span><span class="sxs-lookup"><span data-stu-id="0a7f0-113">Option</span></span>|<span data-ttu-id="0a7f0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a7f0-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0a7f0-115">Raccolta</span><span class="sxs-lookup"><span data-stu-id="0a7f0-115">Collection</span></span>|<span data-ttu-id="0a7f0-116">Recuperare i dati dall'origine OData utilizzando il nome di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-116">Retrieve data from the OData source by using a collection name.</span></span>|  
|<span data-ttu-id="0a7f0-117">Percorso risorsa</span><span class="sxs-lookup"><span data-stu-id="0a7f0-117">Resource Path</span></span>|<span data-ttu-id="0a7f0-118">Recuperare i dati dall'origine OData utilizzando un percorso della risorsa.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-118">Retrieve data from the OData source by using a resource path.</span></span>|  
  
 <span data-ttu-id="0a7f0-119">**Opzioni query**</span><span class="sxs-lookup"><span data-stu-id="0a7f0-119">**Query options**</span></span>  
 <span data-ttu-id="0a7f0-120">Specificare le opzioni per la query.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-120">Specify options for the query.</span></span>  <span data-ttu-id="0a7f0-121">Ad esempio: $top=5</span><span class="sxs-lookup"><span data-stu-id="0a7f0-121">For example: $top=5</span></span>  
  
 <span data-ttu-id="0a7f0-122">**URL feed**</span><span class="sxs-lookup"><span data-stu-id="0a7f0-122">**Feed url**</span></span>  
 <span data-ttu-id="0a7f0-123">Viene visualizzato l'URL del feed di dati di sola lettura in base alle opzioni selezionate nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-123">Displays the read-only Feed URL based on options you selected on this dialog box.</span></span>  
  
 <span data-ttu-id="0a7f0-124">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="0a7f0-124">**Preview**</span></span>  
 <span data-ttu-id="0a7f0-125">Vengono visualizzati in anteprima i risultati tramite la finestra di dialogo **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="0a7f0-125">Preview results by using the **Preview** dialog box.</span></span> <span data-ttu-id="0a7f0-126">L'**anteprima** supporta la visualizzazione di un massimo di 20 righe.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-126">**Preview** can display up to 20 rows.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="0a7f0-127">Opzioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="0a7f0-127">Dynamic Options</span></span>  
  
### <a name="use-collection-or-resource-path--collection"></a><span data-ttu-id="0a7f0-128">Usa percorso risorsa o raccolta = Raccolta</span><span class="sxs-lookup"><span data-stu-id="0a7f0-128">Use collection or resource path = Collection</span></span>  
 <span data-ttu-id="0a7f0-129">**Raccolta**</span><span class="sxs-lookup"><span data-stu-id="0a7f0-129">**Collection**</span></span>  
 <span data-ttu-id="0a7f0-130">Selezionare una raccolta dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-130">Select a collection from the drop-down list.</span></span>  
  
### <a name="use-collection-or-resource-path--resource-path"></a><span data-ttu-id="0a7f0-131">Usa percorso risorsa o raccolta = Percorso risorsa</span><span class="sxs-lookup"><span data-stu-id="0a7f0-131">Use collection or resource path = Resource Path</span></span>  
 <span data-ttu-id="0a7f0-132">**Resource path**</span><span class="sxs-lookup"><span data-stu-id="0a7f0-132">**Resource path**</span></span>  
 <span data-ttu-id="0a7f0-133">Digitare un percorso della risorsa.</span><span class="sxs-lookup"><span data-stu-id="0a7f0-133">Type a resource path.</span></span> <span data-ttu-id="0a7f0-134">Ad esempio: Dipendenti</span><span class="sxs-lookup"><span data-stu-id="0a7f0-134">For example: Employees</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a7f0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a7f0-135">See Also</span></span>  
 <span data-ttu-id="0a7f0-136">[Editor origine OData &#40;pagina colonne&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="0a7f0-136">[OData Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="0a7f0-137">[Editor origine OData &#40;pagina output degli errori&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="0a7f0-137">[OData Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="0a7f0-138">Gestione connessione OData</span><span class="sxs-lookup"><span data-stu-id="0a7f0-138">OData Connection Manager</span></span>](connection-manager/odata-connection-manager.md)  
  
  
