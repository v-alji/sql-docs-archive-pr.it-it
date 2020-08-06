---
title: Creare outer join (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- joins [SQL Server], outer
ms.assetid: 18de47b1-f936-427d-b852-fe6d20334f71
author: stevestein
ms.author: sstein
ms.openlocfilehash: f02c0be049e2e75e1a657bb3c027d20430d562cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725208"
---
# <a name="create-outer-joins-visual-database-tools"></a><span data-ttu-id="ae4c9-102">Creazione di join esterni (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ae4c9-102">Create Outer Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="ae4c9-103">Per impostazione predefinita, in [Progettazione query e Progettazione viste](visual-database-tools.md) viene creato un inner join tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-103">By default, the [Query and View Designer](visual-database-tools.md) creates an inner join between tables.</span></span> <span data-ttu-id="ae4c9-104">Le righe prive di corrispondenza nell'altra tabella vengono eliminate.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-104">Inner joins eliminate the rows that do not match with a row from the other table.</span></span> <span data-ttu-id="ae4c9-105">Gli outer join restituiscono invece tutte le righe di almeno una delle tabelle o viste specificate nella clausola FROM, a condizione che tali righe soddisfino una delle condizioni di ricerca della clausola WHERE o HAVING.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-105">Outer joins, however, return all rows from at least one of the tables or views mentioned in the FROM clause, as long as those rows meet any WHERE or HAVING search conditions.</span></span> <span data-ttu-id="ae4c9-106">Se si desidera includere nel set di risultati le righe di dati che non hanno una corrispondenza nella tabella in join, sarà possibile creare un outer join.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-106">If you want to include data rows in the result set that do not have a match in the joined table, you can create an outer join.</span></span>  
  
 <span data-ttu-id="ae4c9-107">Durante la creazione di un outer join, l'ordine di inserimento delle tabelle nell'istruzione SQL (riflesso nel riquadro SQL) è significativo.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-107">When you create an outer join, the order in which tables appear in the SQL statement (as reflected in the SQL pane) is significant.</span></span> <span data-ttu-id="ae4c9-108">La prima tabella aggiunta diventa la tabella di sinistra ("left") e la seconda diventa la tabella di destra ("right").</span><span class="sxs-lookup"><span data-stu-id="ae4c9-108">The first table you add becomes the "left" table and the second table becomes the "right" table.</span></span> <span data-ttu-id="ae4c9-109">Non è invece significativo l'ordine effettivo in cui le tabelle sono visualizzate nel [riquadro Diagramma](diagram-pane-visual-database-tools.md) . Quando si specifica un left outer join o un right outer join, si fa riferimento alla sequenza di inserimento delle tabelle nella query o all'ordine in cui vengono visualizzate nell'istruzione SQL nel [riquadro SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ae4c9-109">(The actual order in which the tables appear in the [Diagram pane](diagram-pane-visual-database-tools.md) is not significant.) When you specify a left or right outer join, you are referring to the order in which the tables were added to the query and to the order in which they appear in the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-an-outer-join"></a><span data-ttu-id="ae4c9-110">Per creare un outer join</span><span class="sxs-lookup"><span data-stu-id="ae4c9-110">To create an outer join</span></span>  
  
1.  <span data-ttu-id="ae4c9-111">Creare un join, automaticamente o manualmente.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-111">Create the join, either automatically or manually.</span></span> <span data-ttu-id="ae4c9-112">Per informazioni dettagliate, vedere [Unione di tabelle in modo automatico &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) o [Unione di tabelle in modo manuale &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ae4c9-112">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) or [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="ae4c9-113">Selezionare la linea di join nel riquadro Diagramma e scegliere **Seleziona tutte le righe da**  dal menu **Progettazione query\<tablename>** . Il comando da scegliere è quello relativo alla tabella contenente le righe supplementari da inserire.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-113">Select the join line in the Diagram pane, and then from the **Query Designer** menu, choose **Select All Rows from \<tablename>**, selecting the command that includes the table whose extra rows you want to include.</span></span>  
  
    -   <span data-ttu-id="ae4c9-114">Scegliere la prima tabella per creare un left outer join.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-114">Choose the first table to create a left outer join.</span></span>  
  
    -   <span data-ttu-id="ae4c9-115">Scegliere la seconda tabella per creare un right outer join.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-115">Choose the second table to create a right outer join.</span></span>  
  
    -   <span data-ttu-id="ae4c9-116">Scegliere entrambe le tabelle per creare un full outer join.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-116">Choose both tables to create a full outer join.</span></span>  
  
 <span data-ttu-id="ae4c9-117">Quando si specifica un outer join, la linea di join verrà modificata automaticamente a indicare l'outer join.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-117">When you specify an outer join, the Query and View Designer modifies the join line to indicate an outer join.</span></span>  
  
 <span data-ttu-id="ae4c9-118">Inoltre, l'istruzione SQL nel riquadro SQL verrà modificata in modo da riflettere la modifica del tipo di join, come mostrato nella seguente istruzione:</span><span class="sxs-lookup"><span data-stu-id="ae4c9-118">In addition, the Query and View Designer modifies the SQL statement in the SQL pane to reflect the change in join type, as shown in the following statement:</span></span>  
  
```  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
```  
  
 <span data-ttu-id="ae4c9-119">Dato che l'outer join include le righe prive di corrispondenza, è possibile utilizzarlo per trovare le righe che violano vincoli di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-119">Because an outer join includes unmatched rows, you can use it to find rows that violate foreign key constraints.</span></span> <span data-ttu-id="ae4c9-120">Per eseguire questa operazione, è possibile creare un outer join, quindi aggiungere una condizione di ricerca che consenta di trovare le righe in cui la colonna chiave primaria della tabella a destra sia di tipo Null.</span><span class="sxs-lookup"><span data-stu-id="ae4c9-120">To do so, you create an outer join and then add a search condition to find rows in which the primary key column of the rightmost table is null.</span></span> <span data-ttu-id="ae4c9-121">L'outer join illustrato di seguito consente ad esempio di trovare nella tabella `employee` le righe a cui non corrisponde alcuna riga nella tabella `jobs` :</span><span class="sxs-lookup"><span data-stu-id="ae4c9-121">For example, the following outer join finds rows in the `employee` table that do not have corresponding rows in the `jobs` table:</span></span>  
  
```  
SELECT employee.emp_id, employee.job_id  
FROM employee LEFT OUTER JOIN jobs   
   ON employee.job_id = jobs.job_id  
WHERE (jobs.job_id IS NULL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae4c9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae4c9-122">See Also</span></span>  
 <span data-ttu-id="ae4c9-123">[Eseguire query con join &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ae4c9-123">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ae4c9-124">Finestra di dialogo Join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ae4c9-124">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
