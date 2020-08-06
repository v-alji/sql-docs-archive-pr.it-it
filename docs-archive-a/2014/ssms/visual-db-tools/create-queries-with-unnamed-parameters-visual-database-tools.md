---
title: Creare query con parametri senza nome (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- unnamed parameters
- parameters [SQL Server], unnamed
ms.assetid: 5f4b664b-3d3d-4d07-a0e7-791d78743504
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0ea53afd1fa4d44390f5805d6b28494428608b90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623704"
---
# <a name="create-queries-with-unnamed-parameters-visual-database-tools"></a><span data-ttu-id="65fd0-102">Creazione di query con parametri senza nome (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="65fd0-102">Create Queries with Unnamed Parameters (Visual Database Tools)</span></span>
  <span data-ttu-id="65fd0-103">Per creare una query con un parametro senza nome, è possibile inserire un punto interrogativo (?) come segnaposto per un valore letterale.</span><span class="sxs-lookup"><span data-stu-id="65fd0-103">You can create a query with an unnamed parameter by specifying a question mark (?) as a placeholder for a literal value.</span></span> <span data-ttu-id="65fd0-104">In Progettazione query e Progettazione viste gli verrà assegnato automaticamente un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="65fd0-104">Query and View Designer will give it a temporary name.</span></span> <span data-ttu-id="65fd0-105">Nella query è possibile specificare qualsiasi numero di parametri senza nome.</span><span class="sxs-lookup"><span data-stu-id="65fd0-105">You can specify as many unnamed parameters in the query as you need.</span></span>  
  
 <span data-ttu-id="65fd0-106">Al momento dell'esecuzione della query in Progettazione query e Progettazione viste, nella finestra di dialogo Parametri query viene visualizzato il nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="65fd0-106">When you run the query in the Query and View Designer, the Query Parameters Dialog Box is displayed with the temporary name.</span></span>  
  
### <a name="to-specify-an-unnamed-parameter"></a><span data-ttu-id="65fd0-107">Per specificare un parametro senza nome</span><span class="sxs-lookup"><span data-stu-id="65fd0-107">To specify an unnamed parameter</span></span>  
  
1.  <span data-ttu-id="65fd0-108">Aggiungere al [riquadro Criteri](visual-database-tools.md)le colonne o le espressioni da includere nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="65fd0-108">Add the columns or expressions that you want to search to the [Criteria pane](visual-database-tools.md).</span></span> <span data-ttu-id="65fd0-109">Per evitare che le colonne o le espressioni compaiano nell'output della query, rimuoverle dalle colonne di output.</span><span class="sxs-lookup"><span data-stu-id="65fd0-109">If you do not want the search columns or expressions to appear in the query output, remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="65fd0-110">Individuare la riga che contiene la colonna di dati o l'espressione da includere nella ricerca e aggiungere un punto interrogativo (?) nella colonna **Filtro** della griglia.</span><span class="sxs-lookup"><span data-stu-id="65fd0-110">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter a question mark (?).</span></span>  
  
     <span data-ttu-id="65fd0-111">Per impostazione predefinita viene aggiunto l'operatore "=".</span><span class="sxs-lookup"><span data-stu-id="65fd0-111">By default, the Query and View Designer adds the "=" operator.</span></span> <span data-ttu-id="65fd0-112">In ogni caso, è possibile modificare la cella inserendo ">", "<" o qualsiasi altro operatore di confronto SQL.</span><span class="sxs-lookup"><span data-stu-id="65fd0-112">However, you can edit the cell to substitute ">", "<", or any other SQL comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65fd0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65fd0-113">See Also</span></span>  
 [<span data-ttu-id="65fd0-114">Esecuzione di query con parametri &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="65fd0-114">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
