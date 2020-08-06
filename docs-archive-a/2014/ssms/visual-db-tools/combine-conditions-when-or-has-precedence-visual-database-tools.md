---
title: Combinare condizioni quando OR ha la precedenza (Visual Database Tools) | Microsoft Docs
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
- OR operator
ms.assetid: b30f5ac9-25e7-4163-80ed-44e4bccb455d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8be0d2f783c28662eb01f6bf191dc24d339534f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711483"
---
# <a name="combine-conditions-when-or-has-precedence-visual-database-tools"></a><span data-ttu-id="f24e9-102">Combinare condizioni quando OR ha la precedenza (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="f24e9-102">Combine Conditions When OR Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="f24e9-103">Per collegare condizioni con OR e attribuire loro la precedenza sulle condizioni collegate con AND, è necessario ripetere la condizione AND per ogni condizione OR.</span><span class="sxs-lookup"><span data-stu-id="f24e9-103">To link conditions with OR and give them precedence over conditions linked with AND, you must repeat the AND condition for each OR condition.</span></span>  
  
 <span data-ttu-id="f24e9-104">Per trovare, ad esempio, i dipendenti che hanno lavorato nell'azienda per più di cinque anni con mansioni di basso livello o che sono in pensione,</span><span class="sxs-lookup"><span data-stu-id="f24e9-104">For example, imagine that you want to find all employees who have been with the company more than five years and have lower-level jobs or are retired.</span></span> <span data-ttu-id="f24e9-105">occorre creare una query con tre condizioni, un'unica condizione collegata ad altre due mediante AND:</span><span class="sxs-lookup"><span data-stu-id="f24e9-105">This query requires three conditions, a single condition linked to two additional conditions with AND:</span></span>  
  
-   <span data-ttu-id="f24e9-106">I dipendenti assunti da più di cinque anni e</span><span class="sxs-lookup"><span data-stu-id="f24e9-106">Employees with a hire date earlier than five years ago, and</span></span>  
  
-   <span data-ttu-id="f24e9-107">I dipendenti con livello pari a 100 o il cui stato sia "R" (retired, pensionato).</span><span class="sxs-lookup"><span data-stu-id="f24e9-107">Employees with a job level of 100 or whose status is "R" (for retired).</span></span>  
  
 <span data-ttu-id="f24e9-108">Nella procedura riportata di seguito viene illustrato come creare questo tipo di query nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="f24e9-108">The following procedure illustrates how to create this type of query in the Criteria pane.</span></span>  
  
### <a name="to-combine-conditions-when-or-has-precedence"></a><span data-ttu-id="f24e9-109">Per combinare condizioni quando OR ha la precedenza</span><span class="sxs-lookup"><span data-stu-id="f24e9-109">To combine conditions when OR has precedence</span></span>  
  
