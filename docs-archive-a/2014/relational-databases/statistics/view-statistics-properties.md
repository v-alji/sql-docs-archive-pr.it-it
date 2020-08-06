---
title: Visualizzare le proprietà delle statistiche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.details.f1
helpviewer_keywords:
- viewing statistics properties
- statistics [SQL Server], viewing properties
ms.assetid: 0eaa2101-006e-4015-9979-3468b50e0aaa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63cabc5d8844982604993acac6a791317ee36925
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636615"
---
# <a name="view-statistics-properties"></a><span data-ttu-id="301a6-102">Visualizzare le proprietà delle statistiche</span><span class="sxs-lookup"><span data-stu-id="301a6-102">View Statistics Properties</span></span>
  <span data-ttu-id="301a6-103">È possibile visualizzare le statistiche di ottimizzazione delle query correnti per una tabella o una vista indicizzata in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="301a6-103">You can display current query optimization statistics for a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="301a6-104">L'oggetto statistiche include un'intestazione con metadati relativi alle statistiche, un istogramma con la distribuzione dei valori nella prima colonna chiave dell'oggetto stesso e un vettore di densità per misurare la correlazione tra colonne.</span><span class="sxs-lookup"><span data-stu-id="301a6-104">Statistics objects include a header with metadata about the statistics, a histogram with the distribution of values in the first key column of the statistics object, and a density vector to measure cross-column correlation.</span></span> <span data-ttu-id="301a6-105">Per altre informazioni sugli istogrammi e sui vettori di densità, vedere [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="301a6-105">For more information about histograms and density vectors, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql)</span></span>  
  
 <span data-ttu-id="301a6-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="301a6-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="301a6-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="301a6-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="301a6-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="301a6-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="301a6-109">**Visualizzare le proprietà delle statistiche tramite:**</span><span class="sxs-lookup"><span data-stu-id="301a6-109">**To view statistics properties, using:**</span></span>  
  
     [<span data-ttu-id="301a6-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="301a6-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="301a6-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="301a6-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="301a6-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="301a6-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="301a6-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="301a6-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="301a6-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="301a6-114">Permissions</span></span>  
 <span data-ttu-id="301a6-115">Per visualizzare l'oggetto statistiche, l'utente deve essere il proprietario della tabella oppure un membro del ruolo predefinito del server `sysadmin` o del ruolo predefinito del database `db_owner` o `db_ddladmin`.</span><span class="sxs-lookup"><span data-stu-id="301a6-115">In order to view the statistics object, the user must own the table or the user must be a member of the `sysadmin` fixed server role, the `db_owner` fixed database role, or the `db_ddladmin` fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="301a6-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="301a6-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="301a6-117">Per visualizzare le proprietà delle statistiche</span><span class="sxs-lookup"><span data-stu-id="301a6-117">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="301a6-118">In **Esplora oggetti**fare clic sul segno più per espandere il database in cui si desidera creare una nuova statistica.</span><span class="sxs-lookup"><span data-stu-id="301a6-118">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="301a6-119">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="301a6-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="301a6-120">Fare clic sul segno più per espandere la tabella in cui verranno visualizzate le proprietà della statistica.</span><span class="sxs-lookup"><span data-stu-id="301a6-120">Click the plus sign to expand the table in which you want to view the statistic's properties.</span></span>  
  
4.  <span data-ttu-id="301a6-121">Fare clic sul segno più per espandere la cartella **Statistiche** .</span><span class="sxs-lookup"><span data-stu-id="301a6-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="301a6-122">Fare clic con il pulsante destro del mouse sull'oggetto statistiche di cui si vogliono visualizzare le proprietà e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="301a6-122">Right-click the Statistics object of which you want to view the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="301a6-123">Nella finestra di dialogo **Proprietà statistiche -** _nome_statistiche_ selezionare **Dettagli** nel riquadro **Seleziona una pagina**.</span><span class="sxs-lookup"><span data-stu-id="301a6-123">In the **Statistics Properties -** _statistics_name_ dialog box, in the **Select a page** pane, select **Details**.</span></span>  
  
     <span data-ttu-id="301a6-124">Nella pagina **Dettagli** della finestra di dialogo **Proprietà statistiche -** _nome_statistiche_ vengono visualizzate le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="301a6-124">The following properties show on the **Details** page in the **Statistics Properties -** _statistics_name_ dialog box.</span></span>  
  
     <span data-ttu-id="301a6-125">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="301a6-125">**Table Name**</span></span>  
     <span data-ttu-id="301a6-126">Consente di visualizzare il nome della tabella descritta dalle statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-126">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="301a6-127">**Nome statistiche**</span><span class="sxs-lookup"><span data-stu-id="301a6-127">**Statistics Name**</span></span>  
     <span data-ttu-id="301a6-128">Consente di visualizzare il nome dell'oggetto di database in cui sono archiviate le statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-128">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="301a6-129">**Statistiche per l'indice nome_statistiche**</span><span class="sxs-lookup"><span data-stu-id="301a6-129">**Statistics for INDEXstatistics_name**</span></span>  
     <span data-ttu-id="301a6-130">Questa casella di testo consente di visualizzare le proprietà restituite dall'oggetto statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-130">This text box shows the properties returned from the statistics object.</span></span> <span data-ttu-id="301a6-131">Queste proprietà sono divise in tre sezioni: Stats Header, Density Vector, and Histogram (Intestazione statistiche, Vettore di densità e Istogramma).</span><span class="sxs-lookup"><span data-stu-id="301a6-131">This properties are divided into three sections: Stats Header, Density Vector, and Histogram.</span></span>  
  
     <span data-ttu-id="301a6-132">Tramite le informazioni seguenti vengono descritte le colonne restituite nel set di risultati per l'intestazione delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-132">The following information describes the columns returned in the result set for the Stats Header.</span></span>  
  
     <span data-ttu-id="301a6-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="301a6-133">**Name**</span></span>  
     <span data-ttu-id="301a6-134">Nome dell'oggetto statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-134">Name of the statistics object.</span></span>  
  
     <span data-ttu-id="301a6-135">**Aggiornato**</span><span class="sxs-lookup"><span data-stu-id="301a6-135">**Updated**</span></span>  
     <span data-ttu-id="301a6-136">Data e ora dell'ultimo aggiornamento delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-136">Date and time the statistics were last updated.</span></span>  
  
     <span data-ttu-id="301a6-137">**prime righe**</span><span class="sxs-lookup"><span data-stu-id="301a6-137">**Rows**</span></span>  
     <span data-ttu-id="301a6-138">Numero totale di righe della tabella o della vista indicizzata al momento dell'ultimo aggiornamento delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-138">Total number of rows in the table or indexed view when the statistics were last updated.</span></span> <span data-ttu-id="301a6-139">Se le statistiche vengono filtrate o corrispondono a un indice filtrato, il numero di righe potrebbe essere inferiore al numero di righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="301a6-139">If the statistics are filtered or correspond to a filtered index, the number of rows might be less than the number of rows in the table.</span></span>  
  
     <span data-ttu-id="301a6-140">**Rows Sampled**</span><span class="sxs-lookup"><span data-stu-id="301a6-140">**Rows Sampled**</span></span>  
     <span data-ttu-id="301a6-141">Numero totale di righe campionate per i calcoli statistici.</span><span class="sxs-lookup"><span data-stu-id="301a6-141">Total number of rows sampled for statistics calculations.</span></span> <span data-ttu-id="301a6-142">Se Rows Sampled < Rows, l'istogramma e i risultati relativi alla densità visualizzati vengono stimati in base alle righe campionate.</span><span class="sxs-lookup"><span data-stu-id="301a6-142">If Rows Sampled < Rows, the displayed histogram and density results are estimates based on the sampled rows.</span></span>  
  
     <span data-ttu-id="301a6-143">**Passaggi**</span><span class="sxs-lookup"><span data-stu-id="301a6-143">**Steps**</span></span>  
     <span data-ttu-id="301a6-144">Numero di intervalli nell'istogramma.</span><span class="sxs-lookup"><span data-stu-id="301a6-144">Number of steps in the histogram.</span></span> <span data-ttu-id="301a6-145">Ogni intervallo comprende un insieme di valori di colonna seguiti da un valore di colonna pari al limite superiore.</span><span class="sxs-lookup"><span data-stu-id="301a6-145">Each step spans a range of column values followed by an upper bound column value.</span></span> <span data-ttu-id="301a6-146">Gli intervalli dell'istogramma vengono definiti nella prima colonna chiave delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-146">The histogram steps are defined on the first key column in the statistics.</span></span> <span data-ttu-id="301a6-147">Il numero massimo di intervalli è 200.</span><span class="sxs-lookup"><span data-stu-id="301a6-147">The maximum number of steps is 200.</span></span>  
  
     <span data-ttu-id="301a6-148">**Density**</span><span class="sxs-lookup"><span data-stu-id="301a6-148">**Density**</span></span>  
     <span data-ttu-id="301a6-149">Valore calcolato come 1/ *valori distinct* per tutti i valori nella prima colonna chiave dell'oggetto statistiche, ad eccezione dei valori limite dell'istogramma.</span><span class="sxs-lookup"><span data-stu-id="301a6-149">Calculated as 1 / *distinct values* for all values in the first key column of the statistics object, excluding the histogram boundary values.</span></span> <span data-ttu-id="301a6-150">Questo valore Density non viene utilizzato da Query Optimizer e viene visualizzato per compatibilità con le versioni precedenti rispetto a SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="301a6-150">This Density value is not used by the query optimizer and is displayed for backward compatibility with versions before SQL Server 2008.</span></span>  
  
     <span data-ttu-id="301a6-151">**Average Key Length**</span><span class="sxs-lookup"><span data-stu-id="301a6-151">**Average Key Length**</span></span>  
     <span data-ttu-id="301a6-152">Numero medio di byte per valore per tutte le colonne chiave nell'oggetto statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-152">Average number of bytes per value for all of the key columns in the statistics object.</span></span>  
  
     <span data-ttu-id="301a6-153">**String Index**</span><span class="sxs-lookup"><span data-stu-id="301a6-153">**String Index**</span></span>  
     <span data-ttu-id="301a6-154">Il valore Yes indica che l'oggetto statistiche contiene statistiche di riepilogo delle stringhe per migliorare le stime relative alla cardinalità per i predicati della query che utilizzano l'operatore LIKE, ad esempio `WHERE ProductName LIKE '%Bike'`.</span><span class="sxs-lookup"><span data-stu-id="301a6-154">Yes indicates the statistics object contains string summary statistics to improve the cardinality estimates for query predicates that use the LIKE operator; for example, `WHERE ProductName LIKE '%Bike'`.</span></span> <span data-ttu-id="301a6-155">Le statistiche di riepilogo delle stringhe vengono archiviate separatamente rispetto all'istogramma e vengono create nella prima colonna chiave dell'oggetto statistiche quando tale colonna è di tipo **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)** , **nvarchar(max)** , **text**o **ntext**.</span><span class="sxs-lookup"><span data-stu-id="301a6-155">String summary statistics are stored separately from the histogram and are created on the first key column of the statistics object when it is of type **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)**, **nvarchar(max)**, **text**, or **ntext**.</span></span>  
  
     <span data-ttu-id="301a6-156">**Espressione filtro**</span><span class="sxs-lookup"><span data-stu-id="301a6-156">**Filter Expression**</span></span>  
     <span data-ttu-id="301a6-157">Predicato per il subset di righe della tabella incluso nell'oggetto statistiche.</span><span class="sxs-lookup"><span data-stu-id="301a6-157">Predicate for the subset of table rows included in the statistics object.</span></span> <span data-ttu-id="301a6-158">NULL = statistiche non filtrate.</span><span class="sxs-lookup"><span data-stu-id="301a6-158">NULL = non-filtered statistics.</span></span>  
  
     <span data-ttu-id="301a6-159">**Unfiltered Rows**</span><span class="sxs-lookup"><span data-stu-id="301a6-159">**Unfiltered Rows**</span></span>  
     <span data-ttu-id="301a6-160">Numero totale di righe nella tabella prima dell'applicazione dell'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="301a6-160">Total number of rows in the table before applying the filter expression.</span></span> <span data-ttu-id="301a6-161">Se l'espressione di filtro è NULL, Unfiltered Rows è uguale a Rows.</span><span class="sxs-lookup"><span data-stu-id="301a6-161">If Filter Expression is NULL, Unfiltered Rows is equal to Rows.</span></span>  
  
     <span data-ttu-id="301a6-162">Tramite le informazioni seguenti vengono descritte le colonne restituite nel set di risultati per il vettore di densità.</span><span class="sxs-lookup"><span data-stu-id="301a6-162">The following information describes the columns returned in the result set for the Density Vector.</span></span>  
  
     <span data-ttu-id="301a6-163">**All Density**</span><span class="sxs-lookup"><span data-stu-id="301a6-163">**All Density**</span></span>  
     <span data-ttu-id="301a6-164">Il valore Density viene calcolato come 1/ *valori distinct*.</span><span class="sxs-lookup"><span data-stu-id="301a6-164">Density is 1 / *distinct values*.</span></span> <span data-ttu-id="301a6-165">Nei risultati la densità viene visualizzata per ogni prefisso di colonna dell'oggetto statistiche, una riga per ogni densità.</span><span class="sxs-lookup"><span data-stu-id="301a6-165">Results display density for each prefix of columns in the statistics object, one row per density.</span></span> <span data-ttu-id="301a6-166">Un valore distinct è un elenco distinto dei valori delle colonne per riga e per prefisso di colonna.</span><span class="sxs-lookup"><span data-stu-id="301a6-166">A distinct value is a distinct list of the column values per row and per columns prefix.</span></span> <span data-ttu-id="301a6-167">Se l'oggetto statistiche contiene, ad esempio, le colonne chiave (A, B, C), i risultati restituiscono la densità degli elenchi di valori distinct in ognuno di tali prefissi di colonna, ovvero (A), (A,B) e (A, B, C).</span><span class="sxs-lookup"><span data-stu-id="301a6-167">For example, if the statistics object contains key columns (A, B, C), the results report the density of the distinct lists of values in each of these column prefixes: (A), (A,B), and (A, B, C).</span></span> <span data-ttu-id="301a6-168">Usando il prefisso (A, B, C), ciascuno di questi elenchi è un elenco di valori distinct, ovvero (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span><span class="sxs-lookup"><span data-stu-id="301a6-168">Using the prefix (A, B, C), each of these lists is a distinct value list: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span></span> <span data-ttu-id="301a6-169">Usando il prefisso (A, B) agli stessi valori di colonna sono associati gli elenchi di valori distinct (3, 5), (4, 4), e (4, 5).</span><span class="sxs-lookup"><span data-stu-id="301a6-169">Using the prefix (A, B) the same column values have these distinct value lists: (3, 5), (4, 4), and (4, 5).</span></span>  
  
     <span data-ttu-id="301a6-170">**Average Length**</span><span class="sxs-lookup"><span data-stu-id="301a6-170">**Average Length**</span></span>  
     <span data-ttu-id="301a6-171">Lunghezza media, in byte, per archiviare un elenco di valori di colonna per il prefisso di colonna.</span><span class="sxs-lookup"><span data-stu-id="301a6-171">Average length, in bytes, to store a list of the column values for the column prefix.</span></span> <span data-ttu-id="301a6-172">Se per ogni valore presente nell'elenco (3, 5, 6), ad esempio, sono necessari 4 byte, la lunghezza media è di 12 byte.</span><span class="sxs-lookup"><span data-stu-id="301a6-172">For example, if the values in the list (3, 5, 6) each require 4 bytes the length is 12 bytes.</span></span>  
  
     <span data-ttu-id="301a6-173">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="301a6-173">**Columns**</span></span>  
     <span data-ttu-id="301a6-174">Nomi delle colonne nel prefisso per cui sono visualizzati i valori di All Density e Average Length.</span><span class="sxs-lookup"><span data-stu-id="301a6-174">Names of columns in the prefix for which All density and Average length are displayed.</span></span>  
  
     <span data-ttu-id="301a6-175">Tramite le informazioni seguenti vengono descritte le colonne restituite nel set di risultati per l'istogramma.</span><span class="sxs-lookup"><span data-stu-id="301a6-175">The following information describes the columns returned in the result set for the Histogram.</span></span>  
  
     <span data-ttu-id="301a6-176">**RANGE_HI_KEY**</span><span class="sxs-lookup"><span data-stu-id="301a6-176">**RANGE_HI_KEY**</span></span>  
     <span data-ttu-id="301a6-177">Valore di colonna pari al limite superiore per un intervallo dell'istogramma.</span><span class="sxs-lookup"><span data-stu-id="301a6-177">Upper bound column value for a histogram step.</span></span> <span data-ttu-id="301a6-178">Il valore di colonna viene denominato anche valore chiave.</span><span class="sxs-lookup"><span data-stu-id="301a6-178">The column value is also called a key value.</span></span>  
  
     <span data-ttu-id="301a6-179">**RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="301a6-179">**RANGE_ROWS**</span></span>  
     <span data-ttu-id="301a6-180">Numero stimato di righe il cui valore di colonna è compreso in un intervallo dell'istogramma, escluso il limite superiore.</span><span class="sxs-lookup"><span data-stu-id="301a6-180">Estimated number of rows whose column value falls within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="301a6-181">**EQ_ROWS**</span><span class="sxs-lookup"><span data-stu-id="301a6-181">**EQ_ROWS**</span></span>  
     <span data-ttu-id="301a6-182">Numero stimato di righe il cui valore di colonna è uguale al limite superiore dell'intervallo dell'istogramma.</span><span class="sxs-lookup"><span data-stu-id="301a6-182">Estimated number of rows whose column value equals the upper bound of the histogram step.</span></span>  
  
     <span data-ttu-id="301a6-183">**DISTINCT_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="301a6-183">**DISTINCT_RANGE_ROWS**</span></span>  
     <span data-ttu-id="301a6-184">Numero stimato di righe con un valore distinct di colonna compreso in un intervallo dell'istogramma, escluso il limite superiore.</span><span class="sxs-lookup"><span data-stu-id="301a6-184">Estimated number of rows with a distinct column value within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="301a6-185">**AVG_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="301a6-185">**AVG_RANGE_ROWS**</span></span>  
     <span data-ttu-id="301a6-186">Numero medio di righe con valori di colonna duplicati compresi in un intervallo dell'istogramma, escluso il limite superiore (RANGE_ROWS / DISTINCT_RANGE_ROWS per DISTINCT_RANGE_ROWS > 0).</span><span class="sxs-lookup"><span data-stu-id="301a6-186">Average number of rows with duplicate column values within a histogram step, excluding the upper bound (RANGE_ROWS / DISTINCT_RANGE_ROWS for DISTINCT_RANGE_ROWS > 0).</span></span>  
  
7.  <span data-ttu-id="301a6-187">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="301a6-187">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="301a6-188">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="301a6-188">Using Transact-SQL</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="301a6-189">Per visualizzare le proprietà delle statistiche</span><span class="sxs-lookup"><span data-stu-id="301a6-189">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="301a6-190">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="301a6-190">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="301a6-191">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="301a6-191">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="301a6-192">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="301a6-192">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example displays all statistics information for the AK_Address_rowguid index of the Person.Address table.   
    DBCC SHOW_STATISTICS ("Person.Address", AK_Address_rowguid);   
    GO  
    ```  
  
 <span data-ttu-id="301a6-193">Per altre informazioni, vedere [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="301a6-193">For more information, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span></span>  
  
#### <a name="to-find-all-of-the-statistics-on-a-table-or-view"></a><span data-ttu-id="301a6-194">Per trovare tutte le statistiche su una tabella o una vista</span><span class="sxs-lookup"><span data-stu-id="301a6-194">To find all of the statistics on a table or view</span></span>  
  
1.  <span data-ttu-id="301a6-195">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="301a6-195">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="301a6-196">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="301a6-196">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="301a6-197">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="301a6-197">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Gets the following information: name and ID of the statistics, whether the statistics were created automatically or by the user, whether the statistics were created with the NORECOMPUTE option, and whether the statistics have a filter and, if so, what that filter is.  
    */  
    SELECT name AS statistics_name  
        ,stats_id  
        ,auto_created  
        ,user_created  
        ,no_recompute  
        ,has_filter  
        ,filter_definition  
    -- using the sys.stats catalog view  
    FROM sys.stats  
    -- for the Sales.SpecialOffer table  
    WHERE object_id = OBJECT_ID('Sales.SpecialOffer');  
    GO  
    ```  
  
 <span data-ttu-id="301a6-198">Per altre informazioni, vedere [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="301a6-198">For more information, see [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span></span>  
  
  
