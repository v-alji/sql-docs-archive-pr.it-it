---
title: Editor percorso flusso di dati (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.patheditor.general.f1
helpviewer_keywords:
- Data Flow Path Editor dialog box
ms.assetid: 72a9ff1d-3748-41d1-a9b2-63f4a77bba24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71eca61b1454e2e8cb811bbe450f584191ae77b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713387"
---
# <a name="data-flow-path-editor-general-page"></a><span data-ttu-id="82a72-102">Editor percorso flusso di dati (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="82a72-102">Data Flow Path Editor (General Page)</span></span>
  <span data-ttu-id="82a72-103">Utilizzare la finestra di dialogo **Editor percorso flusso di dati** per impostare le proprietà del percorso, visualizzare i metadati delle colonne e gestire i visualizzatori di dati collegati al percorso.</span><span class="sxs-lookup"><span data-stu-id="82a72-103">Use the **Data Flow Path Editor** dialog box to set path properties, view column metadata, and manage the data viewers attached to the path.</span></span>  
  
 <span data-ttu-id="82a72-104">Utilizzare il nodo **Generale** della finestra di dialogo **Editor percorso flusso di dati** per assegnare un nome e una descrizione al percorso e per specificare le opzioni relative all'annotazione del percorso.</span><span class="sxs-lookup"><span data-stu-id="82a72-104">Use the **General** node of the **Data Flow Path Editor** dialog box to name and describe the path, and to specify the options for path annotation.</span></span>  
  
## <a name="options"></a><span data-ttu-id="82a72-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="82a72-105">Options</span></span>  
 <span data-ttu-id="82a72-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="82a72-106">**Name**</span></span>  
 <span data-ttu-id="82a72-107">Consente di digitare un nome univoco per il percorso.</span><span class="sxs-lookup"><span data-stu-id="82a72-107">Provide a unique name for the path.</span></span>  
  
 <span data-ttu-id="82a72-108">**ID**</span><span class="sxs-lookup"><span data-stu-id="82a72-108">**ID**</span></span>  
 <span data-ttu-id="82a72-109">L'identificatore di derivazione del percorso.</span><span class="sxs-lookup"><span data-stu-id="82a72-109">The lineage identifier of the path.</span></span> <span data-ttu-id="82a72-110">Questa proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="82a72-110">This property is read-only.</span></span>  
  
 <span data-ttu-id="82a72-111">**IdentificationString**</span><span class="sxs-lookup"><span data-stu-id="82a72-111">**IdentificationString**</span></span>  
 <span data-ttu-id="82a72-112">Stringa che identifica il percorso.</span><span class="sxs-lookup"><span data-stu-id="82a72-112">The string that identifies the path.</span></span> <span data-ttu-id="82a72-113">Viene generata automaticamente in base al nome immesso sopra.</span><span class="sxs-lookup"><span data-stu-id="82a72-113">Automatically generated from the name entered above.</span></span>  
  
 <span data-ttu-id="82a72-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="82a72-114">**Description**</span></span>  
 <span data-ttu-id="82a72-115">Consente di digitare una descrizione del percorso.</span><span class="sxs-lookup"><span data-stu-id="82a72-115">Describe the path.</span></span>  
  
 <span data-ttu-id="82a72-116">**PathAnnotation**</span><span class="sxs-lookup"><span data-stu-id="82a72-116">**PathAnnotation**</span></span>  
 <span data-ttu-id="82a72-117">Specificare il tipo di annotazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="82a72-117">Specify the type of annotation to use.</span></span> <span data-ttu-id="82a72-118">Selezionare **Never** per disabilitare le annotazioni, **AsNeeded** per abilitare le annotazioni su richiesta, **SourceName** per aggiungere automaticamente le annotazioni utilizzando il valore dell'opzione **SourceName** e **PathName** per aggiungere automaticamente le annotazioni utilizzano il valore della proprietà **Nome** .</span><span class="sxs-lookup"><span data-stu-id="82a72-118">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **SourceName** to automatically annotate using the value of the **SourceName** option, and **PathName** to automatically annotate using the value of the **Name** property.</span></span>  
  
 <span data-ttu-id="82a72-119">**DestinationName**</span><span class="sxs-lookup"><span data-stu-id="82a72-119">**DestinationName**</span></span>  
 <span data-ttu-id="82a72-120">Consente di visualizzare l'input corrispondente alla fine del percorso.</span><span class="sxs-lookup"><span data-stu-id="82a72-120">Displays the input that is the end of the path.</span></span>  
  
 <span data-ttu-id="82a72-121">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="82a72-121">**SourceName**</span></span>  
 <span data-ttu-id="82a72-122">Indica l'output che corrisponde all'inizio del percorso.</span><span class="sxs-lookup"><span data-stu-id="82a72-122">Displays the output that is the start of the path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a72-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82a72-123">See Also</span></span>  
 <span data-ttu-id="82a72-124">[Editor percorso flusso di dati &#40;pagina metadati&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span><span class="sxs-lookup"><span data-stu-id="82a72-124">[Data Flow Path Editor &#40;Metadata Page&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span></span>  
 <span data-ttu-id="82a72-125">[Editor percorso flusso di dati &#40;pagina visualizzatori dati&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span><span class="sxs-lookup"><span data-stu-id="82a72-125">[Data Flow Path Editor &#40;Data Viewers Page&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span></span>  
 <span data-ttu-id="82a72-126">[Flusso di dati](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="82a72-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="82a72-127">Utilizzo di annotazioni nei pacchetti</span><span class="sxs-lookup"><span data-stu-id="82a72-127">Use Annotations in Packages</span></span>](use-annotations-in-packages.md)  
  
  
