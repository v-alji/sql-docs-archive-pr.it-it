---
title: Visualizzazione di informazioni sulle regole di confronto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], view
ms.assetid: 1338b4ea-7142-44bc-a3b9-44e54431405f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 995e559cfd7ca871f5abd90751f2f79167bdf76f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637900"
---
# <a name="view-collation-information"></a><span data-ttu-id="7af50-102">Visualizzazione di informazioni sulle regole di confronto</span><span class="sxs-lookup"><span data-stu-id="7af50-102">View Collation Information</span></span>
    
##  <a name="you-can-view-the-collation-of-a-server-database-or-column-in-ssmanstudiofull-using-object-explorer-menu-options-or-by-using-tsql"></a><a name="Top"></a> <span data-ttu-id="7af50-103">È possibile visualizzare le regole di confronto di un server, di un database o di una colonna in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usando le opzioni di menu di Esplora oggetti oppure tramite [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7af50-103">You can view the collation of a server, database, or column in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
##  <a name="how-to-view-a-collation-setting"></a><a name="Procedures"></a> <span data-ttu-id="7af50-104">Visualizzazione di un'impostazione relativa alle regole di confronto</span><span class="sxs-lookup"><span data-stu-id="7af50-104">How to View a Collation Setting</span></span>  
 <span data-ttu-id="7af50-105">È possibile usare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="7af50-105">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="7af50-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7af50-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="7af50-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7af50-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7af50-108">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7af50-108">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7af50-109">**Per visualizzare un'impostazione delle regole di confronto per un server (istanza di SQL Server) in Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="7af50-109">**To view a collation setting for a server (instance of SQL Server) in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7af50-110">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7af50-110">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7af50-111">Fare clic con il pulsante destro del mouse sull'istanza e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7af50-111">Right-click the instance and select **Properties**.</span></span>  
  
 <span data-ttu-id="7af50-112">**Per visualizzare un'impostazione delle regole di confronto per un database in Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="7af50-112">**To view a collation setting for a database in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7af50-113">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="7af50-113">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7af50-114">Espandere **Database**, fare clic con il pulsante destro del mouse sul database e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7af50-114">Expand **Databases**, right-click the database and select **Properties**.</span></span>  
  
 <span data-ttu-id="7af50-115">**Per visualizzare un'impostazione delle regole di confronto per una colonna in Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="7af50-115">**To view a collation setting for a column in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7af50-116">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="7af50-116">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7af50-117">Espandere **Database**, il database desiderato, quindi **Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="7af50-117">Expand **Databases**, expand the database and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="7af50-118">Espandere la tabella che contiene la colonna, quindi espandere **Colonne**.</span><span class="sxs-lookup"><span data-stu-id="7af50-118">Expand the table that contains the column and then expand **Columns**.</span></span>  
  
4.  <span data-ttu-id="7af50-119">Fare clic con il pulsante destro del mouse sulla colonna e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7af50-119">Right-click the column and select **Properties**.</span></span> <span data-ttu-id="7af50-120">Se la proprietà di regola di confronto è vuota, la colonna non è un tipo di dati character.</span><span class="sxs-lookup"><span data-stu-id="7af50-120">If the collation property is empty, the column is not a character data type.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7af50-121">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7af50-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="7af50-122">**Per visualizzare l'impostazione delle regole di confronto di un server**</span><span class="sxs-lookup"><span data-stu-id="7af50-122">**To view the collation setting of a server**</span></span>  
  
1.  <span data-ttu-id="7af50-123">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] e nella barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="7af50-123">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7af50-124">Nella finestra Query, immettere l'istruzione seguente che usano la funzione di sistema SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="7af50-124">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, SERVERPROPERTY('collation'));  
    ```  
  
3.  <span data-ttu-id="7af50-125">In alternativa, è possibile usare la stored procedure di sistema sp_helpsort.</span><span class="sxs-lookup"><span data-stu-id="7af50-125">Alternatively, you can use the sp_helpsort system stored procedure.</span></span>  
  
    ```  
    EXECUTE sp_helpsort;  
    ```  
  
 <span data-ttu-id="7af50-126">**Per visualizzare tutte le regole di confronto supportate da [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="7af50-126">**To view all collations supported by [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span></span>  
  
1.  <span data-ttu-id="7af50-127">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] e nella barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="7af50-127">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7af50-128">Nella finestra Query, immettere l'istruzione seguente che usano la funzione di sistema SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="7af50-128">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT name, description FROM sys.fn_helpcollations();  
    ```  
  
 <span data-ttu-id="7af50-129">**Per visualizzare l'impostazione delle regole di confronto di un database**</span><span class="sxs-lookup"><span data-stu-id="7af50-129">**To view the collation setting of a database**</span></span>  
  
1.  <span data-ttu-id="7af50-130">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] e nella barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="7af50-130">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7af50-131">Nella finestra Query, immettere l'istruzione seguente che usano la vista del catalogo sys.databases.</span><span class="sxs-lookup"><span data-stu-id="7af50-131">In the query window, enter the following statement that uses the sys.databases system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.databases;  
    ```  
  
3.  <span data-ttu-id="7af50-132">In alternativa, è possibile usare la funzione di sistema DATABASEPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="7af50-132">Alternatively, you can use the DATABASEPROPERTYEX system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, DATABASEPROPERTYEX('database_name','collation'));  
    ```  
  
 <span data-ttu-id="7af50-133">**Per visualizzare l'impostazione delle regole di confronto di una colonna**</span><span class="sxs-lookup"><span data-stu-id="7af50-133">**To view the collation setting of a column**</span></span>  
  
1.  <span data-ttu-id="7af50-134">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] e nella barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="7af50-134">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7af50-135">Nella finestra Query, immettere l'istruzione seguente che usano la vista del catalogo sys.columns.</span><span class="sxs-lookup"><span data-stu-id="7af50-135">In the query window, enter the following statement that uses the sys.columns system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.columns WHERE name = N'<insert character data type column name>';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7af50-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7af50-136">See Also</span></span>  
 <span data-ttu-id="7af50-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7af50-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="7af50-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7af50-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="7af50-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7af50-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="7af50-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7af50-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span></span>  
 <span data-ttu-id="7af50-141">[Precedenza delle regole di confronto &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7af50-141">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 [<span data-ttu-id="7af50-142">sp_helpsort &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7af50-142">sp_helpsort &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-helpsort-transact-sql)  
  
  
