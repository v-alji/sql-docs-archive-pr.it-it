---
title: Inserimento e aggiornamento di dati in una tabella (esercitazione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- inserting and updating data
ms.assetid: 514dc87a-b829-43b5-8fc8-1a400a260284
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0646019f166e1c2cc126a4cc7d2ed8f27a7bd2f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630183"
---
# <a name="inserting-and-updating-data-in-a-table-tutorial"></a><span data-ttu-id="f02f3-102">Esercitazione per l'inserimento e l'aggiornamento dei dati in una tabella</span><span class="sxs-lookup"><span data-stu-id="f02f3-102">Inserting and Updating Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="f02f3-103">Dopo aver creato la tabella **Products** è possibile inserirvi dati con l'istruzione INSERT.</span><span class="sxs-lookup"><span data-stu-id="f02f3-103">Now that you have created the **Products** table, you are ready to insert data into the table by using the INSERT statement.</span></span> <span data-ttu-id="f02f3-104">Dopo aver inserito i dati, si procederà alla modifica del contenuto di una riga mediante l'istruzione UPDATE.</span><span class="sxs-lookup"><span data-stu-id="f02f3-104">After the data is inserted, you will change the content of a row by using an UPDATE statement.</span></span> <span data-ttu-id="f02f3-105">Per limitare l'operazione di aggiornamento a una sola riga verrà utilizzata la clausola WHERE dell'istruzione UPDATE.</span><span class="sxs-lookup"><span data-stu-id="f02f3-105">You will use the WHERE clause of the UPDATE statement to restrict the update to a single row.</span></span> <span data-ttu-id="f02f3-106">Le quattro istruzioni immetteranno i dati seguenti.</span><span class="sxs-lookup"><span data-stu-id="f02f3-106">The four statements will enter the following data.</span></span>  
  
|<span data-ttu-id="f02f3-107">ProductID</span><span class="sxs-lookup"><span data-stu-id="f02f3-107">ProductID</span></span>|<span data-ttu-id="f02f3-108">ProductName</span><span class="sxs-lookup"><span data-stu-id="f02f3-108">ProductName</span></span>|<span data-ttu-id="f02f3-109">Prezzo</span><span class="sxs-lookup"><span data-stu-id="f02f3-109">Price</span></span>|<span data-ttu-id="f02f3-110">ProductDescription</span><span class="sxs-lookup"><span data-stu-id="f02f3-110">ProductDescription</span></span>|  
|---------------|-----------------|-----------|------------------------|  
|<span data-ttu-id="f02f3-111">1</span><span class="sxs-lookup"><span data-stu-id="f02f3-111">1</span></span>|<span data-ttu-id="f02f3-112">Clamp</span><span class="sxs-lookup"><span data-stu-id="f02f3-112">Clamp</span></span>|<span data-ttu-id="f02f3-113">12.48</span><span class="sxs-lookup"><span data-stu-id="f02f3-113">12.48</span></span>|<span data-ttu-id="f02f3-114">Workbench clamp</span><span class="sxs-lookup"><span data-stu-id="f02f3-114">Workbench clamp</span></span>|  
|<span data-ttu-id="f02f3-115">50</span><span class="sxs-lookup"><span data-stu-id="f02f3-115">50</span></span>|<span data-ttu-id="f02f3-116">Screwdriver</span><span class="sxs-lookup"><span data-stu-id="f02f3-116">Screwdriver</span></span>|<span data-ttu-id="f02f3-117">3,17</span><span class="sxs-lookup"><span data-stu-id="f02f3-117">3.17</span></span>|<span data-ttu-id="f02f3-118">Flat head</span><span class="sxs-lookup"><span data-stu-id="f02f3-118">Flat head</span></span>|  
|<span data-ttu-id="f02f3-119">75</span><span class="sxs-lookup"><span data-stu-id="f02f3-119">75</span></span>|<span data-ttu-id="f02f3-120">Tire Bar</span><span class="sxs-lookup"><span data-stu-id="f02f3-120">Tire Bar</span></span>||<span data-ttu-id="f02f3-121">Tool for changing tires.</span><span class="sxs-lookup"><span data-stu-id="f02f3-121">Tool for changing tires.</span></span>|  
|<span data-ttu-id="f02f3-122">3000</span><span class="sxs-lookup"><span data-stu-id="f02f3-122">3000</span></span>|<span data-ttu-id="f02f3-123">3mm Bracket</span><span class="sxs-lookup"><span data-stu-id="f02f3-123">3mm Bracket</span></span>|<span data-ttu-id="f02f3-124">.52</span><span class="sxs-lookup"><span data-stu-id="f02f3-124">.52</span></span>||  
  
 <span data-ttu-id="f02f3-125">La sintassi di base è INSERT, nome tabella, elenco colonne, VALUES, a cui segue quindi un elenco dei valori da inserire.</span><span class="sxs-lookup"><span data-stu-id="f02f3-125">The basic syntax is: INSERT, table name, column list, VALUES, and then a list of the values to be inserted.</span></span> <span data-ttu-id="f02f3-126">I due trattini davanti a una riga indicano che si tratta di un commento il cui testo verrà ignorato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="f02f3-126">The two hyphens in front of a line indicate that the line is a comment and the text will be ignored by the compiler.</span></span> <span data-ttu-id="f02f3-127">In questo caso il commento descrive una variazione consentita della sintassi.</span><span class="sxs-lookup"><span data-stu-id="f02f3-127">In this case, the comment describes a permissible variation of the syntax.</span></span>  
  
### <a name="to-insert-data-into-a-table"></a><span data-ttu-id="f02f3-128">Per inserire dati in una tabella</span><span class="sxs-lookup"><span data-stu-id="f02f3-128">To insert data into a table</span></span>  
  
1.  <span data-ttu-id="f02f3-129">Eseguire l'istruzione seguente per inserire una riga nella tabella `Products` creata nell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="f02f3-129">Execute the following statement to insert a row into the `Products` table that was created in the previous task.</span></span> <span data-ttu-id="f02f3-130">Viene utilizzata la sintassi di base.</span><span class="sxs-lookup"><span data-stu-id="f02f3-130">This is the basic syntax.</span></span>  
  
    ```  
    -- Standard syntax  
    INSERT dbo.Products (ProductID, ProductName, Price, ProductDescription)  
        VALUES (1, 'Clamp', 12.48, 'Workbench clamp')  
    GO  
  
    ```  
  
2.  <span data-ttu-id="f02f3-131">L'istruzione seguente illustra come modificare l'ordine in cui vengono specificati i parametri scambiando la posizione di `ProductID` e `ProductName` in entrambi gli elenchi di campi (tra parentesi) e nell'elenco dei valori.</span><span class="sxs-lookup"><span data-stu-id="f02f3-131">The following statement shows how you can change the order in which the parameters are provided by switching the placement of the `ProductID` and `ProductName` in both the field list (in parentheses) and in the values list.</span></span>  
  
    ```  
    -- Changing the order of the columns  
    INSERT dbo.Products (ProductName, ProductID, Price, ProductDescription)  
        VALUES ('Screwdriver', 50, 3.17, 'Flat head')  
    GO  
  
    ```  
  
3.  <span data-ttu-id="f02f3-132">L'istruzione seguente illustra che i nomi delle colonne sono facoltativi a condizione che i valori siano elencati nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="f02f3-132">The following statement demonstrates that the names of the columns are optional, as long as the values are listed in the correct order.</span></span> <span data-ttu-id="f02f3-133">Questa sintassi comune non è tuttavia consigliata poiché potrebbe rendere il codice di difficile comprensione per gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="f02f3-133">This syntax is common but is not recommended because it might be harder for others to understand your code.</span></span> <span data-ttu-id="f02f3-134">`NULL` viene specificato per la colonna `Price` perché il prezzo del prodotto corrispondente non è ancora noto.</span><span class="sxs-lookup"><span data-stu-id="f02f3-134">`NULL` is specified for the `Price` column because the price for this product is not yet known.</span></span>  
  
    ```  
    -- Skipping the column list, but keeping the values in order  
    INSERT dbo.Products  
        VALUES (75, 'Tire Bar', NULL, 'Tool for changing tires.')  
    GO  
  
    ```  
  
4.  <span data-ttu-id="f02f3-135">Il nome dello schema è facoltativo a condizione che si acceda per la modifica a una tabella inclusa nello schema predefinito.</span><span class="sxs-lookup"><span data-stu-id="f02f3-135">The schema name is optional as long as you are accessing and changing a table in your default schema.</span></span> <span data-ttu-id="f02f3-136">Poiché la colonna `ProductDescription` supporta valori Null e non viene specificato alcun valore, il nome e il valore della colonna `ProductDescription` verranno eliminati completamente dall'istruzione.</span><span class="sxs-lookup"><span data-stu-id="f02f3-136">Because the `ProductDescription` column allows null values and no value is being provided, the `ProductDescription` column name and value can be dropped from the statement completely.</span></span>  
  
    ```  
    -- Dropping the optional dbo and dropping the ProductDescription column  
    INSERT Products (ProductID, ProductName, Price)  
        VALUES (3000, '3mm Bracket', .52)  
    GO  
    ```  
  
### <a name="to-update-the-products-table"></a><span data-ttu-id="f02f3-137">Per aggiornare la tabella Products</span><span class="sxs-lookup"><span data-stu-id="f02f3-137">To update the products table</span></span>  
  
1.  <span data-ttu-id="f02f3-138">Digitare ed eseguire l'istruzione `UPDATE` seguente per modificare il valore `ProductName` del secondo prodotto da `Screwdriver`in `Flat Head Screwdriver`.</span><span class="sxs-lookup"><span data-stu-id="f02f3-138">Type and execute the following `UPDATE` statement to change the `ProductName` of the second product from `Screwdriver`, to `Flat Head Screwdriver`.</span></span>  
  
    ```  
    UPDATE dbo.Products  
        SET ProductName = 'Flat Head Screwdriver'  
        WHERE ProductID = 50  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f02f3-139">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="f02f3-139">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f02f3-140">Lettura dei dati di una tabella &#40;esercitazione&#41;</span><span class="sxs-lookup"><span data-stu-id="f02f3-140">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="f02f3-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f02f3-141">See Also</span></span>  
 <span data-ttu-id="f02f3-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f02f3-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 [<span data-ttu-id="f02f3-143">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f02f3-143">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
