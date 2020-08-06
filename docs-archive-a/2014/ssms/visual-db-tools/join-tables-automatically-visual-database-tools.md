---
title: Unire tabelle in modo automatico (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- joins [SQL Server], creating
- joins [SQL Server], automatic
ms.assetid: f152af82-bcb6-49ca-af19-48cdb7fc9ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: d05100f801d972759c1b5c105814f5cdbdccf84f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711440"
---
# <a name="join-tables-automatically-visual-database-tools"></a><span data-ttu-id="a5f3a-102">Unione di tabelle in modo automatico (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a5f3a-102">Join Tables Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="a5f3a-103">Quando si aggiungono due o più tabelle a una query, in [Progettazione query e Progettazione viste](visual-database-tools.md) viene eseguito un tentativo per determinare se le tabelle sono correlate.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-103">When you add two or more tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to determine if they are related.</span></span> <span data-ttu-id="a5f3a-104">In caso affermativo, linee di join verranno inserite automaticamente tra i rettangoli che rappresentano le tabelle o gli oggetti con struttura di tabella.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-104">If they are, the Query and View Designer automatically puts join lines between the rectangles representing the tables or table-structured objects.</span></span>  
  
 <span data-ttu-id="a5f3a-105">In Progettazione query e Progettazione viste le tabelle saranno considerate in join se:</span><span class="sxs-lookup"><span data-stu-id="a5f3a-105">The Query and View Designer will recognize tables as joined if:</span></span>  
  
-   <span data-ttu-id="a5f3a-106">Il database contiene informazioni che specificano che le tabelle sono correlate.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-106">The database contains information that specifies that the tables are related.</span></span>  
  
-   <span data-ttu-id="a5f3a-107">Se due colonne, una per ogni tabella, hanno lo stesso nome e lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-107">If two columns, one in each table, have the same name and data type.</span></span> <span data-ttu-id="a5f3a-108">La colonna è una chiave primaria in almeno una delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-108">The column must be a primary key in at least one of the tables.</span></span> <span data-ttu-id="a5f3a-109">Se, in caso di aggiunta delle tabelle `employee` e `jobs` , la colonna `job_id` è la chiave primaria nella tabella `jobs` ed entrambe le tabelle contengono una colonna denominata `job_id` con lo stesso tipo di dati, le due tabelle verranno unite automaticamente in join in Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-109">For example, if you add `employee` and `jobs` tables, if the `job_id` column is the primary key in the `jobs` table, and if each table has a column called `job_id` with the same data type, the Query and View Designer will automatically join the tables.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5f3a-110">In Progettazione query e Progettazione viste verrà creato un solo join basato sulle colonne con lo stesso nome e lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-110">The Query and View Designer will create only one join based on columns with the same name and data type.</span></span> <span data-ttu-id="a5f3a-111">Se sono possibili più join, Progettazione query prevederà un arresto in seguito alla creazione di un join basato sul primo set di colonne corrispondenti incontrate.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-111">If more than one join is possible, the Query and View Designer stops after creating a join based on the first set of matching columns that it finds.</span></span>  
  
-   <span data-ttu-id="a5f3a-112">Si rileverà che una condizione di ricerca (una clausola WHERE) in effetti è una condizione di join.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-112">The Query and View Designer detects that a search condition (a WHERE clause) is actually a join condition.</span></span> <span data-ttu-id="a5f3a-113">Sarà ad esempio possibile aggiungere le tabelle `employee` e `jobs`e creare una condizione di ricerca per lo stesso valore nella colonna `job_id` di entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-113">For example, you might add the tables `employee` and `jobs`, then create a search condition that searches for the same value in the `job_id` column of both tables.</span></span> <span data-ttu-id="a5f3a-114">A questo punto, in Progettazione query si rileverà che il risultato della condizione di ricerca è un join e si creerà una condizione di join basata sulla condizione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-114">When you do, the Query and View Designer detects that the search condition results in a join, and then creates a join condition based on the search condition.</span></span>  
  
 <span data-ttu-id="a5f3a-115">Se in Progettazione query e Progettazione viste è stato creato un join non pertinente alla query, sarà possibile modificare il join o rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-115">If the Query and View Designer has created a join that is not suitable to your query, you can modify the join or remove it.</span></span> <span data-ttu-id="a5f3a-116">For informazioni dettagliate, vedere [Modifica di operatori di join &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) e [Rimozione di join &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a5f3a-116">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) and [Remove Joins &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="a5f3a-117">Se le tabelle non vengono unite in join automaticamente nella query, sarà possibile creare manualmente il join.</span><span class="sxs-lookup"><span data-stu-id="a5f3a-117">If the Query and View Designer does not automatically join the tables in your query, you can create a join yourself.</span></span> <span data-ttu-id="a5f3a-118">Per informazioni dettagliate, vedere [Unione di tabelle in modo manuale &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a5f3a-118">For details, see [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f3a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5f3a-119">See Also</span></span>  
 <span data-ttu-id="a5f3a-120">[Rappresentazione di join in Progettazione query e Progettazione viste &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a5f3a-120">[How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a5f3a-121">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a5f3a-121">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a5f3a-122">Eseguire query con join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a5f3a-122">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
