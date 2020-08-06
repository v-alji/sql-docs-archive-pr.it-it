---
title: Eseguire query con join (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [Visual Database Tools]
- View Designer, joins
- table joins [SQL Server]
- multiple table joins
- Visual Database Tools [SQL Server], queries
- Query Designer [SQL Server], joins
- joins [SQL Server], queries
ms.assetid: 8f068207-d777-4e64-8c4c-d821f0ddb450
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9d0053e6786d96508be8a87347cdc0b19975a3fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713672"
---
# <a name="query-with-joins-visual-database-tools"></a><span data-ttu-id="fe35c-102">Esecuzione di query con join (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fe35c-102">Query with Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="fe35c-103">Il risultato di una query può includere dati tratti da più tabelle o oggetti con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="fe35c-103">A query result can include data from multiple tables or table-valued objects.</span></span> <span data-ttu-id="fe35c-104">Per combinare i dati di più oggetti con valori di tabella, è possibile utilizzare l'operazione JOIN di SQL.</span><span class="sxs-lookup"><span data-stu-id="fe35c-104">To combine data from multiple table-valued objects, you use the JOIN operation from SQL.</span></span>  
  
 <span data-ttu-id="fe35c-105">Per informazioni sulla creazione di query con più tabelle, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="fe35c-105">For information about creating queries using multiple tables, see the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe35c-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fe35c-106">In This Section</span></span>  
 [<span data-ttu-id="fe35c-107">Modifica di operatori di join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-107">Modify Join Operators &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
 <span data-ttu-id="fe35c-108">Viene descritto come specificare che il join di tabelle deve essere effettuato utilizzando un operatore diverso dall'uguale (=).</span><span class="sxs-lookup"><span data-stu-id="fe35c-108">Specify that tables should be joined using an operator other than equal (=).</span></span>  
  
 [<span data-ttu-id="fe35c-109">Rappresentazione di join in Progettazione query e Progettazione viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-109">How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;</span></span>](how-the-query-and-view-designer-represents-joins-visual-database-tools.md)  
 <span data-ttu-id="fe35c-110">Viene illustrata la rappresentazione grafica del join visualizzata nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="fe35c-110">Explains the graphic representation of the join as you see it in the Diagram pane.</span></span>  
  
 [<span data-ttu-id="fe35c-111">Unione di tabelle in modo automatico &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-111">Join Tables Automatically &#40;Visual Database Tools&#41;</span></span>](join-tables-automatically-visual-database-tools.md)  
 <span data-ttu-id="fe35c-112">Viene descritta la procedura per consentire a Progettazione query e Progettazione viste di determinare se deve essere eseguito il join di tabelle.</span><span class="sxs-lookup"><span data-stu-id="fe35c-112">Steps for allowing the Query and View Designer determine if tables should be joined.</span></span>  
  
 [<span data-ttu-id="fe35c-113">Unione di tabelle in modo manuale &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-113">Join Tables Manually &#40;Visual Database Tools&#41;</span></span>](join-tables-manually-visual-database-tools.md)  
 <span data-ttu-id="fe35c-114">Viene descritta la procedura per creare manualmente un join nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="fe35c-114">Steps for creating a join manually in the Diagram pane.</span></span>  
  
 [<span data-ttu-id="fe35c-115">Join di tabelle su più colonne &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-115">Join Tables on Multiple Columns &#40;Visual Database Tools&#41;</span></span>](join-tables-on-multiple-columns-visual-database-tools.md)  
 <span data-ttu-id="fe35c-116">Viene descritta la procedura per eseguire il join di tabelle con più criteri per ciascuna.</span><span class="sxs-lookup"><span data-stu-id="fe35c-116">Steps for joining tables with multiple criteria for each table.</span></span>  
  
 [<span data-ttu-id="fe35c-117">Creazione di join esterni &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-117">Create Outer Joins &#40;Visual Database Tools&#41;</span></span>](create-outer-joins-visual-database-tools.md)  
 <span data-ttu-id="fe35c-118">Viene descritto come specificare che le tabelle in join devono includere righe anche quando non corrispondono a righe nella tabella corrispondente.</span><span class="sxs-lookup"><span data-stu-id="fe35c-118">Specify that joined tables should include rows even when they do not match rows in the corresponding table.</span></span>  
  
 [<span data-ttu-id="fe35c-119">Rimozione di join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-119">Remove Joins &#40;Visual Database Tools&#41;</span></span>](remove-joins-visual-database-tools.md)  
 <span data-ttu-id="fe35c-120">Viene descritta la procedura per rimuovere un join tra tabelle.</span><span class="sxs-lookup"><span data-stu-id="fe35c-120">Steps for removing a join between tables.</span></span>  
  
 [<span data-ttu-id="fe35c-121">Creare self-join in modo automatico &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-121">Create Self-Joins Automatically &#40;Visual Database Tools&#41;</span></span>](create-self-joins-automatically-visual-database-tools.md)  
 <span data-ttu-id="fe35c-122">Viene descritta la procedura per consentire a Progettazione query e Progettazione viste di creare un self-join.</span><span class="sxs-lookup"><span data-stu-id="fe35c-122">Steps for allowing the Query and View Designer to create a self-join.</span></span>  
  
 [<span data-ttu-id="fe35c-123">Creazione di self-join in modo manuale &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-123">Create Self-Joins Manually &#40;Visual Database Tools&#41;</span></span>](create-self-joins-manually-visual-database-tools.md)  
 <span data-ttu-id="fe35c-124">Viene descritta la procedura per utilizzare un join per trovare subset di dati all'interno di una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="fe35c-124">Steps for using a join to find subsets of data within a single table.</span></span>  
  
 [<span data-ttu-id="fe35c-125">Visualizzazione delle proprietà di un join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-125">View Join Properties &#40;Visual Database Tools&#41;</span></span>](view-join-properties-visual-database-tools.md)  
 <span data-ttu-id="fe35c-126">Viene descritta la procedura per visualizzare le proprietà di un join.</span><span class="sxs-lookup"><span data-stu-id="fe35c-126">Steps for viewing the properties of a join.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fe35c-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="fe35c-127">Related Sections</span></span>  
 [<span data-ttu-id="fe35c-128">Tipi di query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-128">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
 <span data-ttu-id="fe35c-129">Vengono forniti collegamenti ad argomenti in cui vengono descritti i tipi di query supportati.</span><span class="sxs-lookup"><span data-stu-id="fe35c-129">Provides links to topics describing the supported query types.</span></span>  
  
 [<span data-ttu-id="fe35c-130">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
 <span data-ttu-id="fe35c-131">Vengono forniti collegamenti ad argomenti relativi alle operazioni che è possibile eseguire più comunemente con le query.</span><span class="sxs-lookup"><span data-stu-id="fe35c-131">Provides links to topics covering the most common query tasks.</span></span>  
  
 [<span data-ttu-id="fe35c-132">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fe35c-132">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
 <span data-ttu-id="fe35c-133">Vengono forniti collegamenti ad argomenti relativi ai vari tipi di criteri di ricerca e alle modalità di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="fe35c-133">Provides links to topics covering the various kinds of search criteria and how to use them.</span></span>  
  
  
