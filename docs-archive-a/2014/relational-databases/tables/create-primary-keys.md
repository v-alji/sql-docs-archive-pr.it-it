---
title: Creare chiavi primarie | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- primary keys [SQL Server], creating
ms.assetid: 85c623ca-4656-4d70-a9db-ee4d897cd214
author: stevestein
ms.author: sstein
ms.openlocfilehash: c515ef8f978b41225ff45e87646b0aa7a9706a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638349"
---
# <a name="create-primary-keys"></a><span data-ttu-id="1e0b4-102">Creazione di chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="1e0b4-102">Create Primary Keys</span></span>
  <span data-ttu-id="1e0b4-103">È possibile definire una chiave primaria in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e0b4-103">You can define a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1e0b4-104">Con la creazione di una chiave primaria è possibile creare automaticamente un indice univoco corrispondente, cluster o non cluster.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-104">Creating a primary key automatically creates a corresponding unique, clustered or nonclustered index.</span></span>  
  
 <span data-ttu-id="1e0b4-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="1e0b4-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1e0b4-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="1e0b4-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1e0b4-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1e0b4-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1e0b4-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1e0b4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1e0b4-109">**Per creare una chiave primaria:**</span><span class="sxs-lookup"><span data-stu-id="1e0b4-109">**To create a primary key, using:**</span></span>  
  
     [<span data-ttu-id="1e0b4-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e0b4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1e0b4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e0b4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1e0b4-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1e0b4-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1e0b4-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1e0b4-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1e0b4-114">In una tabella è possibile includere un solo vincolo PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-114">A table can contain only one PRIMARY KEY constraint.</span></span>  
  
-   <span data-ttu-id="1e0b4-115">Tutte le colonne specificate in un vincolo PRIMARY KEY devono essere definite come NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-115">All columns defined within a PRIMARY KEY constraint must be defined as NOT NULL.</span></span> <span data-ttu-id="1e0b4-116">Se non si specifica il supporto di valori Null, per tutte le colonne coinvolte in un vincolo PRIMARY KEY viene impostato NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-116">If nullability is not specified, all columns participating in a PRIMARY KEY constraint have their nullability set to NOT NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1e0b4-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1e0b4-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1e0b4-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1e0b4-118">Permissions</span></span>  
 <span data-ttu-id="1e0b4-119">Per la creazione di una nuova tabella con una chiave primaria è richiesta l'autorizzazione CREATE TABLE per il database e l'autorizzazione ALTER per lo schema in cui viene creata la tabella.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-119">Creating a new table with a primary key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="1e0b4-120">Per la creazione di una chiave primaria in una tabella esistente è richiesta l'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-120">Creating a primary key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1e0b4-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e0b4-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-primary-key"></a><span data-ttu-id="1e0b4-122">Per creare una chiave primaria</span><span class="sxs-lookup"><span data-stu-id="1e0b4-122">To create a primary key</span></span>  
  
1.  <span data-ttu-id="1e0b4-123">In Esplora oggetti fare clic con il pulsante destro del mouse sulla tabella a cui si desidera aggiungere un vincolo UNIQUE, quindi scegliere **progetta**.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-123">In Object Explorer, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="1e0b4-124">In **Progettazione tabelle**fare clic sul selettore di riga per la colonna di database che si desidera definire come chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-124">In **Table Designer**, click the row selector for the database column you want to define as the primary key.</span></span> <span data-ttu-id="1e0b4-125">Per selezionare più colonne, tenere premuto il tasto CTRL e fare clic sul selettore di riga delle altre colonne.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-125">If you want to select multiple columns, hold down the CTRL key while you click the row selectors for the other columns.</span></span>  
  
3.  <span data-ttu-id="1e0b4-126">Fare clic con il pulsante destro del mouse sul selettore di riga per la colonna e selezionare **Imposta chiave primaria**.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-126">Right-click the row selector for the column and select **Set Primary Key**.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1e0b4-127">Per ridefinire la chiave primaria, sarà necessario eliminare tutte le relazioni alla chiave primaria esistente prima di poterne creare una nuova.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-127">If you want to redefine the primary key, any relationships to the existing primary key must be deleted before the new primary key can be created.</span></span> <span data-ttu-id="1e0b4-128">Verrà visualizzato un messaggio di avviso in cui si notificherà che nel corso del processo le relazioni esistenti verranno eliminate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-128">A message will warn you that existing relationships will be automatically deleted as part of this process.</span></span>  
  
 <span data-ttu-id="1e0b4-129">Una colonna chiave primaria è contrassegnata da un simbolo di chiave primaria nel corrispondente selettore di riga.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-129">A primary key column is identified by a primary key symbol in its row selector.</span></span>  
  
 <span data-ttu-id="1e0b4-130">Se una chiave primaria è composta da più colonne, è consentita la presenza di valori duplicati in una colonna ma è comunque richiesta l'univocità delle combinazioni di valori tratti da tutte le colonne nella chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-130">If a primary key consists of more than one column, duplicate values are allowed in one column, but each combination of values from all the columns in the primary key must be unique.</span></span>  
  
 <span data-ttu-id="1e0b4-131">Se si definisce una chiave composta, l'ordine delle colonne nella chiave primaria corrisponderà all'ordine delle colonne come visualizzate nella tabella.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-131">If you define a compound key, the order of columns in the primary key matches the order of columns as shown in the table.</span></span> <span data-ttu-id="1e0b4-132">È comunque possibile modificare l'ordine delle colonne dopo la creazione della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-132">However, you can change the order of columns after the primary key is created.</span></span> <span data-ttu-id="1e0b4-133">Per altre informazioni, vedere [Modifica chiavi primarie](modify-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="1e0b4-133">For more information, see [Modify Primary Keys](modify-primary-keys.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1e0b4-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e0b4-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-primary-key-in-an-existing-table"></a><span data-ttu-id="1e0b4-135">Per creare una chiave primaria in una tabella esistente</span><span class="sxs-lookup"><span data-stu-id="1e0b4-135">To create a primary key in an existing table</span></span>  
  
1.  <span data-ttu-id="1e0b4-136">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e0b4-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1e0b4-137">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1e0b4-138">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1e0b4-139">Nell'esempio si crea una chiave primaria nella colonna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-139">The example creates a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Production.TransactionHistoryArchive   
    ADD CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID);  
    GO  
  
    ```  
  
#### <a name="to-create-a-primary-key-in-a-new-table"></a><span data-ttu-id="1e0b4-140">Per creare una chiave primaria in una nuova tabella</span><span class="sxs-lookup"><span data-stu-id="1e0b4-140">To create a primary key in a new table</span></span>  
  
1.  <span data-ttu-id="1e0b4-141">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e0b4-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1e0b4-142">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1e0b4-143">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1e0b4-144">Nell'esempio si crea una tabella e si definisce una chiave primaria nella colonna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-144">The example creates a table and defines a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive1  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="1e0b4-145">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) e [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e0b4-145">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
