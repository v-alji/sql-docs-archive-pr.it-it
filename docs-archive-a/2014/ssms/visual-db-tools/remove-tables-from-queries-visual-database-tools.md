---
title: Rimuovere tabelle da query (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting tables
- removing tables
- dropping tables
- queries [SQL Server], tables
ms.assetid: 8fea0b4f-99b7-4050-8d6f-a97ffb839619
author: stevestein
ms.author: sstein
ms.openlocfilehash: fab5380e13742f3cd289ce17f26ad2e5fb9089ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628061"
---
# <a name="remove-tables-from-queries-visual-database-tools"></a><span data-ttu-id="a2cad-102">Rimozione di tabelle da query (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a2cad-102">Remove Tables from Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="a2cad-103">È possibile rimuovere una tabella o qualsiasi altro oggetto con valori di tabella dalla query.</span><span class="sxs-lookup"><span data-stu-id="a2cad-103">You can remove a table - or any table-valued object - from the query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2cad-104">Se viene rimossa una tabella o un oggetto con valori di tabella, la rimozione non riguarderà in alcun modo i dati contenuti nel database, ma solo la query corrente.</span><span class="sxs-lookup"><span data-stu-id="a2cad-104">Removing a table or table-valued object does not delete anything from the database; it only removes it from the current query.</span></span> <span data-ttu-id="a2cad-105">Per informazioni dettagliate sulla rimozione di una tabella da un database, vedere [eliminare tabelle &#40;motore di database&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="a2cad-105">For details about removing a table from a database, see [Delete Tables &#40;Database Engine&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span></span>  
  
### <a name="to-remove-a-table-or-table-structured-object"></a><span data-ttu-id="a2cad-106">Per rimuovere una tabella o un oggetto con struttura di tabella</span><span class="sxs-lookup"><span data-stu-id="a2cad-106">To remove a table or table-structured object</span></span>  
  
-   <span data-ttu-id="a2cad-107">Nel **riquadro diagramma**selezionare la tabella, la vista, la funzione definita dall'utente, il sinonimo o la query desiderata e premere CANC oppure fare clic con il pulsante destro del mouse sull'oggetto e scegliere **Rimuovi** nella finestra di dialogo visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a2cad-107">In the **Diagram Pane**, select the table, view, user-defined function, synonym, or query, and then press DELETE, or right-click the object and then choose **Remove** in the resulting dialog box.</span></span> <span data-ttu-id="a2cad-108">È possibile selezionare e rimuovere più oggetti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a2cad-108">You can select and remove multiple objects at one time.</span></span>  
  
     <span data-ttu-id="a2cad-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a2cad-109">-or-</span></span>  
  
-   <span data-ttu-id="a2cad-110">Rimuovere qualsiasi riferimento all'oggetto nel **riquadro SQL**.</span><span class="sxs-lookup"><span data-stu-id="a2cad-110">Remove all references to the object in the **SQL Pane.**</span></span>  
  
 <span data-ttu-id="a2cad-111">Quando viene rimossa una tabella o un oggetto con valori di tabella, in Progettazione query e Progettazione viste vengono eliminati automaticamente i join che lo riguardano e i riferimenti alle colonne dell'oggetto nel **riquadro SQL** e nel **riquadro Criteri**.</span><span class="sxs-lookup"><span data-stu-id="a2cad-111">When you remove a table or table-valued object, the Query and View Designer automatically removes joins that involve that table or table-valued object and removes references to the object's columns in the **SQL Pane** and **Criteria Pane**.</span></span> <span data-ttu-id="a2cad-112">Se tuttavia la query contiene espressioni complesse che coinvolgono l'oggetto, quest'ultimo non verrà automaticamente eliminato fino a che non siano stati eliminati tutti i riferimenti ad esso.</span><span class="sxs-lookup"><span data-stu-id="a2cad-112">However, if the query contains complex expressions involving the object, the object is not automatically removed until all references to it are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2cad-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2cad-113">See Also</span></span>  
 <span data-ttu-id="a2cad-114">[Aggiunta di tabelle a query &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a2cad-114">[Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="a2cad-115">[Creazione di alias di tabella &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a2cad-115">[Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a2cad-116">[Specificare i criteri di ricerca &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a2cad-116">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a2cad-117">[Riepilogare i risultati delle query &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a2cad-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a2cad-118">Eseguire operazioni di base con le query &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a2cad-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
