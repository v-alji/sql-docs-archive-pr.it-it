---
title: Creare self-join in modo manuale (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- self-joins
- manual joins [SQL Server]
- joins [SQL Server], self
ms.assetid: 910ed516-cb84-481b-95d0-cba3e89afdba
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31e125fdfe0f7f285ea679cfe85356d1aa10353a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629700"
---
# <a name="create-self-joins-manually-visual-database-tools"></a><span data-ttu-id="43db4-102">Creazione di self-join in modo manuale (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="43db4-102">Create Self-Joins Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="43db4-103">È possibile unire in join una tabella con se stessa anche se questa non ha una relazione riflessiva nel database.</span><span class="sxs-lookup"><span data-stu-id="43db4-103">You can join a table to itself even if the table does not have a reflexive relationship in the database.</span></span> <span data-ttu-id="43db4-104">È ad esempio possibile utilizzare un self-join per individuare coppie di autori che risiedono nella stessa città.</span><span class="sxs-lookup"><span data-stu-id="43db4-104">For example, you can use a self-join to find pairs of authors living in the same city.</span></span>  
  
 <span data-ttu-id="43db4-105">Come per tutti i tipi di join, un self-join richiede almeno due tabelle,</span><span class="sxs-lookup"><span data-stu-id="43db4-105">As with any join, a self-join requires at least two tables.</span></span> <span data-ttu-id="43db4-106">con la differenza che, anziché aggiungere una seconda tabella alla query, si aggiungerà una seconda istanza della stessa tabella.</span><span class="sxs-lookup"><span data-stu-id="43db4-106">The difference is that, instead of adding a second table to the query, you add a second instance of the same table.</span></span> <span data-ttu-id="43db4-107">Sarà così possibile confrontare una colonna nella prima istanza della tabella con la stessa colonna nella seconda istanza, in modo da confrontare fra loro i valori contenuti in una colonna.</span><span class="sxs-lookup"><span data-stu-id="43db4-107">That way, you can compare a column in the first instance of the table to the same column in the second instance, which allows you to compare the values in a column to each other.</span></span> <span data-ttu-id="43db4-108">In [Progettazione query e Progettazione viste](visual-database-tools.md) verrà assegnato un alias alla seconda istanza della tabella.</span><span class="sxs-lookup"><span data-stu-id="43db4-108">The [Query and View Designer](visual-database-tools.md) assigns an alias to the second instance of the table.</span></span>  
  
 <span data-ttu-id="43db4-109">Se ad esempio si crea un self-join per trovare tutte le coppie di autori di Berkeley, verrà confrontata la colonna `city` nella prima istanza della tabella con la colonna `city` nella seconda istanza.</span><span class="sxs-lookup"><span data-stu-id="43db4-109">For example, if you are creating a self-join to find all pairs of authors within Berkeley, you compare the `city` column in the first instance of the table against the `city` column in the second instance.</span></span> <span data-ttu-id="43db4-110">La query risultante potrebbe essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="43db4-110">The resulting query might look like the following:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="43db4-111">La creazione di un self-join spesso richiede più condizioni di join.</span><span class="sxs-lookup"><span data-stu-id="43db4-111">Creating a self-join often requires multiple join conditions.</span></span> <span data-ttu-id="43db4-112">Il risultato della query precedente può essere utile per comprenderne la motivazione:</span><span class="sxs-lookup"><span data-stu-id="43db4-112">To understand why, consider the result of the preceding query:</span></span>  
  
```  
Cheryl Carson       Cheryl Carson  
Abraham Bennet      Abraham Bennet  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="43db4-113">La prima riga è inutile: indica che Cheryl Carson vive nella stessa città di Cheryl Carson.</span><span class="sxs-lookup"><span data-stu-id="43db4-113">The first row is useless; it indicates that Cheryl Carson lives in the same city as Cheryl Carson.</span></span> <span data-ttu-id="43db4-114">Altrettanto inutile è la seconda riga.</span><span class="sxs-lookup"><span data-stu-id="43db4-114">The second row is equally useless.</span></span> <span data-ttu-id="43db4-115">Per eliminare questi dati inutili, è possibile aggiungere un'altra condizione che consenta di conservare solo i risultati in cui i due nomi identificano autori diversi.</span><span class="sxs-lookup"><span data-stu-id="43db4-115">To eliminate this useless data, you add another condition retaining only those result rows in which the two author names describe different authors.</span></span> <span data-ttu-id="43db4-116">La query risultante sarà analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="43db4-116">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             <> authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="43db4-117">Il set di risultati è migliorato:</span><span class="sxs-lookup"><span data-stu-id="43db4-117">The result set is improved:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="43db4-118">Le due righe di risultati, tuttavia, sono ridondanti.</span><span class="sxs-lookup"><span data-stu-id="43db4-118">But the two result rows are redundant.</span></span> <span data-ttu-id="43db4-119">La prima dice che Carson vive nella stessa città di Bennet e la seconda dice che Bennet vive nella stessa città di Carson.</span><span class="sxs-lookup"><span data-stu-id="43db4-119">The first says Carson lives in the same city as Bennet, and the second says the Bennet lives in the same city as Carson.</span></span> <span data-ttu-id="43db4-120">Per eliminare questa ridondanza, è possibile modificare la seconda condizione di join da "non uguale" a "minore di".</span><span class="sxs-lookup"><span data-stu-id="43db4-120">To eliminate this redundancy, you can alter the second join condition from "not equals" to "less than."</span></span> <span data-ttu-id="43db4-121">La query risultante sarà analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="43db4-121">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             < authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="43db4-122">Si otterrà così un set di risultati analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="43db4-122">And the result set looks like this:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
```  
  
### <a name="to-create-a-self-join-manually"></a><span data-ttu-id="43db4-123">Per creare manualmente un self-join</span><span class="sxs-lookup"><span data-stu-id="43db4-123">To create a self-join manually</span></span>  
  
1.  <span data-ttu-id="43db4-124">Aggiungere la tabella o l'oggetto con valori di tabella al riquadro [Diagramma](diagram-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="43db4-124">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the table or table-valued object you want to work with.</span></span>  
  
2.  <span data-ttu-id="43db4-125">Aggiungere nuovamente la stessa tabella o lo stesso oggetto con valori di tabella in modo che venga visualizzato due volte nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="43db4-125">Add the same table again, so that the Diagram pane shows the same table or table-valued object twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="43db4-126">Un alias verrà assegnato alla seconda istanza aggiungendo un numero sequenziale al nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="43db4-126">The Query and View Designer assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="43db4-127">Verrà inoltre inserita una linea di join tra le due occorrenze della tabella o dell'oggetto con valori di tabella all'interno del riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="43db4-127">In addition, the Query and View Designer creates a join line between the two occurrences of the table or table-valued object within the Diagram pane.</span></span>  
  
3.  <span data-ttu-id="43db4-128">Fare clic con il pulsante destro del mouse sulla linea di join e scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="43db4-128">Right-click the join line and choose **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="43db4-129">Nella finestra Proprietà fare clic su **Condizione e tipo di join** e sui **puntini di sospensione (...)** a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="43db4-129">In the Properties window click **Join Condition and Type** and click the **ellipses (...)** to the right of the property.</span></span>  
  
5.  <span data-ttu-id="43db4-130">Nella [finestra di dialogo Join](join-dialog-box-visual-database-tools.md) cambiare l'operatore di confronto tra le chiavi primarie secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="43db4-130">In the [Join Dialog Box](join-dialog-box-visual-database-tools.md) change the comparison operator between the primary keys as required.</span></span> <span data-ttu-id="43db4-131">È ad esempio possibile modificare l'operatore minore di (<).</span><span class="sxs-lookup"><span data-stu-id="43db4-131">For example, you might change the operator to less than (<).</span></span>  
  
6.  <span data-ttu-id="43db4-132">Creare l'altra condizione di join, ad esempio authors.zip = authors1.zip, trascinando il nome della colonna join primaria nella prima occorrenza della tabella o dell'oggetto con valori di tabella e rilasciandolo sulla colonna corrispondente nella seconda occorrenza.</span><span class="sxs-lookup"><span data-stu-id="43db4-132">Create the additional join condition (for example, authors.zip = authors1.zip) by dragging the name of the primary join column in the first occurrence of the table or table-valued object and dropping it on the corresponding column in the second occurrence.</span></span>  
  
7.  <span data-ttu-id="43db4-133">Specificare le altre opzioni per la query, quali le colonne di output, le condizioni di ricerca e il criterio di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="43db4-133">Specify other options for the query such as output columns, search conditions, and sort order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43db4-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43db4-134">See Also</span></span>  
 <span data-ttu-id="43db4-135">[Creazione di self-join automaticamente &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="43db4-135">[Create Self-Joins Automatically &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="43db4-136">Eseguire query con join &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="43db4-136">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
