---
title: Creazione di viste e stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating views and stored procedures
ms.assetid: 53a0426d-07d8-4b7c-aa21-22632753bad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 76f6ecec446536191e8be4b05547ba5fd44c9d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711411"
---
# <a name="creating-views-and-stored-procedures"></a><span data-ttu-id="a0b06-102">Creazione di viste e stored procedure</span><span class="sxs-lookup"><span data-stu-id="a0b06-102">Creating Views and Stored Procedures</span></span>
  <span data-ttu-id="a0b06-103">Dopo aver concesso all'utente Mary l'accesso al database **TestData** è possibile creare alcuni oggetti di database, ad esempio una vista e una stored procedure, quindi concedere a Mary l'accesso a tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="a0b06-103">Now that Mary can access the **TestData** database, you may want to create some database objects, such as a view and a stored procedure, and then grant Mary access to them.</span></span> <span data-ttu-id="a0b06-104">Una vista è costituita da un'istruzione SELECT, mentre una stored procedure da una o più istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] eseguite in un batch.</span><span class="sxs-lookup"><span data-stu-id="a0b06-104">A view is a stored SELECT statement, and a stored procedure is one or more [!INCLUDE[tsql](../includes/tsql-md.md)] statements that execute as a batch.</span></span>  
  
 <span data-ttu-id="a0b06-105">Sulle viste è possibile eseguire query come con le tabelle, ad eccezione del fatto che le viste non accettano parametri.</span><span class="sxs-lookup"><span data-stu-id="a0b06-105">Views are queried like tables and do not accept parameters.</span></span> <span data-ttu-id="a0b06-106">Le stored procedure sono più complesse delle viste</span><span class="sxs-lookup"><span data-stu-id="a0b06-106">Stored procedures are more complex than views.</span></span> <span data-ttu-id="a0b06-107">e possono avere parametri di input e output, nonché contenere istruzioni per controllare il flusso del codice, ad esempio istruzioni IF e WHILE.</span><span class="sxs-lookup"><span data-stu-id="a0b06-107">Stored procedures can have both input and output parameters and can contain statements to control the flow of the code, such as IF and WHILE statements.</span></span> <span data-ttu-id="a0b06-108">È consigliabile dal punto di vista della programmazione utilizzare le stored procedure per tutte le azioni ripetitive sul database.</span><span class="sxs-lookup"><span data-stu-id="a0b06-108">It is good programming practice to use stored procedures for all repetitive actions in the database.</span></span>  
  
 <span data-ttu-id="a0b06-109">In questo esempio si userà CREATE VIEW per creare una vista che seleziona solo due delle colonne incluse nella tabella **Products** .</span><span class="sxs-lookup"><span data-stu-id="a0b06-109">For this example, you will use CREATE VIEW to create a view that selects only two of the columns in the **Products** table.</span></span> <span data-ttu-id="a0b06-110">Si utilizzerà quindi CREATE PROCEDURE per creare una stored procedure che accetta un parametro di prezzo e restituisce solo i prodotti il cui costo è inferiore al valore di tale parametro.</span><span class="sxs-lookup"><span data-stu-id="a0b06-110">Then, you will use CREATE PROCEDURE to create a stored procedure that accepts a price parameter and returns only those products that cost less than the specified parameter value.</span></span>  
  
### <a name="to-create-a-view"></a><span data-ttu-id="a0b06-111">Per creare una vista</span><span class="sxs-lookup"><span data-stu-id="a0b06-111">To create a view</span></span>  
  
1.  <span data-ttu-id="a0b06-112">Eseguire l'istruzione seguente per creare un vista molto semplice che esegue un'istruzione SELECT e restituisce i nomi e i prezzi dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="a0b06-112">Execute the following statement to create a very simple view that executes a select statement, and returns the names and prices of our products to the user.</span></span>  
  
    ```  
    CREATE VIEW vw_Names  
       AS  
       SELECT ProductName, Price FROM Products;  
    GO  
  
    ```  
  
