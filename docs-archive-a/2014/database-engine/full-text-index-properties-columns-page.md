---
title: Proprietà indice full-text (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.columns.f1
ms.assetid: 75e52edb-0d07-4393-9345-8b5af4561e35
author: rothja
ms.author: jroth
ms.openlocfilehash: f947af04463948ef551c6df866d5a306c248c6b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638054"
---
# <a name="full-text-index-properties-columns-page"></a><span data-ttu-id="af2c6-102">Proprietà indice full-text (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="af2c6-102">Full-Text Index Properties (Columns Page)</span></span>
  <span data-ttu-id="af2c6-103">**Per visualizzare o modificare le proprietà di un indice full-text**</span><span class="sxs-lookup"><span data-stu-id="af2c6-103">**To view or change the properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="af2c6-104">Gestione di indici full-text.</span><span class="sxs-lookup"><span data-stu-id="af2c6-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="af2c6-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="af2c6-105">UI element list</span></span>  
 <span data-ttu-id="af2c6-106">**Indice univoco**</span><span class="sxs-lookup"><span data-stu-id="af2c6-106">**Unique index**</span></span>  
 <span data-ttu-id="af2c6-107">Selezionare un indice dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="af2c6-107">Select an index from the drop down list.</span></span> <span data-ttu-id="af2c6-108">L'indice deve essere univoco, a colonna singola, che non ammette valori Null.</span><span class="sxs-lookup"><span data-stu-id="af2c6-108">The index must be a single-key-column, unique, non-nullable index.</span></span>  
  
 <span data-ttu-id="af2c6-109">**Selezionare le colonne idonee per l'indicizzazione full-text**</span><span class="sxs-lookup"><span data-stu-id="af2c6-109">**Select the eligible columns that will be full-text indexed**</span></span>  
 <span data-ttu-id="af2c6-110">Nella griglia vengono visualizzate le colonne della tabella disponibili per l'indice full-text corrente.</span><span class="sxs-lookup"><span data-stu-id="af2c6-110">The grid displays the table columns that are available for this full-text index.</span></span> <span data-ttu-id="af2c6-111">Le colonne con indicizzazione full-text sono selezionate.</span><span class="sxs-lookup"><span data-stu-id="af2c6-111">Columns that are currently full-text indexed are checked.</span></span> <span data-ttu-id="af2c6-112">Se si desidera, è possibile selezionare colonne aggiuntive cui applicare l'indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="af2c6-112">Optionally, you can check additional columns that you want to be full-text indexed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af2c6-113">Prima di fare clic su OK, verificare che sia selezionata almeno una colonna.</span><span class="sxs-lookup"><span data-stu-id="af2c6-113">Ensure that at least one column is checked before you click OK.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af2c6-114">**Colonne disponibili**</span><span class="sxs-lookup"><span data-stu-id="af2c6-114">**Available Columns**</span></span>|<span data-ttu-id="af2c6-115">Nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="af2c6-115">The column name.</span></span>|  
|<span data-ttu-id="af2c6-116">**Lingua per il Word breaker**</span><span class="sxs-lookup"><span data-stu-id="af2c6-116">**Language for Word Breaker**</span></span>|<span data-ttu-id="af2c6-117">Lingua i cui word breaker e stemmer eseguono l'analisi linguistica su tutti i dati con indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="af2c6-117">The language whose word breakers and stemmers perform linguistic analysis on all full-text indexed data.</span></span><br /><br /> <span data-ttu-id="af2c6-118">Per ulteriori informazioni, vedere [configurare e gestire Word breaker e stemmer per la ricerca](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) e [scegliere una lingua durante la creazione di un indice full-text](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span><span class="sxs-lookup"><span data-stu-id="af2c6-118">For more information, see [Configure and Manage Word Breakers and Stemmers for Search](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) and [Choose a Language When Creating a Full-Text Index](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span></span>|  
|<span data-ttu-id="af2c6-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="af2c6-119">**Type**</span></span>|<span data-ttu-id="af2c6-120">Nome della colonna di tabella contenente il tipo di documento della colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="af2c6-120">The name of the table column that holds the document type of the selected column.</span></span> <span data-ttu-id="af2c6-121">Questa proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="af2c6-121">This is a read-only property.</span></span>|  
|<span data-ttu-id="af2c6-122">**Semantica statistica**</span><span class="sxs-lookup"><span data-stu-id="af2c6-122">**Statistical Semantics**</span></span>|<span data-ttu-id="af2c6-123">Consente di selezionare se abilitare l'indicizzazione semantica per la colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="af2c6-123">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="af2c6-124">Per altre informazioni, vedere [Ricerca semantica &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="af2c6-124">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="af2c6-125">Se si seleziona una lingua in **Lingua** prima di selezionare **Semantica statistica**e alla lingua selezionata non è associato alcun modello di lingua semantico, la casella di controllo **Semantica statistica** è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="af2c6-125">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="af2c6-126">Se si seleziona **Semantica statistica** prima di selezionare una lingua in **Lingua**, le lingue disponibili nella casella combinata a discesa saranno limitate a quelle per cui è disponibile un modello di lingua semantico.</span><span class="sxs-lookup"><span data-stu-id="af2c6-126">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af2c6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af2c6-127">See Also</span></span>  
 [<span data-ttu-id="af2c6-128">Popolamento degli indici full-text</span><span class="sxs-lookup"><span data-stu-id="af2c6-128">Populate Full-Text Indexes</span></span>](../relational-databases/search/populate-full-text-indexes.md)  
  
  
