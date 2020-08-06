---
title: Esercitazione per la lettura dei dati di una tabella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- reading data in a table
ms.assetid: 532232c9-3d41-45cd-9150-de67a1cbfcf5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4bdaaeeddf8f35792c536624abfe6ff11b2dbd2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630184"
---
# <a name="reading-the-data-in-a-table-tutorial"></a><span data-ttu-id="d860e-102">Esercitazione per la lettura dei dati di una tabella</span><span class="sxs-lookup"><span data-stu-id="d860e-102">Reading the Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="d860e-103">Utilizzare l'istruzione SELECT per leggere i dati archiviati in una tabella.</span><span class="sxs-lookup"><span data-stu-id="d860e-103">Use the SELECT statement to read the data in a table.</span></span> <span data-ttu-id="d860e-104">L'istruzione SELECT è una delle più importanti istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] e la relativa sintassi presenta numerose variazioni.</span><span class="sxs-lookup"><span data-stu-id="d860e-104">The SELECT statement is one of the most important [!INCLUDE[tsql](../includes/tsql-md.md)] statements, and there are many variations in the syntax.</span></span> <span data-ttu-id="d860e-105">Ai fini di questa esercitazione ne verranno utilizzate cinque semplici versioni.</span><span class="sxs-lookup"><span data-stu-id="d860e-105">For this tutorial, you will work with five simple versions.</span></span>  
  
### <a name="to-read-the-data-in-a-table"></a><span data-ttu-id="d860e-106">Per leggere i dati archiviati in una tabella</span><span class="sxs-lookup"><span data-stu-id="d860e-106">To read the data in a table</span></span>  
  
1.  <span data-ttu-id="d860e-107">Per leggere i dati archiviati nella tabella `Products` , digitare ed eseguire le istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d860e-107">Type and execute the following statements to read the data in the `Products` table.</span></span>  
  
    ```  
    -- The basic syntax for reading data from a single table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
    GO  
  
    ```  
  
2.  <span data-ttu-id="d860e-108">È possibile utilizzare un asterisco per selezionare tutte le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="d860e-108">You can use an asterisk to select all the columns in the table.</span></span> <span data-ttu-id="d860e-109">Si tratta di una tecnica utilizzata spesso nelle query ad hoc.</span><span class="sxs-lookup"><span data-stu-id="d860e-109">This is often used in ad hoc queries.</span></span> <span data-ttu-id="d860e-110">È consigliabile specificare l'elenco delle colonne nel codice permanente in modo che l'istruzione restituisca le colonne previste anche se viene successivamente aggiunta una nuova colonna alla tabella.</span><span class="sxs-lookup"><span data-stu-id="d860e-110">You should provide the column list in you permanent code so that the statement will return the predicted columns, even if a new column is added to the table later.</span></span>  
  
    ```  
    -- Returns all columns in the table  
    -- Does not use the optional schema, dbo  
    SELECT * FROM Products  
    GO  
  
    ```  
  
3.  <span data-ttu-id="d860e-111">È possibile omettere le colonne che non si desidera vengano restituite.</span><span class="sxs-lookup"><span data-stu-id="d860e-111">You can omit columns that you do not want to return.</span></span> <span data-ttu-id="d860e-112">Le colonne verranno restituite nell'ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="d860e-112">The columns will be returned in the order that they are listed.</span></span>  
  
    ```  
    -- Returns only two of the columns from the table  
    SELECT ProductName, Price  
        FROM dbo.Products  
    GO  
  
    ```  
  
4.  <span data-ttu-id="d860e-113">Utilizzare una clausola `WHERE` per limitare le righe restituite.</span><span class="sxs-lookup"><span data-stu-id="d860e-113">Use a `WHERE` clause to limit the rows that are returned to the user.</span></span>  
  
    ```  
    -- Returns only two of the records in the table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
        WHERE ProductID < 60  
    GO  
  
    ```  
  
5.  <span data-ttu-id="d860e-114">È possibile utilizzare i valori nelle colonne quando vengono restituiti.</span><span class="sxs-lookup"><span data-stu-id="d860e-114">You can work with the values in the columns as they are returned.</span></span> <span data-ttu-id="d860e-115">L'esempio seguente esegue un'operazione matematica sulla colonna `Price` .</span><span class="sxs-lookup"><span data-stu-id="d860e-115">The following example performs a mathematical operation on the `Price` column.</span></span> <span data-ttu-id="d860e-116">Alle colonne modificate in questo modo non verrà assegnato un nome a meno che non se ne specifichi uno utilizzando la parola chiave `AS` .</span><span class="sxs-lookup"><span data-stu-id="d860e-116">Columns that have been changed in this way will not have a name unless you provide one by using the `AS` keyword.</span></span>  
  
    ```  
    -- Returns ProductName and the Price including a 7% tax  
    -- Provides the name CustomerPays for the calculated column  
    SELECT ProductName, Price * 1.07 AS CustomerPays  
        FROM dbo.Products  
    GO  
    ```  
  
## <a name="functions-that-are-useful-in-a-select-statement"></a><span data-ttu-id="d860e-117">Funzioni utili in un'istruzione SELECT</span><span class="sxs-lookup"><span data-stu-id="d860e-117">Functions That Are Useful in a SELECT Statement</span></span>  
 <span data-ttu-id="d860e-118">Per informazioni su alcune funzioni che consentono di utilizzare i dati in un'istruzione SELECT, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d860e-118">For information about some functions that you can use to work with data in SELECT statements, see the following topics:</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="d860e-119">Funzioni per i valori stringa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d860e-119">String Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/string-functions-transact-sql)|[<span data-ttu-id="d860e-120">Funzioni e tipi di dati di data e ora &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d860e-120">Date and Time Data Types and Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|  
|[<span data-ttu-id="d860e-121">Funzioni matematiche &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d860e-121">Mathematical Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)|[<span data-ttu-id="d860e-122">Funzioni per i valori text e image &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d860e-122">Text and Image Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/text-and-image-functions-textptr-transact-sql)|  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d860e-123">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="d860e-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d860e-124">Riepilogo: Creazione di oggetti di database</span><span class="sxs-lookup"><span data-stu-id="d860e-124">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="d860e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d860e-125">See Also</span></span>  
 [<span data-ttu-id="d860e-126">SELECT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d860e-126">SELECT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/select-transact-sql)  
  
  
