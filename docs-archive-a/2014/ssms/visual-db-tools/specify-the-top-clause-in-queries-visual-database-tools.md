---
title: Definire la clausola TOP nelle query (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- TOP clause, queries
- percentage of rows returned [SQL Server]
- number of rows
- search conditions [SQL Server], TOP clause
- restricting rows returned
- search criteria [SQL Server], limiting rows returned
- inspecting portion of results
- limiting rows returned
- search criteria [SQL Server], TOP clause
ms.assetid: ba7d7c10-9bb3-4d9b-90b0-5fa94ecae59b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8228779703b1bbe3753f1e2728e83b4b5c3a3d17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724328"
---
# <a name="specify-the-top-clause-in-queries-visual-database-tools"></a><span data-ttu-id="1dcdd-102">Definire la clausola TOP nelle query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1dcdd-102">Specify the TOP Clause in Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="1dcdd-103">La clausola TOP restituisce solo le prime *n* righe o il primo *n percento* delle righe di una query.</span><span class="sxs-lookup"><span data-stu-id="1dcdd-103">The TOP clause returns only the first *n* or *n percent* rows from a query.</span></span> <span data-ttu-id="1dcdd-104">La clausola TOP è utile quando si desidera controllare una parte dei risultati per verificare se la query funziona come previsto. Tale clausola consente di eseguire questa operazione senza occupare tutte le risorse necessarie per restituire tutti i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="1dcdd-104">The TOP clause is useful when you want to inspect a portion of your results to find out if your query does what you expect it to do, without taking the resources necessary to return all of the query results.</span></span>  
  
### <a name="to-specify-the-top-clause-in-queries"></a><span data-ttu-id="1dcdd-105">Per specificare la clausola TOP nelle query</span><span class="sxs-lookup"><span data-stu-id="1dcdd-105">To specify the TOP clause in queries</span></span>  
  
1.  <span data-ttu-id="1dcdd-106">Aprire una query in Esplora soluzioni o crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="1dcdd-106">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="1dcdd-107">Scegliere **Finestra Proprietà** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="1dcdd-107">From the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="1dcdd-108">Nella finestra **Proprietà**individuare ed espandere la proprietà **Specifica Top** .</span><span class="sxs-lookup"><span data-stu-id="1dcdd-108">In the **Properties Window**, locate and expand the **Top Specification** property.</span></span>  
  
4.  <span data-ttu-id="1dcdd-109">Fare clic sulla proprietà figlio **(Top)** e impostarla su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1dcdd-109">Click the **(Top)** child property and set it to **Yes**.</span></span>  
  
5.  <span data-ttu-id="1dcdd-110">Nella proprietà figlio **Espressione** digitare un'espressione con risultato numerico, ad esempio "10" o "2\*5".</span><span class="sxs-lookup"><span data-stu-id="1dcdd-110">In the **Expression** child property, type an expression that has a numeric result (for example, "10" or "2\*5").</span></span>  
  
6.  <span data-ttu-id="1dcdd-111">Fare clic sulla proprietà figlio **Percentuale** e indicare se la proprietà **Espressione** deve essere considerata come percentuale di tutte le righe restituite (Sì) o come numero assoluto di righe restituite (No).</span><span class="sxs-lookup"><span data-stu-id="1dcdd-111">Click the **Percent** child property and indicate whether or not to treat the **Expression** property as a percentage of all rows returned (Yes) or as the absolute number of rows returned (No).</span></span>  
  
7.  <span data-ttu-id="1dcdd-112">Se nella query viene usata la clausola ORDER BY, fare clic sulla proprietà figlio **Con valori equivalenti** e scegliere **Sì** per visualizzare tutte le righe di un gruppo se viene inclusa solo una parte del gruppo oppure **No** per non visualizzarle tutte.</span><span class="sxs-lookup"><span data-stu-id="1dcdd-112">If your query uses the ORDER BY clause, click the **With Ties** child property and choose **Yes** to display all rows in a group if only part of the group is included or **No** to truncate them.</span></span>  
  
 <span data-ttu-id="1dcdd-113">Man mano che si esegue la procedura sopra descritta, la clausola TOP visualizzata nel riquadro SQL viene aggiornata in base alle impostazioni correnti delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="1dcdd-113">As you work through the preceding procedure, notice that the TOP clause, displayed in the SQL pane, changes to reflect the current settings of the properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1dcdd-114">Per modificare i valori delle proprietà figlio della proprietà **Specifica Top** , è anche possibile modificare la clausola TOP nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="1dcdd-114">You can also change the values of the child properties of the **Top Specification** by editing the TOP clause in the SQL pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dcdd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dcdd-115">See Also</span></span>  
 <span data-ttu-id="1dcdd-116">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1dcdd-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1dcdd-117">Proprietà delle query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="1dcdd-117">Query Properties &#40;Visual Database Tools&#41;</span></span>](query-properties-visual-database-tools.md)  
  
  