1.  <span data-ttu-id="f24e9-110">Nel [riquadro Criteri](visual-database-tools.md)aggiungere le colonne di dati da includere nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="f24e9-110">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="f24e9-111">Per eseguire la ricerca sulla stessa colonna utilizzando due o più condizioni collegate con AND, è necessario aggiungere alla griglia il nome della colonna di dati per ciascun valore da includere nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="f24e9-111">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="f24e9-112">Creare le condizioni da collegare con OR immettendo la prima nella colonna **Filtro** della griglia e la seconda (e le successive) in colonne **OR…** separate.</span><span class="sxs-lookup"><span data-stu-id="f24e9-112">Create the conditions to be linked with OR by entering the first one into the **Filter** grid column and the second (and subsequent ones) into separate **Or...** columns.</span></span> <span data-ttu-id="f24e9-113">Ad esempio, per collegare con OR condizioni per l'esecuzione della ricerca nelle colonne `job_lvl` e `status` , immettere `= 100` nella colonna **Filtro** per `job_lvl` e `= 'R'` nella colonna **OR...** per `status`.</span><span class="sxs-lookup"><span data-stu-id="f24e9-113">For example, to link conditions with OR that search the `job_lvl` and `status` columns, enter `= 100` in the **Filter** column for `job_lvl` and `= 'R'` in the **Or...** column for `status`.</span></span>  
  
     <span data-ttu-id="f24e9-114">Immettendo questi valori nella griglia, verrà prodotta la seguente clausola WHERE nell'istruzione del riquadro SQL:</span><span class="sxs-lookup"><span data-stu-id="f24e9-114">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) OR (status = 'R')  
    ```  
  
3.  <span data-ttu-id="f24e9-115">Creare la condizione AND immettendola una volta per ciascuna condizione OR.</span><span class="sxs-lookup"><span data-stu-id="f24e9-115">Create the AND condition by entering it once for each OR condition.</span></span> <span data-ttu-id="f24e9-116">Collocare ogni voce nella stessa colonna della griglia in cui è presente la corrispondente condizione OR.</span><span class="sxs-lookup"><span data-stu-id="f24e9-116">Place each entry in the same grid column as the OR condition it corresponds to.</span></span> <span data-ttu-id="f24e9-117">Ad esempio, per aggiungere una condizione AND che consenta di eseguire la ricerca nella colonna `hire_date` e sia valida per entrambe le condizioni OR, immettere `< '1/1/91'` nella colonna Criteri e nella colonna **OR...** .</span><span class="sxs-lookup"><span data-stu-id="f24e9-117">For example, to add an AND condition that searches the `hire_date` column and applies to both OR conditions, enter `< '1/1/91'` in both the Criteria column and the **Or...** column.</span></span>  
  
     <span data-ttu-id="f24e9-118">Immettendo questi valori nella griglia, verrà prodotta la seguente clausola WHERE nell'istruzione del riquadro SQL:</span><span class="sxs-lookup"><span data-stu-id="f24e9-118">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) AND   
      (hire_date < '01/01/91' ) OR  
      (status = 'R') AND   
      (hire_date < '01/01/91' )  
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="f24e9-119">Per ripetere una condizione AND, aggiungerla una volta, quindi usare i comandi **Taglia** e **Incolla** del menu **Modifica** per ripeterla per altre condizioni OR.</span><span class="sxs-lookup"><span data-stu-id="f24e9-119">You can repeat an AND condition by adding it once, and then using the **Cut** and **Paste** commands from the **Edit** menu to repeat it for other OR conditions.</span></span>  
  
 <span data-ttu-id="f24e9-120">La clausola WHERE creata da Progettazione query e Progettazione viste è equivalente alla clausola WHERE riportata di seguito, in cui le parentesi consentono di specificare la precedenza di OR su AND:</span><span class="sxs-lookup"><span data-stu-id="f24e9-120">The WHERE clause created by the Query and View Designer is equivalent to the following WHERE clause, which uses parentheses to specify the precedence of OR over AND:</span></span>  
  
```  
WHERE (job_lvl = 100 OR status = 'R') AND  
   (hire_date < '01/01/91')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f24e9-121">Se le condizioni di ricerca vengono immesse nel formato indicato sopra nel [riquadro SQL](sql-pane-visual-database-tools.md)e la query viene poi modificata nel riquadro Diagramma o Criteri, in Progettazione query e Progettazione viste l'istruzione SQL verrà ricreata per assicurare la corrispondenza tra il formato in uso e la condizione AND distribuita esplicitamente a entrambe le condizioni OR.</span><span class="sxs-lookup"><span data-stu-id="f24e9-121">If you enter the search conditions in the format shown immediately above in the [SQL Pane](sql-pane-visual-database-tools.md), but then make a change to the query in the Diagram or Criteria panes, the Query and View Designer recreates the SQL statement to match the form with the AND condition explicitly distributed to both OR conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f24e9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f24e9-122">See Also</span></span>  
 <span data-ttu-id="f24e9-123">[Convenzioni per la combinazione di condizioni di ricerca nel riquadro Criteri &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f24e9-123">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="f24e9-124">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="f24e9-124">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
