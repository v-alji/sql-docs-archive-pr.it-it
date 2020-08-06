---
title: Proprietà dell'origine OData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4fde5bb0-6d78-4ec4-8f0b-67f91c53fe99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8139f79ed595ca3e6204f96823f6bc95e6fb40df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724820"
---
# <a name="odata-source-properties"></a><span data-ttu-id="f06e8-102">Proprietà dell'origine OData</span><span class="sxs-lookup"><span data-stu-id="f06e8-102">OData Source Properties</span></span>
  <span data-ttu-id="f06e8-103">Quando si fa clic con il pulsante destro del mouse su **Origine OData** nel flusso di dati e si sceglie **Proprietà**, vengono visualizzate le proprietà per il componente **Origine OData** nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="f06e8-103">When you right-click **OData Source** in the data flow and click **Properties**, you will see properties for the **OData Source** component in the **Properties** window.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f06e8-104">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f06e8-104">Property</span></span>|<span data-ttu-id="f06e8-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f06e8-105">Description</span></span>|  
|<span data-ttu-id="f06e8-106">CollectionName</span><span class="sxs-lookup"><span data-stu-id="f06e8-106">CollectionName</span></span>|<span data-ttu-id="f06e8-107">Nome della raccolta che si desidera recuperare dal servizio OData.</span><span class="sxs-lookup"><span data-stu-id="f06e8-107">Name of the collection you wish to retrieve from the OData service.</span></span> <span data-ttu-id="f06e8-108">La proprietà **CollectionName** viene utilizzata quando **UseResourcePath** è False.</span><span class="sxs-lookup"><span data-stu-id="f06e8-108">The **CollectionName** property is used when **UseResourcePath** is False.</span></span><br /><br /> <span data-ttu-id="f06e8-109">Questa proprietà ammette le espressioni e consente l'impostazione del valore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f06e8-109">This property is expression-able, allowing the value to be set at runtime.</span></span> <span data-ttu-id="f06e8-110">Tuttavia, se i metadati della raccolta non corrispondono a quelli utilizzati in fase di progettazione, si verifica un errore di convalida e l'esecuzione del flusso di dati non viene completata.</span><span class="sxs-lookup"><span data-stu-id="f06e8-110">However, if the metadata of the collection does not match the metadata that was used at design time, a validation error will occur, causing the data flow execution to fail.</span></span>|  
|<span data-ttu-id="f06e8-111">DefaultStringLength</span><span class="sxs-lookup"><span data-stu-id="f06e8-111">DefaultStringLength</span></span>|<span data-ttu-id="f06e8-112">Con questo valore viene specificata la lunghezza predefinita per le colonne stringa che sono prive della lunghezza massima.</span><span class="sxs-lookup"><span data-stu-id="f06e8-112">This value specifies default length for string columns that have no max length.</span></span><br /><br /> <span data-ttu-id="f06e8-113">**Valore predefinito:** 4000</span><span class="sxs-lookup"><span data-stu-id="f06e8-113">**Default:** 4000</span></span>|  
|<span data-ttu-id="f06e8-114">Query</span><span class="sxs-lookup"><span data-stu-id="f06e8-114">Query</span></span>|<span data-ttu-id="f06e8-115">Parametri della query OData.</span><span class="sxs-lookup"><span data-stu-id="f06e8-115">The OData query parameters.</span></span> <span data-ttu-id="f06e8-116">Questa proprietà ammette le espressioni e può essere impostata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f06e8-116">This property is expression-able and can be set at runtime.</span></span>|  
|<span data-ttu-id="f06e8-117">ResourcePath</span><span class="sxs-lookup"><span data-stu-id="f06e8-117">ResourcePath</span></span>|<span data-ttu-id="f06e8-118">Utilizzare questa proprietà quando è necessario specificare un percorso completo della risorsa, anziché selezionare semplicemente il nome di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="f06e8-118">Use this property when you need to specify a full resource path, rather than just selecting a collection name.</span></span> <span data-ttu-id="f06e8-119">Questa proprietà viene utilizzata quando **UseResourcePath** è True.</span><span class="sxs-lookup"><span data-stu-id="f06e8-119">This property is used when **UseResourcePath** is True.</span></span>|  
|<span data-ttu-id="f06e8-120">UseResourcePath</span><span class="sxs-lookup"><span data-stu-id="f06e8-120">UseResourcePath</span></span>|<span data-ttu-id="f06e8-121">Quando impostato su True, il valore di **ResourcePath** viene aggiunto all'URL di base per determinare il percorso del feed OData.</span><span class="sxs-lookup"><span data-stu-id="f06e8-121">When set to True, the **ResourcePath** value is appended to the base URL to determine the OData feed location.</span></span> <span data-ttu-id="f06e8-122">Quando impostato su False, viene utilizzato il valore di **CollectionName** .</span><span class="sxs-lookup"><span data-stu-id="f06e8-122">When set to False, the **CollectionName** value is used.</span></span><br /><br /> <span data-ttu-id="f06e8-123">**Impostazione predefinita:** False</span><span class="sxs-lookup"><span data-stu-id="f06e8-123">**Default:** False</span></span>|  
  
  
