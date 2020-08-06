---
title: Proprietà delle query (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69636
- vdt.ppg.querydesigner.query
ms.assetid: 07495669-6ed5-4004-904e-aae1230be5e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3c8adfb50e15113228afe8b48218f341f19084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713680"
---
# <a name="query-properties-visual-database-tools"></a><span data-ttu-id="4ae35-102">Proprietà delle query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4ae35-102">Query Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="4ae35-103">Queste proprietà vengono visualizzate nella finestra Proprietà quando in Progettazione query e Progettazione viste è aperta una query.</span><span class="sxs-lookup"><span data-stu-id="4ae35-103">These properties appear in the Properties window when you have a query open in Query and View Designer.</span></span> <span data-ttu-id="4ae35-104">Se non specificato diversamente, tali proprietà possono essere modificate nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ae35-104">Unless otherwise noted, you can edit these properties in the Properties window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ae35-105">Le proprietà in questo argomento sono ordinate per categoria anziché alfabeticamente.</span><span class="sxs-lookup"><span data-stu-id="4ae35-105">The properties in this topic are ordered by category, rather than alphabetically.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4ae35-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4ae35-106">Options</span></span>  
 <span data-ttu-id="4ae35-107">**Categoria Identità**</span><span class="sxs-lookup"><span data-stu-id="4ae35-107">**Identity Category**</span></span>  
 <span data-ttu-id="4ae35-108">Viene espansa per visualizzare la proprietà **Nome** .</span><span class="sxs-lookup"><span data-stu-id="4ae35-108">Expand to show the **Name** property.</span></span>  
  
 <span data-ttu-id="4ae35-109">**Nome**</span><span class="sxs-lookup"><span data-stu-id="4ae35-109">**Name**</span></span>  
 <span data-ttu-id="4ae35-110">Visualizza il nome della query corrente.</span><span class="sxs-lookup"><span data-stu-id="4ae35-110">Shows the name of the current query.</span></span> <span data-ttu-id="4ae35-111">Non è possibile modificarlo in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ae35-111">Cannot be changed in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="4ae35-112">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="4ae35-112">**Database Name**</span></span>  
 <span data-ttu-id="4ae35-113">Visualizza il nome dell'origine dati della tabella selezionata</span><span class="sxs-lookup"><span data-stu-id="4ae35-113">Shows the name of the data source for the selected table.</span></span>  
  
 <span data-ttu-id="4ae35-114">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="4ae35-114">**Server Name**</span></span>  
 <span data-ttu-id="4ae35-115">Visualizza il nome del server dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4ae35-115">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="4ae35-116">**Categoria Progettazione query**</span><span class="sxs-lookup"><span data-stu-id="4ae35-116">**Query Designer Category**</span></span>  
 <span data-ttu-id="4ae35-117">Viene espansa per visualizzare le proprietà rimanenti.</span><span class="sxs-lookup"><span data-stu-id="4ae35-117">Expands to show the remaining properties.</span></span>  
  
 <span data-ttu-id="4ae35-118">**Tabella di destinazione**</span><span class="sxs-lookup"><span data-stu-id="4ae35-118">**Destination table**</span></span>  
 <span data-ttu-id="4ae35-119">Specifica il nome della tabella in cui si stanno inserendo dati.</span><span class="sxs-lookup"><span data-stu-id="4ae35-119">Specify the name of the table into which you are inserting data.</span></span> <span data-ttu-id="4ae35-120">Questo elenco viene visualizzato se si sta creando una query INSERT o MAKE TABLE.</span><span class="sxs-lookup"><span data-stu-id="4ae35-120">This list appears if you are creating an INSERT query or MAKE TABLE query.</span></span> <span data-ttu-id="4ae35-121">Per una query di inserimento, selezionare un nome di tabella nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4ae35-121">For an INSERT query, select a table name from the list.</span></span>  
  
 <span data-ttu-id="4ae35-122">Per una query di creazione tabella (MAKE TABLE), specificare il nome della nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="4ae35-122">For a MAKE TABLE query, type the name of the new table.</span></span> <span data-ttu-id="4ae35-123">Per creare una tabella di destinazione in un'altra origine dati, specificare un nome di tabella completo che comprenda il nome dell'origine dati di destinazione, il proprietario (se necessario) e il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="4ae35-123">To create a destination table in another data source, specify a fully qualified table name, including the name of the target data source, the owner (if required), and the name of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ae35-124">Progettazione query non consente di verificare se il nome è già in uso o se l'utente dispone dell'autorizzazione necessaria per creare la tabella.</span><span class="sxs-lookup"><span data-stu-id="4ae35-124">Query Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
 <span data-ttu-id="4ae35-125">**Valori DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="4ae35-125">**Distinct values**</span></span>  
 <span data-ttu-id="4ae35-126">Consente di specificare che nella query verranno esclusi i duplicati dal set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4ae35-126">Specify that the query will filter out duplicates in the result set.</span></span> <span data-ttu-id="4ae35-127">Questa opzione risulta utile quando si utilizzano solo alcune colonne della tabella o delle tabelle e tali colonne potrebbero contenere valori duplicati. L'opzione è utile inoltre quando dal processo di unione di due o più tabelle vengono generate righe duplicate nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4ae35-127">This option is useful when you are using only some of the columns from the table or tables and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="4ae35-128">Selezionare questa opzione equivale a inserire la parola DISTINCT nell'istruzione del riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="4ae35-128">Choosing this option is equivalent to inserting the word DISTINCT into the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="4ae35-129">**Estensione GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="4ae35-129">**GROUP BY Extension**</span></span>  
 <span data-ttu-id="4ae35-130">Specifica che sono disponibili opzioni aggiuntive per le query basate su query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="4ae35-130">Specify that additional options for queries based on aggregate queries are available.</span></span> <span data-ttu-id="4ae35-131">(si applica solo a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="4ae35-131">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="4ae35-132">**Tutte le colonne**</span><span class="sxs-lookup"><span data-stu-id="4ae35-132">**Output All Columns**</span></span>  
 <span data-ttu-id="4ae35-133">Specifica che tutte le colonne di tutte le tabelle nella query corrente saranno presenti nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4ae35-133">Specify that all columns from all tables in the current query will be in the result set.</span></span> <span data-ttu-id="4ae35-134">Selezionare questa opzione equivale a specificare un asterisco (\*) al posto dei singoli nomi di colonne dopo la parola chiave SELECT nell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="4ae35-134">Choosing this option is equivalent to specifying an asterisk (\*) in place of individual column names after the SELECT keyword in the SQL statement.</span></span>  
  
 <span data-ttu-id="4ae35-135">**Elenco parametri query**</span><span class="sxs-lookup"><span data-stu-id="4ae35-135">**Query Parameter List**</span></span>  
 <span data-ttu-id="4ae35-136">Visualizza i parametri della query.</span><span class="sxs-lookup"><span data-stu-id="4ae35-136">Shows query parameters.</span></span> <span data-ttu-id="4ae35-137">Per modificarli, fare clic sulla proprietà e quindi sui puntini di sospensione **(...)** a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ae35-137">To edit the parameters click the property and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="4ae35-138">(si applica solo a OLE DB generico).</span><span class="sxs-lookup"><span data-stu-id="4ae35-138">(Applies only to generic OLE DB.)</span></span>  
  
 <span data-ttu-id="4ae35-139">**Commento SQL**</span><span class="sxs-lookup"><span data-stu-id="4ae35-139">**SQL Comment**</span></span>  
 <span data-ttu-id="4ae35-140">Visualizza una descrizione delle istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="4ae35-140">Shows a description of the SQL statements.</span></span> <span data-ttu-id="4ae35-141">Per visualizzare la descrizione completa o modificarla, fare clic su di essa, quindi sui puntini di sospensione **(...)** a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ae35-141">To see the entire description or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="4ae35-142">Nei commenti è possibile specificare ad esempio chi utilizza la query e quando</span><span class="sxs-lookup"><span data-stu-id="4ae35-142">Your comments can include information such as who uses the query and when they use it.</span></span> <span data-ttu-id="4ae35-143">(si applica solo a database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="4ae35-143">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 databases or later.)</span></span>  
  
 <span data-ttu-id="4ae35-144">**Categoria Specifica Top**</span><span class="sxs-lookup"><span data-stu-id="4ae35-144">**Top Specification Category**</span></span>  
 <span data-ttu-id="4ae35-145">Viene espansa per visualizzare le proprietà relative alle proprietà **In alto**, **Percentuale**, **Espressione**e **Con valori equivalenti** .</span><span class="sxs-lookup"><span data-stu-id="4ae35-145">Expand to show properties for the **Top**, **Percent**, **Expression**, and **With Ties** properties.</span></span>  
  
 <span data-ttu-id="4ae35-146">**(In alto)**</span><span class="sxs-lookup"><span data-stu-id="4ae35-146">**(Top)**</span></span>  
 <span data-ttu-id="4ae35-147">Specifica che la query includerà una clausola TOP che restituisce soltanto le prime *n* righe o solo il primo *n* percento delle righe del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4ae35-147">Specify hat the query will include a TOP clause, which returns only the first *n* rows or first *n* percentage of rows in the result set.</span></span> <span data-ttu-id="4ae35-148">Per impostazione predefinita, la query restituisce le prime 10 righe del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4ae35-148">The default is that the query returns the first 10 rows in the result set.</span></span>  
  
 <span data-ttu-id="4ae35-149">Utilizzare questa casella per cambiare il numero di righe restituite o specificare una percentuale diversa</span><span class="sxs-lookup"><span data-stu-id="4ae35-149">Use this box to change the number of rows to return or to specify a different percentage.</span></span> <span data-ttu-id="4ae35-150">(si applica solo a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="4ae35-150">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later.)</span></span>  
  
 <span data-ttu-id="4ae35-151">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="4ae35-151">**Expression**</span></span>  
 <span data-ttu-id="4ae35-152">Specifica il numero o la percentuale delle righe che verranno restituite dalla query.</span><span class="sxs-lookup"><span data-stu-id="4ae35-152">Specify the number or percentage of rows that the query will return.</span></span> <span data-ttu-id="4ae35-153">Se si imposta **Percentuale** su Sì, il numero indicherà la percentuale delle righe che verranno restituite dalla query, mentre se si imposta **Percentuale** su No, il valore rappresenterà il numero di righe da restituire</span><span class="sxs-lookup"><span data-stu-id="4ae35-153">If you set **Percent** to Yes, this number is the percentage of rows the query will return; if you set **Percent** to No, it represents the number of rows to return.</span></span> <span data-ttu-id="4ae35-154">(si applica solo a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="4ae35-154">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="4ae35-155">**Percentuale**</span><span class="sxs-lookup"><span data-stu-id="4ae35-155">**Percent**</span></span>  
 <span data-ttu-id="4ae35-156">Specifica che la query restituirà soltanto il primo *n* percento delle righe del set di risultati</span><span class="sxs-lookup"><span data-stu-id="4ae35-156">Specify that the query will return only the first *n* percent of rows in the result set.</span></span> <span data-ttu-id="4ae35-157">(si applica solo a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="4ae35-157">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="4ae35-158">**Con valori equivalenti**</span><span class="sxs-lookup"><span data-stu-id="4ae35-158">**With Ties**</span></span>  
 <span data-ttu-id="4ae35-159">Specifica che la vista includerà una clausola WITH TIES.</span><span class="sxs-lookup"><span data-stu-id="4ae35-159">Specify that the view will include a WITH TIES clause.</span></span> <span data-ttu-id="4ae35-160">WITH TIES è utile se nella vista sono incluse anche una clausola ORDER BY e una clausola TOP basata sulla percentuale.</span><span class="sxs-lookup"><span data-stu-id="4ae35-160">WITH TIES is useful if a view includes an ORDER BY clause and a TOP clause based on percentage.</span></span> <span data-ttu-id="4ae35-161">Se questa opzione è impostata e la percentuale limite specificata cade all'interno di un set di righe con valori identici nella clausola ORDER BY, la vista verrà estesa oltre tale percentuale fino a includere tutte queste righe</span><span class="sxs-lookup"><span data-stu-id="4ae35-161">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the ORDER BY clause, the view is extended to include all such rows.</span></span> <span data-ttu-id="4ae35-162">(si applica solo a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="4ae35-162">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae35-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ae35-163">See Also</span></span>  
 <span data-ttu-id="4ae35-164">[Esecuzione di query con parametri &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4ae35-164">[Query with Parameters &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4ae35-165">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4ae35-165">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