### <a name="test-the-view"></a><span data-ttu-id="a0b06-113">Test della vista</span><span class="sxs-lookup"><span data-stu-id="a0b06-113">Test the view</span></span>  
  
1.  <span data-ttu-id="a0b06-114">Le viste vengono utilizzate in modo analogo alle tabelle.</span><span class="sxs-lookup"><span data-stu-id="a0b06-114">Views are treated just like tables.</span></span> <span data-ttu-id="a0b06-115">Utilizzare un'istruzione `SELECT` per accedere a una vista.</span><span class="sxs-lookup"><span data-stu-id="a0b06-115">Use a `SELECT` statement to access a view.</span></span>  
  
    ```  
    SELECT * FROM vw_Names;  
    GO  
  
    ```  
  
### <a name="to-create-a-stored-procedure"></a><span data-ttu-id="a0b06-116">Per creare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="a0b06-116">To create a stored procedure</span></span>  
  
1.  <span data-ttu-id="a0b06-117">L'istruzione seguente crea una stored procedure denominata `pr_Names`che accetta un parametro di input denominato `@VarPrice` con tipo di dati `money`.</span><span class="sxs-lookup"><span data-stu-id="a0b06-117">The following statement creates a stored procedure name `pr_Names`, accepts an input parameter named `@VarPrice` of data type `money`.</span></span> <span data-ttu-id="a0b06-118">La stored procedure visualizza il testo `Products less than` concatenata al parametro di input modificato da tipo di dati `money` in tipo di dati carattere `varchar(10)` .</span><span class="sxs-lookup"><span data-stu-id="a0b06-118">The stored procedure prints the statement `Products less than` concatenated with the input parameter that is changed from the `money` data type into a `varchar(10)` character data type.</span></span> <span data-ttu-id="a0b06-119">La procedura esegue quindi un'istruzione `SELECT` sulla vista, passando il parametro di input come parte della clausola `WHERE` .</span><span class="sxs-lookup"><span data-stu-id="a0b06-119">Then, the procedure executes a `SELECT` statement on the view, passing the input parameter as part of the `WHERE` clause.</span></span> <span data-ttu-id="a0b06-120">Ciò restituisce tutti i prodotti il cui costo è inferiore al valore del parametro di input.</span><span class="sxs-lookup"><span data-stu-id="a0b06-120">This returns all products that cost less than the input parameter value.</span></span>  
  
    ```  
    CREATE PROCEDURE pr_Names @VarPrice money  
       AS  
       BEGIN  
          -- The print statement returns text to the user  
          PRINT 'Products less than ' + CAST(@VarPrice AS varchar(10));  
          -- A second statement starts here  
          SELECT ProductName, Price FROM vw_Names  
                WHERE Price < @varPrice;  
       END  
    GO  
  
    ```  
  
### <a name="test-the-stored-procedure"></a><span data-ttu-id="a0b06-121">Test della stored procedure</span><span class="sxs-lookup"><span data-stu-id="a0b06-121">Test the stored procedure</span></span>  
  
1.  <span data-ttu-id="a0b06-122">Per testare la stored procedure, digitare ed eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="a0b06-122">To test the stored procedure, type and execute the following statement.</span></span> <span data-ttu-id="a0b06-123">La procedura restituirà i nomi di due prodotti immessi nella tabella `Products` nella lezione 1 con prezzo inferiore a `10.00`.</span><span class="sxs-lookup"><span data-stu-id="a0b06-123">The procedure should return the names of the two products entered into the `Products` table in Lesson 1 with a price that is less than `10.00`.</span></span>  
  
    ```  
    EXECUTE pr_Names 10.00;  
    GO  
  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a0b06-124">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="a0b06-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a0b06-125">Concessione dell'accesso a un oggetto di database</span><span class="sxs-lookup"><span data-stu-id="a0b06-125">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0b06-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0b06-126">See Also</span></span>  
 <span data-ttu-id="a0b06-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a0b06-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 [<span data-ttu-id="a0b06-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a0b06-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
