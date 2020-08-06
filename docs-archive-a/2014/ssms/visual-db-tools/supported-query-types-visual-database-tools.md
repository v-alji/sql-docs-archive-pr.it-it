---
title: Tipi di query supportati (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Delete query
- queries [SQL Server], types
- Update query
- Query Designer [SQL Server], query types
- Criteria pane
- Insert Values query
- Select query
- Make Table query
- Insert Results query
- Diagram pane [Visual Database Tools]
- View Designer, query types
ms.assetid: 72b9116c-c128-4078-a78d-257a2955a3f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b00b7018fc6d0b631696811bd1870e09842b4162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720711"
---
# <a name="supported-query-types-visual-database-tools"></a><span data-ttu-id="1d1e8-102">Tipi di query supportati (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1d1e8-102">Supported Query Types (Visual Database Tools)</span></span>
  <span data-ttu-id="1d1e8-103">Nei riquadri Diagramma e Criteri di [Progettazione query e Progettazione viste](visual-database-tools.md)è possibile creare i tipi di query seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d1e8-103">You can create the following types of queries in the Diagram and Criteria panes (the graphical panes) of the [Query and View Designer](visual-database-tools.md):</span></span>  
  
-   <span data-ttu-id="1d1e8-104">**Query di selezione** Recupera dati da una o più tabelle o viste.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-104">**Select query** Retrieves data from one or more tables or views.</span></span> <span data-ttu-id="1d1e8-105">Questo tipo di query crea un'istruzione SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-105">This type of query creates an SQL SELECT statement.</span></span>  
  
-   <span data-ttu-id="1d1e8-106">**Accodamento** Crea nuove righe copiando righe esistenti da una tabella a un'altra o all'interno della stessa tabella come righe nuove.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-106">**Insert Results** Creates new rows by copying existing rows from one table into another, or into the same table as new rows.</span></span> <span data-ttu-id="1d1e8-107">Questo tipo di query crea un'istruzione SQL INSERT INTO...SELECT.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-107">This type of query creates an SQL INSERT INTO...SELECT statement.</span></span>  
  
-   <span data-ttu-id="1d1e8-108">**Accodamento valori** Crea una nuova riga e inserisce valori nelle colonne specificate.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-108">**Insert Values** Creates a new row and inserts values into specified columns.</span></span> <span data-ttu-id="1d1e8-109">Questo tipo di query crea un'istruzione SQL INSERT INTO...VALUES.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-109">This type of query creates an SQL INSERT INTO...VALUES statement.</span></span>  
  
-   <span data-ttu-id="1d1e8-110">**Query di aggiornamento** Modifica i valori di singole colonne di una o più righe esistenti in una tabella.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-110">**Update query** Changes the values of individual columns in one or more existing rows in a table.</span></span> <span data-ttu-id="1d1e8-111">Questo tipo di query crea un'istruzione SQL UPDATE...SET.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-111">This type of query creates an SQL UPDATE...SET statement.</span></span>  
  
-   <span data-ttu-id="1d1e8-112">**Query di eliminazione** Rimuove una o più righe da una tabella.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-112">**Delete query** Removes one or more rows from a table.</span></span> <span data-ttu-id="1d1e8-113">Questo tipo di query crea un'istruzione SQL DELETE.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-113">This type of query creates an SQL DELETE statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1d1e8-114">Una query di eliminazione rimuove intere righe dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-114">A Delete query removes entire rows from the table.</span></span> <span data-ttu-id="1d1e8-115">Se si desidera eliminare valori da singole colonne di dati, utilizzare una query di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-115">If you want to delete values from individual data columns, use an Update query.</span></span>  
  
-   <span data-ttu-id="1d1e8-116">**Query di creazione tabella** Crea una nuova tabella e le relative righe copiandovi i risultati di una query.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-116">**Make Table query** Creates a new table and creates rows in it by copying the results of a query into it.</span></span> <span data-ttu-id="1d1e8-117">Questo tipo di query crea un'istruzione SQL SELECT...INTO.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-117">This type of query creates an SQL SELECT...INTO statement.</span></span>  
  
 <span data-ttu-id="1d1e8-118">Oltre a creare le query utilizzando i riquadri grafici, è possibile immettere qualsiasi istruzione SQL nel riquadro SQL per creare query come quelle di unione.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-118">In addition to the queries you can create using the graphical panes, you can enter any SQL statement into the SQL pane, such as Union queries.</span></span>  
  
 <span data-ttu-id="1d1e8-119">Quando si creano query con istruzioni SQL che non possono essere rappresentate nei riquadri grafici, in Progettazione query e Progettazione viste tali riquadri vengono visualizzati in grigio, per indicare che non si riferiscono alla query creata.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-119">When you create queries using SQL statements that cannot be represented in the graphical panes, the Query and View Designer dims those panes to indicate that they do not reflect the query you are creating.</span></span> <span data-ttu-id="1d1e8-120">I riquadri visualizzati in grigio sono tuttavia ancora attivi e, in molti casi, consentono di apportare modifiche alla query.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-120">However, the dimmed panes are still active and, in many cases, you can make changes to the query in those panes.</span></span> <span data-ttu-id="1d1e8-121">Se le modifiche apportate generano una query che può essere rappresentata nei riquadri grafici, tali riquadri non verranno più visualizzati in grigio.</span><span class="sxs-lookup"><span data-stu-id="1d1e8-121">If the changes you make result in a query that can be represented in the graphical panes, those panes are no longer dimmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d1e8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d1e8-122">See Also</span></span>  
 <span data-ttu-id="1d1e8-123">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1d1e8-123">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1d1e8-124">Tipi di query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="1d1e8-124">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
