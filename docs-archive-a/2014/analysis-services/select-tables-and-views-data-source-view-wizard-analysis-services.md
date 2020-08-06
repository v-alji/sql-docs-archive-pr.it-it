---
title: Selezione tabelle e viste (creazione guidata vista origine dati) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.selecttablesandviews.f1
ms.assetid: ea7d1232-f213-46e9-90d9-0fd616ca003d
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac7159255ef526d871ed8906fc873d9f16d2eb64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723152"
---
# <a name="select-tables-and-views-data-source-view-wizard-analysis-services"></a><span data-ttu-id="7faab-102">Selezione tabelle e viste (Creazione guidata vista origine dati) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="7faab-102">Select Tables and Views (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="7faab-103">La pagina **Selezione tabelle e viste** consente di selezionare le tabelle o le viste dall'origine dati da includere nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="7faab-103">Use the **Select Tables and Views** page to select the tables or views from the data source that you want to include in the data source view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7faab-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7faab-104">Options</span></span>  
 <span data-ttu-id="7faab-105">**Available objects**</span><span class="sxs-lookup"><span data-stu-id="7faab-105">**Available objects**</span></span>  
 <span data-ttu-id="7faab-106">Elenca le tabelle e le viste nello schema dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="7faab-106">Lists the tables and views in the data source schema.</span></span> <span data-ttu-id="7faab-107">Se è presente più di uno schema, il nome dello schema viene anteposto al nome dei singoli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7faab-107">The schema name prefixes the name of every object if more than one schema is listed.</span></span> <span data-ttu-id="7faab-108">Se è presente un solo schema, ai nomi degli oggetti non verrà anteposto il nome dello schema.</span><span class="sxs-lookup"><span data-stu-id="7faab-108">If only one schema is listed, the schema's name does not prefix the object names.</span></span>  
  
 <span data-ttu-id="7faab-109">Per riordinare l'elenco in ordine crescente o decrescente, fare clic su **Nome** o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="7faab-109">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="7faab-110">**Included objects**</span><span class="sxs-lookup"><span data-stu-id="7faab-110">**Included objects**</span></span>  
 <span data-ttu-id="7faab-111">Elenca le tabelle e le viste nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="7faab-111">Lists the tables and views to include in the data source view.</span></span>  
  
 <span data-ttu-id="7faab-112">Per riordinare l'elenco in ordine crescente o decrescente, fare clic su **Nome** o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="7faab-112">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="7faab-113">**Filter**</span><span class="sxs-lookup"><span data-stu-id="7faab-113">**Filter**</span></span>  
 <span data-ttu-id="7faab-114">Filtra gli oggetti elencati in **Oggetti disponibili**.</span><span class="sxs-lookup"><span data-stu-id="7faab-114">Filters the objects listed under **Available objects**.</span></span> <span data-ttu-id="7faab-115">Digitare una stringa e quindi fare clic su **Filtro** per elencare solo i nomi che contengono la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="7faab-115">Type a string, and then click **Filter** to list only the names that contain a specified string.</span></span> <span data-ttu-id="7faab-116">Per ricercare una stringa esatta di caratteri, racchiudere la stringa tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="7faab-116">To find an exact string of characters, enclose the string between double quotation marks.</span></span> <span data-ttu-id="7faab-117">Il filtro non supporta la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="7faab-117">The filter is not case sensitive.</span></span>  
  
 <span data-ttu-id="7faab-118">È possibile includere i caratteri jolly inclusi nella tabella seguente in qualsiasi punto della stringa di filtro.</span><span class="sxs-lookup"><span data-stu-id="7faab-118">You can include the wildcard characters listed in the following table anywhere in the filter string.</span></span>  
  
