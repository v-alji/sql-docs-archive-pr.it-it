---
title: Impostare o modificare le regole di confronto delle colonne | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tempdb database [SQL Server], collations
- collations [SQL Server], column
ms.assetid: d7a9638b-717c-4680-9b98-8849081e08be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8211569b6ce83faaec043e5eb527a60f0ddab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637909"
---
# <a name="set-or-change-the-column-collation"></a><span data-ttu-id="0627c-102">Impostare o modificare le regole di confronto delle colonne</span><span class="sxs-lookup"><span data-stu-id="0627c-102">Set or Change the Column Collation</span></span>
  <span data-ttu-id="0627c-103">È possibile ignorare le regole di confronto del database per i dati `char`, `varchar`, `text`, `nchar`, `nvarchar` e `ntext` specificando regole di confronto diverse per una colonna specifica di una tabella e utilizzando uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0627c-103">You can override the database collation for `char`, `varchar`, `text`, `nchar`, `nvarchar`, and `ntext` data by specifying a different collation for a specific column of a table and using one of the following:</span></span>  
  
-   <span data-ttu-id="0627c-104">Clausola COLLATE di [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) e [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0627c-104">The COLLATE clause of [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) and [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span> <span data-ttu-id="0627c-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0627c-105">For example:</span></span>  
  
    ```  
    CREATE TABLE dbo.MyTable  
      (PrimaryKey   int PRIMARY KEY,  
       CharCol      varchar(10) COLLATE French_CI_AS NOT NULL  
      );  
    GO  
    ALTER TABLE dbo.MyTable ALTER COLUMN CharCol  
                varchar(10)COLLATE Latin1_General_CI_AS NOT NULL;  
    GO  
    ```  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="0627c-106">.</span><span class="sxs-lookup"><span data-stu-id="0627c-106">.</span></span> <span data-ttu-id="0627c-107">Per altre informazioni, vedere [Regole di confronto e supporto Unicode](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="0627c-107">For more information, [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="0627c-108">Utilizzo della `Column.Collation` Proprietà in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SMO (Management Objects).</span><span class="sxs-lookup"><span data-stu-id="0627c-108">Using the `Column.Collation` property in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="0627c-109">Non è possibile modificare le regole di confronto di una colonna a cui fa riferimento uno qualsiasi degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0627c-109">You cannot change the collation of a column that is currently referenced by any one of the following:</span></span>  
  
-   <span data-ttu-id="0627c-110">Una colonna calcolata</span><span class="sxs-lookup"><span data-stu-id="0627c-110">A computed column</span></span>  
  
-   <span data-ttu-id="0627c-111">Un indice</span><span class="sxs-lookup"><span data-stu-id="0627c-111">An index</span></span>  
  
-   <span data-ttu-id="0627c-112">Le statistiche di distribuzione, generate automaticamente o tramite l'istruzione CREATE STATISTICS</span><span class="sxs-lookup"><span data-stu-id="0627c-112">Distribution statistics, either generated automatically or by the CREATE STATISTICS statement</span></span>  
  
-   <span data-ttu-id="0627c-113">Un vincolo CHECK</span><span class="sxs-lookup"><span data-stu-id="0627c-113">A CHECK constraint</span></span>  
  
-   <span data-ttu-id="0627c-114">Un vincolo FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="0627c-114">A FOREIGN KEY constraint</span></span>  
  
 <span data-ttu-id="0627c-115">Quando si usa il database **tempdb**, la clausola [COLLATE](/sql/t-sql/statements/collations) include un'opzione *database_default* per specificare che una colonna di una tabella temporanea utilizza le regole di confronto predefinite del database utente corrente per la connessione anziché quelle del database **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0627c-115">When you work with **tempdb**, the [COLLATE](/sql/t-sql/statements/collations) clause includes a *database_default* option to specify that a column in a temporary table uses the collation default of the current user database for the connection instead of the collation of **tempdb**.</span></span>  
  
## <a name="collations-and-text-columns"></a><span data-ttu-id="0627c-116">Regole di confronto e colonne di tipo text</span><span class="sxs-lookup"><span data-stu-id="0627c-116">Collations and text Columns</span></span>  
 <span data-ttu-id="0627c-117">È possibile inserire o aggiornare valori in una colonna `text` le cui regole di confronto sono diverse dalla tabella codici delle regole di confronto predefinite del database.</span><span class="sxs-lookup"><span data-stu-id="0627c-117">You can insert or update values in a `text` column whose collation is different from the code page of the default collation of the database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0627c-118">converte in modo implicito i valori nelle regole di confronto della colonna.</span><span class="sxs-lookup"><span data-stu-id="0627c-118">implicitly converts the values to the collation of the column.</span></span>  
  
## <a name="collations-and-tempdb"></a><span data-ttu-id="0627c-119">Regole di confronto e database tempdb</span><span class="sxs-lookup"><span data-stu-id="0627c-119">Collations and tempdb</span></span>  
 <span data-ttu-id="0627c-120">Il database **tempdb** viene compilato a ogni avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e presenta le stesse regole di confronto predefinite del database **model** .</span><span class="sxs-lookup"><span data-stu-id="0627c-120">The **tempdb** database is built every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started and has the same default collation as the **model** database.</span></span> <span data-ttu-id="0627c-121">Queste sono generalmente le stesse regole di confronto predefinite dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="0627c-121">This is typically the same as the default collation of the instance.</span></span> <span data-ttu-id="0627c-122">Se si crea un database utente e si specificano regole di confronto predefinite diverse da quelle del database **model**, il database utente utilizzerà regole di confronto predefinite diverse da quelle di **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0627c-122">If you create a user database and specify a different default collation than **model**, the user database has a different default collation than **tempdb**.</span></span> <span data-ttu-id="0627c-123">Tutte le stored procedure temporanee o le tabelle temporanee vengono create e archiviate in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0627c-123">All temporary stored procedures or temporary tables are created and stored in **tempdb**.</span></span> <span data-ttu-id="0627c-124">Di conseguenza, tutte le colonne implicite delle tabelle temporanee e tutte le costanti, le variabili e i parametri a cui possono essere assegnati valori predefiniti e che si trovano in stored procedure temporanee, utilizzano regole di confronto diverse da quelle degli oggetti analoghi creati in tabelle e stored procedure permanenti.</span><span class="sxs-lookup"><span data-stu-id="0627c-124">This means that all implicit columns in temporary tables and all coercible-default constants, variables, and parameters in temporary stored procedures have collations that are different from comparable objects created in permanent tables and stored procedures.</span></span>  
  
 <span data-ttu-id="0627c-125">Ciò può causare problemi derivanti da una non corrispondenza nelle regole di confronto tra i database definiti dall'utente e gli oggetti di database del sistema.</span><span class="sxs-lookup"><span data-stu-id="0627c-125">This could lead to problems with a mismatch in collations between user-defined databases and system database objects.</span></span> <span data-ttu-id="0627c-126">Si supponga ad esempio che un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzi le regole di confronto Latin1_General_CS_AS e di eseguire le seguenti istruzioni:</span><span class="sxs-lookup"><span data-stu-id="0627c-126">For example, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the Latin1_General_CS_AS collation and you execute the following statements:</span></span>  
  
```  
CREATE DATABASE TestDB COLLATE Estonian_CS_AS;  
USE TestDB;  
CREATE TABLE TestPermTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
```  
  
 <span data-ttu-id="0627c-127">In questo sistema nel database **tempdb** vengono utilizzate le regole di confronto Latin1_General_CS_AS con la tabella codici 1252, mentre in `TestDB` e `TestPermTab.Col1` vengono utilizzate le regole di confronto `Estonian_CS_AS` con la tabella codici 1257.</span><span class="sxs-lookup"><span data-stu-id="0627c-127">In this system, the **tempdb** database uses the Latin1_General_CS_AS collation with code page 1252, and `TestDB` and `TestPermTab.Col1` use the `Estonian_CS_AS` collation with code page 1257.</span></span> <span data-ttu-id="0627c-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0627c-128">For example:</span></span>  
  
```  
USE TestDB;  
GO  
-- Create a temporary table with the same column declarations  
-- as TestPermTab  
CREATE TABLE #TestTempTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
INSERT INTO #TestTempTab  
         SELECT * FROM TestPermTab;  
GO  
```  
  
 <span data-ttu-id="0627c-129">Con l'esempio precedente, il database **tempdb** utilizza le regole di confronto Latin1_General_CS_AS, mentre `TestDB` e `TestTab.Col1` utilizzano le regole di confronto `Estonian_CS_AS` .</span><span class="sxs-lookup"><span data-stu-id="0627c-129">With the previous example, the **tempdb** database uses the Latin1_General_CS_AS collation, and `TestDB` and `TestTab.Col1` use the `Estonian_CS_AS` collation.</span></span> <span data-ttu-id="0627c-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0627c-130">For example:</span></span>  
  
```  
SELECT * FROM TestPermTab AS a INNER JOIN #TestTempTab on a.Col1 = #TestTempTab.Col1;  
```  
  
 <span data-ttu-id="0627c-131">Poiché **tempdb** utilizza le regole di confronto predefinite del server e `TestPermTab.Col1` utilizza regole di confronto diverse, in SQL Server viene restituito un errore in cui viene indicato che è impossibile risolvere il conflitto delle regole di confronto tra Latin1_General_CI_AS_KS_WS ed Estonian_CS_AS nell'operazione.</span><span class="sxs-lookup"><span data-stu-id="0627c-131">Because **tempdb** uses the default server collation and `TestPermTab.Col1` uses a different collation, SQL Server returns this error: "Cannot resolve collation conflict between 'Latin1_General_CI_AS_KS_WS' and 'Estonian_CS_AS' in equal to operation."</span></span>  
  
 <span data-ttu-id="0627c-132">Per evitare l'errore è possibile utilizzare una delle alternative seguenti:</span><span class="sxs-lookup"><span data-stu-id="0627c-132">To prevent the error, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="0627c-133">Specificare che per la colonna della tabella temporanea siano utilizzate le regole di confronto predefinite del database utente, anziché quelle del database **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0627c-133">Specify that the temporary table column use the default collation of the user database, not **tempdb**.</span></span> <span data-ttu-id="0627c-134">Ciò consente alla tabella temporanea di utilizzare tabelle con formattazione simile in più database, se ciò è richiesto dal sistema.</span><span class="sxs-lookup"><span data-stu-id="0627c-134">This enables the temporary table to work with similarly formatted tables in multiple databases, if that is required of your system.</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE database_default  
       );  
    ```  
  
-   <span data-ttu-id="0627c-135">Specificare le regole di confronto corrette per la colonna `#TestTempTab` :</span><span class="sxs-lookup"><span data-stu-id="0627c-135">Specify the correct collation for the `#TestTempTab` column:</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE Estonian_CS_AS  
       );  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0627c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0627c-136">See Also</span></span>  
 <span data-ttu-id="0627c-137">[Impostare o modificare le regole di confronto del server](set-or-change-the-server-collation.md) </span><span class="sxs-lookup"><span data-stu-id="0627c-137">[Set or Change the Server Collation](set-or-change-the-server-collation.md) </span></span>  
 <span data-ttu-id="0627c-138">[Impostare o modificare le regole di confronto del database](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="0627c-138">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 [<span data-ttu-id="0627c-139">Regole di confronto e supporto Unicode</span><span class="sxs-lookup"><span data-stu-id="0627c-139">Collation and Unicode Support</span></span>](collation-and-unicode-support.md)  
  
  
