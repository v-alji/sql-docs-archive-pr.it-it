---
title: Creazione di una tabella (esercitazione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating tables
ms.assetid: 653f2dd3-36a2-4bd5-8703-71a57d244661
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c772f2527bd5ddb8a6759cbaa72d8aed9277f5cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630187"
---
# <a name="creating-a-table-tutorial"></a><span data-ttu-id="4957b-102">Esercitazione per la creazione di una tabella</span><span class="sxs-lookup"><span data-stu-id="4957b-102">Creating a Table (Tutorial)</span></span>
  <span data-ttu-id="4957b-103">Per creare una tabella, è necessario specificare un nome per la tabella e i nomi e i tipi di dati di ogni colonna di quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="4957b-103">To create a table, you must provide a name for the table, and the names and data types of each column in the table.</span></span> <span data-ttu-id="4957b-104">È inoltre consigliabile indicare se sono consentiti valori Null in ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="4957b-104">It is also a good practice to indicate whether null values are allowed in each column.</span></span>  
  
 <span data-ttu-id="4957b-105">La maggior parte delle tabelle dispone di una chiave primaria costituita da una o più colonne.</span><span class="sxs-lookup"><span data-stu-id="4957b-105">Most tables have a primary key, made up of one or more columns of the table.</span></span> <span data-ttu-id="4957b-106">La chiave primaria è sempre univoca.</span><span class="sxs-lookup"><span data-stu-id="4957b-106">A primary key is always unique.</span></span> <span data-ttu-id="4957b-107">In [!INCLUDE[ssDE](../includes/ssde-md.md)] è applicata la limitazione per la quale nessun valore di chiave primaria può essere ripetuto nella tabella.</span><span class="sxs-lookup"><span data-stu-id="4957b-107">The [!INCLUDE[ssDE](../includes/ssde-md.md)] will enforce the restriction that any primary key value cannot be repeated in the table.</span></span>  
  
 <span data-ttu-id="4957b-108">Per un elenco di tipi di dati e collegamenti alle relative descrizioni, vedere [Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4957b-108">For a list of data types and links for a description of each, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4957b-109">È possibile installare [!INCLUDE[ssDE](../includes/ssde-md.md)] in modo che venga fatta o meno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4957b-109">The [!INCLUDE[ssDE](../includes/ssde-md.md)] can be installed as case sensitive or non-case sensitive.</span></span> <span data-ttu-id="4957b-110">Se in [!INCLUDE[ssDE](../includes/ssde-md.md)] tale distinzione è rilevante, i nomi degli oggetti devono essere sempre indicati con le lettere maiuscole e minuscole appropriate.</span><span class="sxs-lookup"><span data-stu-id="4957b-110">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as case sensitive, object names must always have the same case.</span></span> <span data-ttu-id="4957b-111">Una tabella denominata OrderData è ad esempio diversa da una tabella denominata ORDERDATA.</span><span class="sxs-lookup"><span data-stu-id="4957b-111">For example, a table named OrderData is a different table from a table named ORDERDATA.</span></span> <span data-ttu-id="4957b-112">Se nel [!INCLUDE[ssDE](../includes/ssde-md.md)] non viene fatta distinzione tra maiuscole e minuscole, tali nomi sono considerati equivalenti e quindi il nome stesso può essere utilizzato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="4957b-112">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as non-case sensitive, those two table names are considered to be the same table, and that name can only be used one time.</span></span>  
  
### <a name="to-create-a-database-to-contain-the-new-table"></a><span data-ttu-id="4957b-113">Per creare un database in cui includere la nuova tabella</span><span class="sxs-lookup"><span data-stu-id="4957b-113">To create a database to contain the new table</span></span>  
  
-   <span data-ttu-id="4957b-114">Immettere il codice seguente in una finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="4957b-114">Enter the following code into a Query Editor window.</span></span>  
  
    ```  
    USE master;  
    GO  
  
    --Delete the TestData database if it exists.  
    IF EXISTS(SELECT * from sys.databases WHERE name='TestData')  
    BEGIN  
        DROP DATABASE TestData;  
    END  
  
    --Create a new database called TestData.  
    CREATE DATABASE TestData;  
    Press the F5 key to execute the code and create the database.  
    ```  
  
### <a name="switch-the-query-editor-connection-to-the-testdata-database"></a><span data-ttu-id="4957b-115">Connessione dell'editor di query al database TestData</span><span class="sxs-lookup"><span data-stu-id="4957b-115">Switch the Query Editor connection to the TestData database</span></span>  
  
-   <span data-ttu-id="4957b-116">Nella finestra dell'editor di query digitare ed eseguire il codice seguente per connettersi al database `TestData` .</span><span class="sxs-lookup"><span data-stu-id="4957b-116">In a Query Editor window, type and execute the following code to change your connection to the `TestData` database.</span></span>  
  
    ```  
    USE TestData  
    GO  
    ```  
  
### <a name="to-create-a-table"></a><span data-ttu-id="4957b-117">Per creare una tabella</span><span class="sxs-lookup"><span data-stu-id="4957b-117">To create a table</span></span>  
  
-   <span data-ttu-id="4957b-118">Nell'editor di query digitare ed eseguire il codice seguente per creare una tabella semplice denominata `Products`.</span><span class="sxs-lookup"><span data-stu-id="4957b-118">In a Query Editor window, type and execute the following code to create a simple table named `Products`.</span></span> <span data-ttu-id="4957b-119">Le colonne nella tabella vengono denominate `ProductID`, `ProductName`, `Price`e `ProductDescription`.</span><span class="sxs-lookup"><span data-stu-id="4957b-119">The columns in the table are named `ProductID`, `ProductName`, `Price`, and `ProductDescription`.</span></span> <span data-ttu-id="4957b-120">La colonna `ProductID` rappresenta la chiave primaria della tabella.</span><span class="sxs-lookup"><span data-stu-id="4957b-120">The `ProductID` column is the primary key of the table.</span></span> <span data-ttu-id="4957b-121">`int`, `varchar(25)`, `money`e `text` sono tutti tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="4957b-121">`int`, `varchar(25)`, `money`, and `text` are all data types.</span></span> <span data-ttu-id="4957b-122">Le uniche colonne che possono non contenere dati quando viene inserita o modificata un riga sono `Price` e `ProductionDescription` .</span><span class="sxs-lookup"><span data-stu-id="4957b-122">Only the `Price` and `ProductionDescription` columns can have no data when a row is inserted or changed.</span></span> <span data-ttu-id="4957b-123">Questa istruzione contiene un elemento facoltativo (`dbo.`) che corrisponde a uno schema.</span><span class="sxs-lookup"><span data-stu-id="4957b-123">This statement contains an optional element (`dbo.`) called a schema.</span></span> <span data-ttu-id="4957b-124">Lo schema rappresenta l'oggetto di database a cui appartiene la tabella.</span><span class="sxs-lookup"><span data-stu-id="4957b-124">The schema is the database object that owns the table.</span></span> <span data-ttu-id="4957b-125">Se si è un amministratore, `dbo` è lo schema predefinito.</span><span class="sxs-lookup"><span data-stu-id="4957b-125">If you are an administrator, `dbo` is the default schema.</span></span> <span data-ttu-id="4957b-126">`dbo` corrisponde al proprietario del database.</span><span class="sxs-lookup"><span data-stu-id="4957b-126">`dbo` stands for database owner.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products  
       (ProductID int PRIMARY KEY NOT NULL,  
        ProductName varchar(25) NOT NULL,  
        Price money NULL,  
        ProductDescription text NULL)  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4957b-127">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="4957b-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4957b-128">Inserimento e aggiornamento di dati in una tabella &#40;esercitazione&#41;</span><span class="sxs-lookup"><span data-stu-id="4957b-128">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](../t-sql/lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="4957b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4957b-129">See Also</span></span>  
 [<span data-ttu-id="4957b-130">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4957b-130">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
