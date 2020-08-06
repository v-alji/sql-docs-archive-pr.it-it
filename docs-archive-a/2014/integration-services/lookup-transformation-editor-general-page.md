---
title: Editor trasformazione Ricerca (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.general.f1
ms.assetid: 4bd15e48-0feb-4f95-be91-5df58105dbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa178118f7e090b6a3c15c7ab9347f322461f07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713303"
---
# <a name="lookup-transformation-editor-general-page"></a><span data-ttu-id="44785-102">Editor trasformazione Ricerca (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="44785-102">Lookup Transformation Editor (General Page)</span></span>
  <span data-ttu-id="44785-103">Utilizzare la pagina **Generale** della finestra di dialogo Editor trasformazione Ricerca per selezionare la modalità di cache, selezionare il tipo di connessione e specificare la modalità di gestione delle righe senza voci corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="44785-103">Use the **General** page of the Lookup Transformation Editor dialog box to select the cache mode, select the connection type, and specify how to handle rows with no matching entries.</span></span>  
  
 <span data-ttu-id="44785-104">Per ulteriori informazioni sulla trasformazione Ricerca, vedere [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="44785-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="44785-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="44785-105">Options</span></span>  
 <span data-ttu-id="44785-106">**Full Cache**</span><span class="sxs-lookup"><span data-stu-id="44785-106">**Full cache**</span></span>  
 <span data-ttu-id="44785-107">Generare e caricare il set di dati di riferimento nella cache prima dell'esecuzione della trasformazione Ricerca.</span><span class="sxs-lookup"><span data-stu-id="44785-107">Generate and load the reference dataset into cache before the Lookup transformation is executed.</span></span>  
  
 <span data-ttu-id="44785-108">**Partial Cache**</span><span class="sxs-lookup"><span data-stu-id="44785-108">**Partial cache**</span></span>  
 <span data-ttu-id="44785-109">Generare il set di dati di riferimento durante l'esecuzione della trasformazione Ricerca.</span><span class="sxs-lookup"><span data-stu-id="44785-109">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="44785-110">Caricare le righe con le voci corrispondenti nel set di dati di riferimento e le righe senza voci corrispondenti nel set di dati nella cache.</span><span class="sxs-lookup"><span data-stu-id="44785-110">Load the rows with matching entries in the reference dataset and the rows with no matching entries in the dataset into cache.</span></span>  
  
 <span data-ttu-id="44785-111">**Nessuna cache**</span><span class="sxs-lookup"><span data-stu-id="44785-111">**No cache**</span></span>  
 <span data-ttu-id="44785-112">Generare il set di dati di riferimento durante l'esecuzione della trasformazione Ricerca.</span><span class="sxs-lookup"><span data-stu-id="44785-112">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="44785-113">Non sono stati caricati dati in cache.</span><span class="sxs-lookup"><span data-stu-id="44785-113">No data is loaded into cache.</span></span>  
  
 <span data-ttu-id="44785-114">**Gestione connessione della cache**</span><span class="sxs-lookup"><span data-stu-id="44785-114">**Cache connection manager**</span></span>  
 <span data-ttu-id="44785-115">Configurare la trasformazione Ricerca per l'utilizzo della gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="44785-115">Configure the Lookup transformation to use a Cache connection manager.</span></span> <span data-ttu-id="44785-116">L'opzione è disponibile solo se è stata selezionata anche l'opzione Full Cache.</span><span class="sxs-lookup"><span data-stu-id="44785-116">This option is available only if the Full cache option is selected.</span></span>  
  
 <span data-ttu-id="44785-117">**Gestione connessione OLE DB**</span><span class="sxs-lookup"><span data-stu-id="44785-117">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="44785-118">Configurare la trasformazione Ricerca per l'utilizzo della gestione connessione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="44785-118">Configure the Lookup transformation to use an OLE DB connection manager.</span></span>  
  
 <span data-ttu-id="44785-119">**Specificare come gestire le righe senza voci corrispondenti**</span><span class="sxs-lookup"><span data-stu-id="44785-119">**Specify how to handle rows with no matching entries**</span></span>  
 <span data-ttu-id="44785-120">Selezionare un'opzione per la gestione delle righe che non dispongono di almeno una voce corrispondente nel set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="44785-120">Select an option for handling rows that do not match at least one entry in the reference dataset.</span></span>  
  
 <span data-ttu-id="44785-121">Quando si seleziona **Reindirizza righe all'output nessuna corrispondenza**, le righe vengono reindirizzate a un output senza corrispondenze e non vengono gestite come errori.</span><span class="sxs-lookup"><span data-stu-id="44785-121">When you select **Redirect rows to no match output**, the rows are redirected to a no match output and are not handled as errors.</span></span> <span data-ttu-id="44785-122">L'opzione **Errore** nella pagina **Output errori** della finestra di dialogo **Editor trasformazione Ricerca** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="44785-122">The **Error** option on the **Error Output** page of the **Lookup Transformation Editor** dialog box is not available.</span></span>  
  
 <span data-ttu-id="44785-123">Quando si seleziona un'altra opzione nella casella di riepilogo **Specificare come gestire le righe senza voci corrispondenti** , le righe vengono gestite come errori.</span><span class="sxs-lookup"><span data-stu-id="44785-123">When you select any other option in the **Specify how to handle rows with no matching entries** list box, the rows are handled as errors.</span></span> <span data-ttu-id="44785-124">L'opzione **Errore** nella pagina **Output errori** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="44785-124">The **Error** option on the **Error Output** page is available.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="44785-125">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="44785-125">External Resources</span></span>  
 <span data-ttu-id="44785-126">Intervento nel blog sulle [modalità cache di ricerca](https://go.microsoft.com/fwlink/?LinkId=219518) su blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="44785-126">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44785-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44785-127">See Also</span></span>  
 <span data-ttu-id="44785-128">[Gestione connessione della cache](connection-manager/cache-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="44785-128">[Cache Connection Manager](connection-manager/cache-connection-manager.md) </span></span>  
 <span data-ttu-id="44785-129">[Editor trasformazione Ricerca &#40;pagina connessione&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="44785-129">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="44785-130">[Editor trasformazione Ricerca &#40;pagina colonne&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="44785-130">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="44785-131">[Editor trasformazione Ricerca &#40;pagina avanzate&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="44785-131">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="44785-132">Editor trasformazione Ricerca &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="44785-132">Lookup Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/lookup-transformation-editor-error-output-page.md)  
  
  
