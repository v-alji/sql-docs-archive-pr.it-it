---
title: Specificare più condizioni di ricerca per più colonne (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 06617729-0d0b-4da2-9890-b7e2f5cdbc7b
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccf08a98d39d4ab808b7c2df794164b341be363a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626444"
---
# <a name="specify-multiple-search-conditions-for-multiple-columns-visual-database-tools"></a><span data-ttu-id="fea1c-102">Definizione di più condizioni di ricerca per più colonne (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fea1c-102">Specify Multiple Search Conditions for Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="fea1c-103">È possibile ampliare o limitare l'ambito della query includendo diverse colonne di dati tra le condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="fea1c-103">You can expand or narrow the scope of your query by including several data columns as part of your search condition.</span></span> <span data-ttu-id="fea1c-104">Può, ad esempio, essere necessario:</span><span class="sxs-lookup"><span data-stu-id="fea1c-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="fea1c-105">Cercare i dipendenti che hanno lavorato più di cinque anni nell'azienda o che hanno determinate mansioni.</span><span class="sxs-lookup"><span data-stu-id="fea1c-105">Search for employees who either have worked more than five years at the company or who hold certain jobs.</span></span>  
  
-   <span data-ttu-id="fea1c-106">Cercare un libro pubblicato da un determinato editore e che tratta di cucina.</span><span class="sxs-lookup"><span data-stu-id="fea1c-106">Search for a book that is both published by a specific publisher and pertains to cooking.</span></span>  
  
 <span data-ttu-id="fea1c-107">Per creare una query per la ricerca di valori in una colonna all'interno di una combinazione di colonne, specificare una condizione OR.</span><span class="sxs-lookup"><span data-stu-id="fea1c-107">To create a query that searches for values in either of two (or more) columns, you specify an OR condition.</span></span> <span data-ttu-id="fea1c-108">Per creare una query che soddisfi tutte le condizioni in più colonne, specificare una condizione AND.</span><span class="sxs-lookup"><span data-stu-id="fea1c-108">To create a query that must meet all conditions in two (or more) columns, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="fea1c-109">Specifica di una condizione OR</span><span class="sxs-lookup"><span data-stu-id="fea1c-109">Specifying an OR Condition</span></span>  
 <span data-ttu-id="fea1c-110">Per creare più condizioni collegate con OR, inserire ciascuna condizione in una colonna diversa del riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="fea1c-110">To create multiple conditions linked with OR, you put each separate condition in a different column of the Criteria pane.</span></span>  
  
#### <a name="to-specify-an-or-condition-for-two-different-columns"></a><span data-ttu-id="fea1c-111">Per specificare una condizione OR per due colonne diverse</span><span class="sxs-lookup"><span data-stu-id="fea1c-111">To specify an OR condition for two different columns</span></span>  
  
1.  <span data-ttu-id="fea1c-112">Nel [riquadro Criteri](visual-database-tools.md)aggiungere le colonne da includere nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="fea1c-112">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="fea1c-113">Nella colonna **Filtro** per la prima colonna da includere nella ricerca, specificare la prima condizione.</span><span class="sxs-lookup"><span data-stu-id="fea1c-113">In the **Filter** column for the first column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="fea1c-114">Nella colonna **Or...** per la seconda colonna di dati da includere nella ricerca, specificare la seconda condizione lasciando vuota la colonna **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="fea1c-114">In the **Or...** column for the second data column to search, specify the second condition, leaving the **Filter** column blank.</span></span>  
  
     <span data-ttu-id="fea1c-115">In Progettazione query e Progettazione viste viene creata una clausola WHERE contenente una condizione OR analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="fea1c-115">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
    ```  
    SELECT job_lvl, hire_date  
    FROM employee  
    WHERE (job_lvl >= 200) OR   
      (hire_date < '01/01/1998')  
    ```  
  
4.  <span data-ttu-id="fea1c-116">Ripetere i passaggi 2 e 3 per tutte le altre condizioni da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="fea1c-116">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span> <span data-ttu-id="fea1c-117">Utilizzare una colonna **Or...** diversa per ogni nuova condizione.</span><span class="sxs-lookup"><span data-stu-id="fea1c-117">Use a different **Or...** column for each new condition.</span></span>  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="fea1c-118">Specifica di una condizione AND</span><span class="sxs-lookup"><span data-stu-id="fea1c-118">Specifying an AND Condition</span></span>  
 <span data-ttu-id="fea1c-119">Per estendere la ricerca a più colonne di dati con condizioni collegate con AND, inserire tutte le condizioni nella colonna **Filtro** della griglia.</span><span class="sxs-lookup"><span data-stu-id="fea1c-119">To search different data columns using conditions linked with AND, you put all the conditions in the **Filter** column of the grid.</span></span>  
  
#### <a name="to-specify-an-and-condition-for-two-different-columns"></a><span data-ttu-id="fea1c-120">Per specificare una condizione AND per due colonne diverse</span><span class="sxs-lookup"><span data-stu-id="fea1c-120">To specify an AND condition for two different columns</span></span>  
  
1.  <span data-ttu-id="fea1c-121">Nel [riquadro Criteri](visual-database-tools.md)aggiungere le colonne da includere nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="fea1c-121">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="fea1c-122">Nella colonna **Filtro** per la prima colonna di dati da includere nella ricerca specificare la prima condizione.</span><span class="sxs-lookup"><span data-stu-id="fea1c-122">In the **Filter** column for the first data column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="fea1c-123">Nella colonna **Filtro** per la seconda colonna di dati specificare la seconda condizione.</span><span class="sxs-lookup"><span data-stu-id="fea1c-123">In the **Filter** column for the second data column, specify the second condition.</span></span>  
  
     <span data-ttu-id="fea1c-124">In Progettazione query e Progettazione viste verrà creata una clausola WHERE contenente una condizione AND analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="fea1c-124">The Query and View Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
    ```  
    SELECT pub_id, title  
    FROM titles  
    WHERE (pub_id = '0877') AND (title LIKE '%Cook%')  
    ```  
  
4.  <span data-ttu-id="fea1c-125">Ripetere i passaggi 2 e 3 per tutte le altre condizioni da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="fea1c-125">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea1c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fea1c-126">See Also</span></span>  
 <span data-ttu-id="fea1c-127">[Combinare condizioni quando AND ha la precedenza &#40;Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fea1c-127">[Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fea1c-128">[Combinare condizioni quando OR ha la precedenza &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fea1c-128">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fea1c-129">[Convenzioni per la combinazione di condizioni di ricerca nel riquadro Criteri &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fea1c-129">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="fea1c-130">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fea1c-130">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
