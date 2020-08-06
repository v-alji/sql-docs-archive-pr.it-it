---
title: Combinare condizioni quando AND ha la precedenza (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], combining
- precedence [SQL Server], Criteria pane
- search criteria [SQL Server], combining conditions
- combining search conditions
- AND, Criteria pane
ms.assetid: 450eb2eb-6ea3-405b-8dd2-1ff926c016e7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 917d5381bc83083ee1fa3c07375945c0908da521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711488"
---
# <a name="combine-conditions-when-and-has-precedence-visual-database-tools"></a><span data-ttu-id="16421-102">Combinazione di condizioni quando AND ha la precedenza (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="16421-102">Combine Conditions When AND Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="16421-103">Per combinare condizioni con AND, aggiungere due volte la colonna alla query, una volta per ogni condizione.</span><span class="sxs-lookup"><span data-stu-id="16421-103">To combine conditions with AND, you add the column to the query twice--once for each condition.</span></span> <span data-ttu-id="16421-104">Per combinare più condizioni con OR, inserire la prima condizione nella colonna Filtro e le altre in una colonna **Or...** .</span><span class="sxs-lookup"><span data-stu-id="16421-104">To combine conditions with OR, you put the first one in the Filter column and additional conditions into an **Or...** column.</span></span>  
  
 <span data-ttu-id="16421-105">Ad esempio, per trovare i dipendenti che hanno lavorato nell'azienda per più di cinque anni con mansioni di basso livello oppure i dipendenti con mansioni di livello medio indipendentemente dalla data di assunzione,</span><span class="sxs-lookup"><span data-stu-id="16421-105">For example, imagine that you want to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs regardless of their hire date.</span></span> <span data-ttu-id="16421-106">occorre creare una query con tre condizioni, due delle quali collegate con AND:</span><span class="sxs-lookup"><span data-stu-id="16421-106">This query requires three conditions, two of them linked with AND:</span></span>  
  
-   <span data-ttu-id="16421-107">I dipendenti assunti da più di cinque anni e con livello pari a 100</span><span class="sxs-lookup"><span data-stu-id="16421-107">Employees with a hire date earlier than five years ago AND with a job level of 100.</span></span>  
  
     <span data-ttu-id="16421-108">-oppure-</span><span class="sxs-lookup"><span data-stu-id="16421-108">-or-</span></span>  
  
-   <span data-ttu-id="16421-109">I dipendenti con livello pari a 200</span><span class="sxs-lookup"><span data-stu-id="16421-109">Employees with a job level of 200.</span></span>  
  
### <a name="to-combine-conditions-when-and-has-precedence"></a><span data-ttu-id="16421-110">Per combinare condizioni quando AND ha la precedenza</span><span class="sxs-lookup"><span data-stu-id="16421-110">To combine conditions when AND has precedence</span></span>  
  
1.  <span data-ttu-id="16421-111">Nel [riquadro Criteri](visual-database-tools.md)aggiungere le colonne di dati da includere nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="16421-111">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="16421-112">Per eseguire la ricerca sulla stessa colonna utilizzando due o più condizioni collegate con AND, è necessario aggiungere alla griglia il nome della colonna di dati per ciascun valore da includere nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="16421-112">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="16421-113">Nella colonna **Filtro** immettere tutte le condizioni da collegare con AND.</span><span class="sxs-lookup"><span data-stu-id="16421-113">In the **Filter** column, enter all the conditions that you want to link with AND.</span></span> <span data-ttu-id="16421-114">Ad esempio, per collegare con AND condizioni per l'esecuzione della ricerca nelle colonne `hire_date` e `job_lvl` , immettere rispettivamente i valori `< '1/1/91'` e `= 100`nella colonna Filtro.</span><span class="sxs-lookup"><span data-stu-id="16421-114">For example, to link conditions with AND that search the `hire_date` and `job_lvl` columns, enter the values `< '1/1/91'` and `= 100`, respectively, in the Filter column.</span></span>  
  
     <span data-ttu-id="16421-115">Queste voci della griglia producono la seguente clausola WHERE nell'istruzione nel [riquadro SQL](sql-pane-visual-database-tools.md):</span><span class="sxs-lookup"><span data-stu-id="16421-115">These grid entries produce the following WHERE clause in the statement in the [SQL Pane](sql-pane-visual-database-tools.md):</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91') AND  
      (job_lvl = 100)  
    ```  
  
3.  <span data-ttu-id="16421-116">Nella colonna **Or...** della griglia immettere le condizioni da collegare con OR.</span><span class="sxs-lookup"><span data-stu-id="16421-116">In the **Or...** grid column, enter conditions that you want to link with OR.</span></span> <span data-ttu-id="16421-117">Ad esempio, per aggiungere una condizione per l'esecuzione della ricerca di un altro valore nella colonna `job_lvl` , immettere nella colonna **Or...** un altro valore, ad esempio `= 200`.</span><span class="sxs-lookup"><span data-stu-id="16421-117">For example, to add a condition that searches for another value in the `job_lvl` column, enter an additional value in the **Or...** column, such as `= 200`.</span></span>  
  
     <span data-ttu-id="16421-118">Aggiungendo un valore nella colonna **Or...** si aggiunge un'altra condizione alla clausola WHERE nell'istruzione nel riquadro SQL:</span><span class="sxs-lookup"><span data-stu-id="16421-118">Adding a value in the **Or...** column adds another condition to the WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91' ) AND  
      (job_lvl = 100) OR   
      (job_lvl = 200)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="16421-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16421-119">See Also</span></span>  
 <span data-ttu-id="16421-120">[Combinare condizioni quando OR ha la precedenza &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="16421-120">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="16421-121">[Convenzioni per la combinazione di condizioni di ricerca nel riquadro Criteri &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="16421-121">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 <span data-ttu-id="16421-122">[Regole per l'immissione di valori di ricerca &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="16421-122">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="16421-123">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="16421-123">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
