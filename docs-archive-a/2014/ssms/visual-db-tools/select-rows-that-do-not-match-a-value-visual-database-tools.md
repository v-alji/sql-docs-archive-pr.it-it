---
title: Selezionare righe non corrispondenti a un valore (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], rows not matching value
- row not matching value [SQL Server]
- NOT operator [Visual Database Tools]
- search criteria [SQL Server], rows not matching value
ms.assetid: 19898578-7b2f-401c-bb8f-9f2a017efdf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 412ec93cbfedc87e92da9e86c7e4c7455919722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719319"
---
# <a name="select-rows-that-do-not-match-a-value-visual-database-tools"></a><span data-ttu-id="4b7fa-102">Selezione di righe non corrispondenti a un valore (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4b7fa-102">Select Rows That Do Not Match a Value (Visual Database Tools)</span></span>
  <span data-ttu-id="4b7fa-103">Per individuare le righe che non corrispondono a un valore, utilizzare l'operatore NOT.</span><span class="sxs-lookup"><span data-stu-id="4b7fa-103">To find rows that do not match a value, use the NOT operator.</span></span>  
  
### <a name="to-find-rows-that-do-not-match-a-value"></a><span data-ttu-id="4b7fa-104">Per individuare le righe che non corrispondono a un valore</span><span class="sxs-lookup"><span data-stu-id="4b7fa-104">To find rows that do not match a value</span></span>  
  
1.  <span data-ttu-id="4b7fa-105">Se non è ancora stato fatto, aggiungere nel [riquadro Criteri](visual-database-tools.md)le colonne o le espressioni da usare nella condizione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="4b7fa-105">If you have not done so already, add the columns or expressions that you want to use within your search condition to the [Criteria pane](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="4b7fa-106">Individuare la riga contenente la colonna di dati o l'espressione da includere nella ricerca, quindi immettere l'operatore NOT seguito da un valore di ricerca nella colonna **Filtro** della griglia.</span><span class="sxs-lookup"><span data-stu-id="4b7fa-106">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter the NOT operator followed by a search value.</span></span>  
  
 <span data-ttu-id="4b7fa-107">Per trovare, ad esempio, tutte le righe in una tabella `products` in cui i valori nella colonna del codice del prodotto iniziano con un carattere diverso da "A", immettere una condizione di ricerca analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="4b7fa-107">For example, to find all the rows in a `products` table where the values in the product code column begin with a character other than "A," you can enter a search condition such as the following:</span></span>  
  
```  
NOT LIKE 'A%'  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b7fa-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b7fa-108">See Also</span></span>  
 <span data-ttu-id="4b7fa-109">[Regole per l'immissione di valori di ricerca &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4b7fa-109">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4b7fa-110">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4b7fa-110">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
