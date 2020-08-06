---
title: Proprietà catalogo full-text (pagina tabelle e viste) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.tablesviews.f1
ms.assetid: 2d45fcd2-0f0f-4167-9027-316d6696c106
author: rothja
ms.author: jroth
ms.openlocfilehash: eb4d968af6c550d19fbb8934b5d76a1bd63cb8da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724091"
---
# <a name="full-text-catalog-properties-tables-and-views-page"></a><span data-ttu-id="f510c-102">Proprietà catalogo full-text (pagina Tabelle e viste)</span><span class="sxs-lookup"><span data-stu-id="f510c-102">Full-Text Catalog Properties (Tables and Views Page)</span></span>
  <span data-ttu-id="f510c-103">Utilizzare questa finestra di dialogo per visualizzare o modificare le tabelle e le viste assegnate al catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="f510c-103">Use this dialog page to view or modify the tables and views that are assigned to the full-text catalog.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f510c-104">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="f510c-104">UI element list</span></span>  
 <span data-ttu-id="f510c-105">**Tutti gli oggetti tabella/vista idonei nel database**</span><span class="sxs-lookup"><span data-stu-id="f510c-105">**All eligible table/view objects in this database**</span></span>  
 <span data-ttu-id="f510c-106">Elenca le tabelle e le viste che hanno un indice univoco definito, ma che non fanno già parte del catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="f510c-106">Lists the tables and views that have a unique index defined on them, but are not already a part of the full-text catalog.</span></span> <span data-ttu-id="f510c-107">Per selezionare una tabella o una vista e assegnarla al catalogo, selezionare gli elementi nella casella di riepilogo e premere il pulsante "->".</span><span class="sxs-lookup"><span data-stu-id="f510c-107">To select a table or view and assign it to the catalog, select the items in the list box and press the "->" button.</span></span>  
  
 <span data-ttu-id="f510c-108">**Oggetti tabella/vista assegnati al catalogo**</span><span class="sxs-lookup"><span data-stu-id="f510c-108">**Table/view objects assigned to the catalog**</span></span>  
 <span data-ttu-id="f510c-109">Elenca le tabelle e le viste attualmente assegnate al catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="f510c-109">Lists the tables and views that are currently assigned to the full-text catalog</span></span>  
  
## <a name="selected-object-properties"></a><span data-ttu-id="f510c-110">Proprietà degli oggetti selezionati</span><span class="sxs-lookup"><span data-stu-id="f510c-110">Selected Object Properties</span></span>  
 <span data-ttu-id="f510c-111">**Proprietà degli oggetti selezionati**</span><span class="sxs-lookup"><span data-stu-id="f510c-111">**Selected object properties**</span></span>  
 <span data-ttu-id="f510c-112">Visualizza le proprietà dell'oggetto selezionato nella casella di riepilogo degli oggetti assegnati al catalogo.</span><span class="sxs-lookup"><span data-stu-id="f510c-112">Displays the properties of the selected object in the list box of objects assigned to the catalog.</span></span>  
  
 <span data-ttu-id="f510c-113">**Indice univoco**</span><span class="sxs-lookup"><span data-stu-id="f510c-113">**Unique Index**</span></span>  
 <span data-ttu-id="f510c-114">Elenca gli indici univoci disponibili della tabella o della vista.</span><span class="sxs-lookup"><span data-stu-id="f510c-114">Lists the available unique indexes of the table or view.</span></span>  
  
 <span data-ttu-id="f510c-115">**Tabella abilitata per la funzionalità full-text**</span><span class="sxs-lookup"><span data-stu-id="f510c-115">**Table is full-text enabled**</span></span>  
 <span data-ttu-id="f510c-116">Selezionare questa casella di controllo per abilitare l'indice full-text nella tabella.</span><span class="sxs-lookup"><span data-stu-id="f510c-116">Select this check box to enable the full-text index on the table.</span></span> <span data-ttu-id="f510c-117">Deselezionare la casella di controllo per disabilitare l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="f510c-117">Clear the check box to disable the full-text index.</span></span>  
  
