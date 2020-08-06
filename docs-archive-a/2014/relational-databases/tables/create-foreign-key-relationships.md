---
title: Creare relazioni di chiave esterna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], creating
ms.assetid: 867a54b8-5be4-46e6-9702-49ae6dabf67c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ee0de3311eb6abffcdb71ab725d0650fe96b04c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638348"
---
# <a name="create-foreign-key-relationships"></a><span data-ttu-id="c6c89-102">Creare relazioni di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="c6c89-102">Create Foreign Key Relationships</span></span>
  <span data-ttu-id="c6c89-103">In questo argomento si illustra come creare relazioni di chiave esterna in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6c89-103">This topic describes how to create foreign key relationships in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c6c89-104">Una relazione tra due tabelle consente di stabilire un'associazione tra le righe di una tabella e le righe di un'altra tabella.</span><span class="sxs-lookup"><span data-stu-id="c6c89-104">You create a relationship between two tables when you want to associate rows of one table with rows of another.</span></span>  
  
 <span data-ttu-id="c6c89-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c6c89-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c6c89-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c6c89-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c6c89-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c6c89-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c6c89-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c6c89-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c6c89-109">**Per creare relazioni di chiave esterna utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="c6c89-109">**To Create Foreign Key Relationships by using:**</span></span>  
  
     [<span data-ttu-id="c6c89-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6c89-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c6c89-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6c89-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c6c89-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c6c89-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c6c89-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c6c89-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c6c89-114">Un vincolo di chiave esterna può anche non essere collegato esclusivamente al vincolo di chiave primaria di un'altra tabella. Può infatti essere definito in modo da fare riferimento alle colonne di un vincolo UNIQUE in un'altra tabella.</span><span class="sxs-lookup"><span data-stu-id="c6c89-114">A foreign key constraint does not have to be linked only to a primary key constraint in another table; it can also be defined to reference the columns of a UNIQUE constraint in another table.</span></span>  
  
-   <span data-ttu-id="c6c89-115">I valori diversi da NULL immessi nella colonna di un vincolo FOREIGN KEY devono essere presenti nella colonna a cui viene fatto riferimento. In caso contrario, viene restituito un messaggio di errore di violazione della chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="c6c89-115">When a value other than NULL is entered into the column of a FOREIGN KEY constraint, the value must exist in the referenced column; otherwise, a foreign key violation error message is returned.</span></span> <span data-ttu-id="c6c89-116">Per assicurarsi che tutti i valori di un vincolo di chiave esterna composto vengano verificati, specificare NOT NULL in tutte le colonne coinvolte.</span><span class="sxs-lookup"><span data-stu-id="c6c89-116">To make sure that all values of a composite foreign key constraint are verified, specify NOT NULL on all the participating columns.</span></span>  
  
-   <span data-ttu-id="c6c89-117">I vincoli FOREIGN KEY possono fare riferimento solo a tabelle di un singolo database nello stesso server.</span><span class="sxs-lookup"><span data-stu-id="c6c89-117">FOREIGN KEY constraints can reference only tables within the same database on the same server.</span></span> <span data-ttu-id="c6c89-118">L'integrità referenziale tra database diversi deve essere implementata tramite trigger.</span><span class="sxs-lookup"><span data-stu-id="c6c89-118">Cross-database referential integrity must be implemented through triggers.</span></span> <span data-ttu-id="c6c89-119">Per altre informazioni, vedere [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6c89-119">For more information, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
-   <span data-ttu-id="c6c89-120">I vincoli FOREIGN KEY possono fare riferimento a un'altra colonna nella stessa tabella.</span><span class="sxs-lookup"><span data-stu-id="c6c89-120">FOREIGN KEY constraints can reference another column in the same table.</span></span> <span data-ttu-id="c6c89-121">Questo tipo di vincolo viene definito autoreferenziale.</span><span class="sxs-lookup"><span data-stu-id="c6c89-121">This is referred to as a self-reference.</span></span>  
  
-   <span data-ttu-id="c6c89-122">Un vincolo FOREIGN KEY specificato a livello di colonna può includere una sola colonna di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c6c89-122">A FOREIGN KEY constraint specified at the column level can list only one reference column.</span></span> <span data-ttu-id="c6c89-123">Il tipo di dati di tale colonna deve essere uguale al tipo di dati della colonna in cui viene definito il vincolo.</span><span class="sxs-lookup"><span data-stu-id="c6c89-123">This column must have the same data type as the column on which the constraint is defined.</span></span>  
  
-   <span data-ttu-id="c6c89-124">Un vincolo FOREIGN KEY specificato a livello di tabella deve includere lo stesso numero di colonne di riferimento di quelle presenti nell'elenco di colonne del vincolo.</span><span class="sxs-lookup"><span data-stu-id="c6c89-124">A FOREIGN KEY constraint specified at the table level must have the same number of reference columns as the number of columns in the constraint column list.</span></span> <span data-ttu-id="c6c89-125">Il tipo di dati di ogni colonna di riferimento deve inoltre essere uguale a quello della colonna corrispondente nell'elenco di colonne.</span><span class="sxs-lookup"><span data-stu-id="c6c89-125">The data type of each reference column must also be the same as the corresponding column in the column list.</span></span>  
  
-   <span data-ttu-id="c6c89-126">Il [!INCLUDE[ssDE](../../includes/ssde-md.md)] non prevede un limite predefinito per il numero di vincoli FOREIGN KEY che possono essere inclusi in una tabella e che fanno riferimento ad altre tabelle o per il numero di vincoli FOREIGN KEY di proprietà di altre tabelle che fanno riferimento a una tabella specifica.</span><span class="sxs-lookup"><span data-stu-id="c6c89-126">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not have a predefined limit on either the number of FOREIGN KEY constraints a table can contain that reference other tables, or the number of FOREIGN KEY constraints that are owned by other tables that reference a specific table.</span></span> <span data-ttu-id="c6c89-127">Il numero effettivo di vincoli FOREIGN KEY che è possibile usare, tuttavia, è limitato dalla configurazione hardware e dalla progettazione del database e dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6c89-127">Nevertheless, the actual number of FOREIGN KEY constraints that can be used is limited by the hardware configuration and by the design of the database and application.</span></span> <span data-ttu-id="c6c89-128">È consigliabile evitare che una tabella contenga più di 253 vincoli FOREIGN KEY e che più di 253 vincoli FOREIGN KEY facciano riferimento alla tabella stessa.</span><span class="sxs-lookup"><span data-stu-id="c6c89-128">We recommend that a table contain no more than 253 FOREIGN KEY constraints, and that it be referenced by no more than 253 FOREIGN KEY constraints.</span></span>  
  
-   <span data-ttu-id="c6c89-129">I vincoli FOREIGN KEY non vengono applicati nelle tabelle temporanee.</span><span class="sxs-lookup"><span data-stu-id="c6c89-129">FOREIGN KEY constraints are not enforced on temporary tables.</span></span>  
  
-   <span data-ttu-id="c6c89-130">Se si definisce una chiave esterna su una colonna di tipo CLR definito dall'utente, è necessario che l'implementazione del tipo supporti l'ordinamento binario.</span><span class="sxs-lookup"><span data-stu-id="c6c89-130">If a foreign key is defined on a CLR user-defined type column, the implementation of the type must support binary ordering.</span></span> <span data-ttu-id="c6c89-131">Per altre informazioni, vedere [Tipi CLR definiti dall'utente](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="c6c89-131">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
-   <span data-ttu-id="c6c89-132">Una colonna di tipo `varchar(max)` può far parte di un vincolo FOREIGN KEY solo se anche la chiave primaria a cui fa riferimento è definita come tipo `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="c6c89-132">A column of type `varchar(max)` can participate in a FOREIGN KEY constraint only if the primary key it references is also defined as type `varchar(max)`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c6c89-133">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c6c89-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6c89-134">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c6c89-134">Permissions</span></span>  
 <span data-ttu-id="c6c89-135">Per la creazione di una nuova tabella con una chiave esterna è richiesta l'autorizzazione CREATE TABLE per il database e l'autorizzazione ALTER per lo schema in cui viene creata la tabella.</span><span class="sxs-lookup"><span data-stu-id="c6c89-135">Creating a new table with a foreign key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="c6c89-136">Per la creazione di una chiave esterna in una tabella esistente è richiesta l'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="c6c89-136">Creating a foreign key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c6c89-137">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6c89-137">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-foreign-key-relationship-in-table-designer"></a><span data-ttu-id="c6c89-138">Per creare una relazione di chiave esterna in Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="c6c89-138">To create a foreign key relationship in Table Designer</span></span>  
  
1.  <span data-ttu-id="c6c89-139">In Esplora oggetti fare clic con il pulsante destro del mouse sulla tabella che si troverà sul lato chiave esterna della relazione e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="c6c89-139">In Object Explorer, right-click the table that will be on the foreign-key side of the relationship and click **Design**.</span></span>  
  
     <span data-ttu-id="c6c89-140">La tabella verrà visualizzata in **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="c6c89-140">The table opens in **Table Designer**.</span></span>  
  
2.  <span data-ttu-id="c6c89-141">Scegliere **Relazioni** dal menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="c6c89-141">From the **Table Designer** menu, click **Relationships**.</span></span>  
  
3.  <span data-ttu-id="c6c89-142">Nella finestra di dialogo **Relazioni chiavi esterne** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c6c89-142">In the **Foreign-key Relationships** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="c6c89-143">La relazione verrà visualizzata nell'elenco **Relazione selezionata** con un nome specificato dal sistema nel formato FK_\<*tablename*>_\<*tablename*>, dove *tablename* è il nome della tabella di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="c6c89-143">The relationship appears in the **Selected Relationship** list with a system-provided name in the format FK_\<*tablename*>_\<*tablename*>, where *tablename* is the name of the foreign key table.</span></span>  
  
4.  <span data-ttu-id="c6c89-144">Fare clic sulla relazione nell'elenco **Relazione selezionata** .</span><span class="sxs-lookup"><span data-stu-id="c6c89-144">Click the relationship in the **Selected Relationship** list.</span></span>  
  
5.  <span data-ttu-id="c6c89-145">Fare clic su **Specifica tabelle e colonne** nella griglia a destra e quindi sul pulsante con i puntini di sospensione ( **...** ) a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c6c89-145">Click **Tables and Columns Specification** in the grid to the right and click the ellipses (**...**) to the right of the property.</span></span>  
  
6.  <span data-ttu-id="c6c89-146">Nella finestra di dialogo **Tabelle e colonne** selezionare dall'elenco a discesa **Chiave primaria** la tabella che si troverà sul lato chiave primaria della relazione.</span><span class="sxs-lookup"><span data-stu-id="c6c89-146">In the **Tables and Columns** dialog box, in the **Primary Key** drop-down list, choose the table that will be on the primary-key side of the relationship.</span></span>  
  
7.  <span data-ttu-id="c6c89-147">Nella griglia sottostante selezionare le colonne che contribuiranno alla chiave primaria della tabella.</span><span class="sxs-lookup"><span data-stu-id="c6c89-147">In the grid beneath, choose the columns contributing to the table's primary key.</span></span> <span data-ttu-id="c6c89-148">Nella cella adiacente alla sinistra di ciascuna colonna selezionare la corrispondente colonna chiave esterna della tabella di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="c6c89-148">In the adjacent grid cell to the left of each column, choose the corresponding foreign-key column of the foreign-key table.</span></span>  
  
     <span data-ttu-id="c6c89-149">**Progettazione tabelle** suggerisce automaticamente un nome da assegnare alla relazione.</span><span class="sxs-lookup"><span data-stu-id="c6c89-149">**Table Designer** suggests a name for the relationship.</span></span> <span data-ttu-id="c6c89-150">Per specificare un nome diverso, modificare il contenuto della casella di testo **Nome relazione** .</span><span class="sxs-lookup"><span data-stu-id="c6c89-150">To change this name, edit the contents of the **Relationship Name** text box.</span></span>  
  
8.  <span data-ttu-id="c6c89-151">Scegliere **OK** per creare la relazione.</span><span class="sxs-lookup"><span data-stu-id="c6c89-151">Choose **OK** to create the relationship.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c6c89-152">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6c89-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-foreign-key-in-a-new-table"></a><span data-ttu-id="c6c89-153">Per creare una chiave esterna in una nuova tabella</span><span class="sxs-lookup"><span data-stu-id="c6c89-153">To create a foreign key in a new table</span></span>  
  
1.  <span data-ttu-id="c6c89-154">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6c89-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6c89-155">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c6c89-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6c89-156">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c6c89-156">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c6c89-157">Nell'esempio si crea una tabella e si definisce un vincolo di chiave esterna nella colonna `TempID` alla quale fa riferimento la colonna `SalesReasonID` nella tabella `Sales.SalesReason` .</span><span class="sxs-lookup"><span data-stu-id="c6c89-157">The example creates a table and defines a foreign key constraint on the column `TempID` that references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span> <span data-ttu-id="c6c89-158">Le clausole ON DELETE CASCADE e ON UPDATE CASCADE vengono utilizzate per garantire che le modifiche apportate alla tabella `Sales.SalesReason` vengano propagate automaticamente alla tabella `Sales.TempSalesReason` .</span><span class="sxs-lookup"><span data-stu-id="c6c89-158">The ON DELETE CASCADE and ON UPDATE CASCADE clauses are used to ensure that changes made to `Sales.SalesReason` table are automatically propagated to the `Sales.TempSalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Sales.TempSalesReason (TempID int NOT NULL, Name nvarchar(50),   
    CONSTRAINT PK_TempSales PRIMARY KEY NONCLUSTERED (TempID),   
    CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    );GO  
  
    ```  
  
#### <a name="to-create-a-foreign-key-in-an-existing-table"></a><span data-ttu-id="c6c89-159">Per creare una chiave esterna in una tabella esistente</span><span class="sxs-lookup"><span data-stu-id="c6c89-159">To create a foreign key in an existing table</span></span>  
  
1.  <span data-ttu-id="c6c89-160">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6c89-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6c89-161">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c6c89-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6c89-162">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c6c89-162">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c6c89-163">Nell'esempio si crea una chiave esterna nella colonna `TempID` e si fa riferimento alla colonna `SalesReasonID` nella tabella `Sales.SalesReason` .</span><span class="sxs-lookup"><span data-stu-id="c6c89-163">The example creates a foreign key on the column `TempID` and references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Sales.TempSalesReason   
    ADD CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    ;  
    GO  
  
    ```  
  
     <span data-ttu-id="c6c89-164">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) e [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6c89-164">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
  
