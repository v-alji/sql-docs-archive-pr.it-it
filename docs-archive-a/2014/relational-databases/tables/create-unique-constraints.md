---
title: Creare vincoli univoci | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- UNIQUE constraints [SQL Server], creating
- constraints [SQL Server], creating
- constraints [SQL Server], unique
ms.assetid: a86f9d6f-f242-43be-b65d-b3435b71b62a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 252de63f965f98734a6d62d94bfff9dc5774cab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722675"
---
# <a name="create-unique-constraints"></a><span data-ttu-id="166d8-102">Creare vincoli univoci</span><span class="sxs-lookup"><span data-stu-id="166d8-102">Create Unique Constraints</span></span>
  <span data-ttu-id="166d8-103">È possibile creare un vincolo univoco in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] per assicurare non vengano immessi valori duplicat nelle colonne specifiche che non partecipano in una chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="166d8-103">You can create a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] to ensure no duplicate values are entered in specific columns that do not participate in a primary key.</span></span> <span data-ttu-id="166d8-104">La creazione automatica di un vincolo univoco crea un indice univoco corrispondente.</span><span class="sxs-lookup"><span data-stu-id="166d8-104">Creating a unique constraint automatically creates a corresponding unique index.</span></span>  
  
 <span data-ttu-id="166d8-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="166d8-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="166d8-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="166d8-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="166d8-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="166d8-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="166d8-108">**Per creare un vincolo univoco:**</span><span class="sxs-lookup"><span data-stu-id="166d8-108">**To create a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="166d8-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="166d8-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="166d8-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="166d8-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="166d8-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="166d8-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="166d8-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="166d8-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="166d8-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="166d8-113">Permissions</span></span>  
 <span data-ttu-id="166d8-114">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="166d8-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="166d8-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="166d8-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="166d8-116">Per creare un vincolo univoco</span><span class="sxs-lookup"><span data-stu-id="166d8-116">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="166d8-117">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella nella quale aggiungere un vincolo univoco e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="166d8-117">In **Object Explorer**, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="166d8-118">Scegliere **Indici/chiavi**dal menu **Progettazione tabelle** .</span><span class="sxs-lookup"><span data-stu-id="166d8-118">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="166d8-119">Nella finestra di dialogo **Indici/chiavi** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="166d8-119">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="166d8-120">Nella griglia in **Generale**fare clic su **Tipo** e selezionare **Chiave univoca** dall'elenco a discesa a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="166d8-120">In the grid under **General**, click **Type** and choose **Unique Key** from the drop-down list box to the right of the property.</span></span>  
  
5.  <span data-ttu-id="166d8-121">Nel menu **File** fare clic su **Salva**_nome tabella_.</span><span class="sxs-lookup"><span data-stu-id="166d8-121">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="166d8-122">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="166d8-122">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="166d8-123">Per creare un vincolo univoco</span><span class="sxs-lookup"><span data-stu-id="166d8-123">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="166d8-124">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="166d8-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="166d8-125">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="166d8-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="166d8-126">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="166d8-126">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="166d8-127">Nell'esempio viene creata la tabella `TransactionHistoryArchive4` e un vincolo univoco sulla colonna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="166d8-127">The example creates the table `TransactionHistoryArchive4` and creates a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive4  
     (  
       TransactionID int NOT NULL,   
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)   
    );   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-on-an-existing-table"></a><span data-ttu-id="166d8-128">Per creare un vincolo univoco in una tabella esistente</span><span class="sxs-lookup"><span data-stu-id="166d8-128">To create a unique constraint on an existing table</span></span>  
  
1.  <span data-ttu-id="166d8-129">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="166d8-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="166d8-130">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="166d8-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="166d8-131">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="166d8-131">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="166d8-132">Nell'esempio viene creato un vincolo univoco nelle colonne `PasswordHash` e `PasswordSalt` della tabella `Person.Password`.</span><span class="sxs-lookup"><span data-stu-id="166d8-132">The example creates a unique constraint on the columns `PasswordHash` and `PasswordSalt` in the table `Person.Password`.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    ALTER TABLE Person.Password   
    ADD CONSTRAINT AK_Password UNIQUE (PasswordHash, PasswordSalt);   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-in-an-new-table"></a><span data-ttu-id="166d8-133">Per creare un vincolo univoco in una nuova tabella</span><span class="sxs-lookup"><span data-stu-id="166d8-133">To create a unique constraint in an new table</span></span>  
  
1.  <span data-ttu-id="166d8-134">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="166d8-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="166d8-135">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="166d8-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="166d8-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="166d8-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="166d8-137">Nell'esempio viene creata una tabella e definito un vincolo univoco nelle colonne `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="166d8-137">The example creates a table and defines a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive2  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="166d8-138">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) e [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="166d8-138">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