## <a name="eligible-columns-grid"></a><span data-ttu-id="f510c-118">Griglia delle colonne idonee</span><span class="sxs-lookup"><span data-stu-id="f510c-118">Eligible Columns Grid</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f510c-119">**Colonne disponibili**</span><span class="sxs-lookup"><span data-stu-id="f510c-119">**Available Columns**</span></span>|<span data-ttu-id="f510c-120">Visualizza tutte le colonne con indice full-text.</span><span class="sxs-lookup"><span data-stu-id="f510c-120">Displays all the columns that are full-text indexed.</span></span> <span data-ttu-id="f510c-121">Selezionare una casella di controllo per aggiungere una colonna all'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="f510c-121">Select a check box to add a column to the full-text index.</span></span>|  
|<span data-ttu-id="f510c-122">**Lingua per il Word breaker**</span><span class="sxs-lookup"><span data-stu-id="f510c-122">**Language for Word Breaker**</span></span>|<span data-ttu-id="f510c-123">Visualizza la lingua per il word breaker.</span><span class="sxs-lookup"><span data-stu-id="f510c-123">Displays the language of the word breaker.</span></span>|  
|<span data-ttu-id="f510c-124">**Colonna tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="f510c-124">**Data Type Column**</span></span>|<span data-ttu-id="f510c-125">Elenca il nome della colonna nella tabella che contiene il tipo di documento della colonna elencata in **colonne disponibili** se la colonna è una `varbinary(max)` colonna o `image` .</span><span class="sxs-lookup"><span data-stu-id="f510c-125">Lists the name of the column in the table that holds the document type of the column listed in **Available Columns** if the column is a `varbinary(max)` or `image` column.</span></span>|  
|<span data-ttu-id="f510c-126">**Semantica statistica**</span><span class="sxs-lookup"><span data-stu-id="f510c-126">**Statistical Semantics**</span></span>|<span data-ttu-id="f510c-127">Consente di selezionare se abilitare l'indicizzazione semantica per la colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="f510c-127">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="f510c-128">Per altre informazioni, vedere [Ricerca semantica &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f510c-128">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="f510c-129">Se si seleziona una lingua in **Lingua** prima di selezionare **Semantica statistica**e alla lingua selezionata non è associato alcun modello di lingua semantico, la casella di controllo **Semantica statistica** è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f510c-129">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="f510c-130">Se si seleziona **Semantica statistica** prima di selezionare una lingua in **Lingua**, le lingue disponibili nella casella combinata a discesa saranno limitate a quelle per cui è disponibile un modello di lingua semantico.</span><span class="sxs-lookup"><span data-stu-id="f510c-130">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="track-changes"></a><span data-ttu-id="f510c-131">Rilevamento modifiche</span><span class="sxs-lookup"><span data-stu-id="f510c-131">Track Changes</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f510c-132">**Automatic** (Automatica)</span><span class="sxs-lookup"><span data-stu-id="f510c-132">**Automatic**</span></span>|<span data-ttu-id="f510c-133">L'indice full-text viene aggiornato automaticamente in caso di modifica, aggiunta o eliminazione dei dati nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="f510c-133">The full-text index is automatically updated when the data in the underlying table is modified, added, or deleted.</span></span>|  
|<span data-ttu-id="f510c-134">**Manuale**</span><span class="sxs-lookup"><span data-stu-id="f510c-134">**Manual**</span></span>|<span data-ttu-id="f510c-135">Le modifiche, le aggiunte o le eliminazioni dei dati indicizzati vengono rilevate da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f510c-135">When data is modified, added, or deleted in the indexed data, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tracks the changes.</span></span> <span data-ttu-id="f510c-136">Quando il rilevamento delle modifiche è impostato su **Manuale** , le modifiche all'indice non vengono aggiornate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f510c-136">When **Manual** change tracking is in effect, the index is not automatically updated with these changes.</span></span> <span data-ttu-id="f510c-137">Un amministratore può invece applicare manualmente le modifiche utilizzando un' [istruzione ALTER FULLTEXT index... START UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) (istruzione).</span><span class="sxs-lookup"><span data-stu-id="f510c-137">Instead, an administrator can apply the changes manually by using an [ALTER FULLTEXT INDEX ... START UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) statement.</span></span>|  
|<span data-ttu-id="f510c-138">**Non rilevare modifiche**</span><span class="sxs-lookup"><span data-stu-id="f510c-138">**Do not track change**</span></span>|<span data-ttu-id="f510c-139">Quando è impostata questa opzione, le modifiche apportate ai dati indicizzati nel catalogo non vengono registrate.</span><span class="sxs-lookup"><span data-stu-id="f510c-139">With this option in effect, changes to the indexed data in the catalog are not recorded.</span></span> <span data-ttu-id="f510c-140">Un amministratore deve compilare l'indice utilizzando ALTER FULLTEXT INDEX con FULL POPULATION o INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="f510c-140">An administrator must build the index by using ALTER FULLTEXT INDEX with either FULL POPULATION or INCREMENTAL POPULATION.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f510c-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f510c-141">See Also</span></span>  
 <span data-ttu-id="f510c-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f510c-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span></span>  
 <span data-ttu-id="f510c-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f510c-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="f510c-144">Popolamento degli indici full-text</span><span class="sxs-lookup"><span data-stu-id="f510c-144">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