|<span data-ttu-id="7faab-119">Carattere jolly</span><span class="sxs-lookup"><span data-stu-id="7faab-119">Wildcard character</span></span>|<span data-ttu-id="7faab-120">Valore</span><span class="sxs-lookup"><span data-stu-id="7faab-120">Value</span></span>|  
|------------------------|-----------|  
|**\***|<span data-ttu-id="7faab-121">Qualsiasi stringa di caratteri</span><span class="sxs-lookup"><span data-stu-id="7faab-121">Any string of characters</span></span>|  
|**%**|<span data-ttu-id="7faab-122">Qualsiasi stringa di caratteri</span><span class="sxs-lookup"><span data-stu-id="7faab-122">Any string of characters</span></span>|  
|<span data-ttu-id="7faab-123">**?**</span><span class="sxs-lookup"><span data-stu-id="7faab-123">**?**</span></span>|<span data-ttu-id="7faab-124">Un singolo carattere</span><span class="sxs-lookup"><span data-stu-id="7faab-124">A single character</span></span>|  
|<span data-ttu-id="7faab-125">**"** *stringa* **"**</span><span class="sxs-lookup"><span data-stu-id="7faab-125">**"** *string* **"**</span></span>|<span data-ttu-id="7faab-126">Una stringa letterale di caratteri.</span><span class="sxs-lookup"><span data-stu-id="7faab-126">A literal string of characters.</span></span> <span data-ttu-id="7faab-127">Questo carattere jolly corrisponderà a qualsiasi sottostringa nel nome dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7faab-127">This wildcard character will match any substring within the object name.</span></span>|  
  
 <span data-ttu-id="7faab-128">**Show system objects**</span><span class="sxs-lookup"><span data-stu-id="7faab-128">**Show system objects**</span></span>  
 <span data-ttu-id="7faab-129">Mostra gli oggetti di sistema in **Oggetti disponibili**.</span><span class="sxs-lookup"><span data-stu-id="7faab-129">Displays system objects under **Available objects**.</span></span> <span data-ttu-id="7faab-130">Questa opzione è disponibile solo se il provider dell'origine dei dati espone gli oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="7faab-130">This option is available only if the data source provider exposes system objects.</span></span> <span data-ttu-id="7faab-131">Se si rimuove un oggetto di sistema dall'elenco **Oggetti inclusi** , questa opzione viene automaticamente selezionata.</span><span class="sxs-lookup"><span data-stu-id="7faab-131">Removing a system object from the **Included objects** list automatically selects this option.</span></span>  
  
 <span data-ttu-id="7faab-132">**Add related tables**</span><span class="sxs-lookup"><span data-stu-id="7faab-132">**Add related tables**</span></span>  
 <span data-ttu-id="7faab-133">Aggiunge tutte le tabelle correlate a quelle elencate in **Oggetti inclusi**.</span><span class="sxs-lookup"><span data-stu-id="7faab-133">Adds all the tables that are related to those listed under **Included objects**.</span></span> <span data-ttu-id="7faab-134">Questa opzione non consente di aggiungere visualizzazioni,</span><span class="sxs-lookup"><span data-stu-id="7faab-134">This option does not add views.</span></span> <span data-ttu-id="7faab-135">bensì permette di aggiungere tabelle partizionate.</span><span class="sxs-lookup"><span data-stu-id="7faab-135">However, this option does add partitioned tables.</span></span> <span data-ttu-id="7faab-136">Se si seleziona un criterio di corrispondenza dei nomi nella pagina **Corrispondenza nomi** della procedura guidata, questa opzione include anche le tabelle logicamente correlate in base al criterio selezionato.</span><span class="sxs-lookup"><span data-stu-id="7faab-136">If you select name-matching criteria on the **Name Matching** page of the wizard, this option also includes logically related tables according to the criteria you select.</span></span> <span data-ttu-id="7faab-137">Vengono inoltre incluse le tabelle correlate a nuove tabelle correlate aggiunte e quelle che presentano una struttura identica alla tabella originale.</span><span class="sxs-lookup"><span data-stu-id="7faab-137">Tables are also included if they are related to the newly added related tables, and if they have an identical structure to the original table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7faab-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7faab-138">See Also</span></span>  
 <span data-ttu-id="7faab-139">[Guida sensibile al contesto della creazione guidata vista origine dati &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="7faab-139">[Data Source View Wizard F1 Help &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span></span>  
 [<span data-ttu-id="7faab-140">Viste origine dati in modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="7faab-140">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
