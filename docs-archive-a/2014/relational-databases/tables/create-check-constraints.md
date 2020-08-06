---
title: Creare vincoli CHECK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table constraints [SQL Server]
- attaching check constraints
- columns [SQL Server], constraints
- constraints [SQL Server], check
- CHECK constraints, attaching
ms.assetid: b8756304-9454-4d39-996a-64516831b7df
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7795ee6eca85a22bdd4e84c90ce49a9449ddff28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638352"
---
# <a name="create-check-constraints"></a><span data-ttu-id="7e543-102">Creare vincoli CHECK</span><span class="sxs-lookup"><span data-stu-id="7e543-102">Create Check Constraints</span></span>
  <span data-ttu-id="7e543-103">È possibile creare un vincolo CHECK in una tabella per specificare i valori di dati accettabili in una o più colonne in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e543-103">You can create a check constraint in a table to specify the data values that are acceptable in one or more columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7e543-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="7e543-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7e543-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="7e543-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7e543-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e543-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7e543-107">**Per creare un nuovo vincolo CHECK:**</span><span class="sxs-lookup"><span data-stu-id="7e543-107">**To create a new check constraint using:**</span></span>  
  
     [<span data-ttu-id="7e543-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e543-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7e543-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e543-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7e543-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7e543-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7e543-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e543-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7e543-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7e543-112">Permissions</span></span>  
 <span data-ttu-id="7e543-113">È necessario disporre delle autorizzazioni ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="7e543-113">Requires ALTER permissions on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7e543-114">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e543-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="7e543-115">Per creare un nuovo vincolo CHECK</span><span class="sxs-lookup"><span data-stu-id="7e543-115">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="7e543-116">In **Esplora oggetti**espandere la tabella a cui si vuole aggiungere un vincolo CHECK, fare clic con il pulsante destro del mouse su **Vincoli** e scegliere **Nuovo vincolo**.</span><span class="sxs-lookup"><span data-stu-id="7e543-116">In **Object Explorer**, expand the table to which you want to add a check constraint, right-click **Constraints** and click **New Constraint**.</span></span>  
  
2.  <span data-ttu-id="7e543-117">Nella finestra di dialogo **Vincoli CHECK** fare clic nel campo **Espressione** e quindi sui puntini di sospensione **(...)** .</span><span class="sxs-lookup"><span data-stu-id="7e543-117">In the **Check Constraints** dialog box, click in the **Expression** field and then click the ellipses **(...)**.</span></span>  
  
3.  <span data-ttu-id="7e543-118">Nella finestra di dialogo **Espressione vincolo CHECK** immettere le espressioni SQL per il vincolo CHECK:</span><span class="sxs-lookup"><span data-stu-id="7e543-118">In the **Check Constraint Expression** dialog box, type the SQL expressions for the check constraint.</span></span> <span data-ttu-id="7e543-119">Ad esempio per limitare le voci nella colonna `SellEndDate` della tabella `Product` a un valore che è maggiore o uguale alla data nella colonna `SellStartDate` o è un valore NULL, digitare:</span><span class="sxs-lookup"><span data-stu-id="7e543-119">For example, to limit the entries in the `SellEndDate` column of the `Product` table to a value that is either greater than or equal to the date in the `SellStartDate` column or is a NULL value, type:</span></span>  
  
    ```  
    SellEndDate >= SellStartDate OR SellEndDate IS NULL  
    ```  
  
     <span data-ttu-id="7e543-120">In alternativa, per richiedere l'immissione di un valore composto da 5 cifre nella colonna `zip` , digitare:</span><span class="sxs-lookup"><span data-stu-id="7e543-120">Or, to require entries in the `zip` column to be 5 digits, type:</span></span>  
  
    ```  
    zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e543-121">Tutti i valori di vincolo non numerici devono essere racchiusi tra virgolette singole (').</span><span class="sxs-lookup"><span data-stu-id="7e543-121">Make sure to enclose any non-numeric constraint values in single quotation marks (').</span></span>  
  
4.  <span data-ttu-id="7e543-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e543-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="7e543-123">Nella categoria **Identità** è possibile modificare il nome del vincolo CHECK e aggiungere una descrizione (proprietà estesa) per il vincolo.</span><span class="sxs-lookup"><span data-stu-id="7e543-123">In the **Identity** category, you can change the name of the check constraint and add a description (extended property) for the constraint.</span></span>  
  
6.  <span data-ttu-id="7e543-124">Nella categoria **Progettazione tabelle** è possibile impostare quando deve essere applicato il vincolo.</span><span class="sxs-lookup"><span data-stu-id="7e543-124">In the **Table Designer** category, you can set when the constraint is enforced.</span></span>  
  
    |<span data-ttu-id="7e543-125">**A:**</span><span class="sxs-lookup"><span data-stu-id="7e543-125">**To:**</span></span>|<span data-ttu-id="7e543-126">**Selezionare Sì nei seguenti campi:**</span><span class="sxs-lookup"><span data-stu-id="7e543-126">**Select Yes in the Following Fields:**</span></span>|  
    |-------------|---------------------------------------------|  
    |<span data-ttu-id="7e543-127">Testare il vincolo su dati che esistevano prima di creare il vincolo</span><span class="sxs-lookup"><span data-stu-id="7e543-127">Test the constraint on data that existed before you created the constraint</span></span>|<span data-ttu-id="7e543-128">**Verificare i dati esistenti durante la creazione o l'abilitazione**</span><span class="sxs-lookup"><span data-stu-id="7e543-128">**Check Existing Data On Creation Or Enabling**</span></span>|  
    |<span data-ttu-id="7e543-129">Applicare il vincolo quando si verifica un'operazione di replica su questa tabella</span><span class="sxs-lookup"><span data-stu-id="7e543-129">Enforce the constraint whenever a replication operation occurs on this table</span></span>|<span data-ttu-id="7e543-130">**Applicare per replica**</span><span class="sxs-lookup"><span data-stu-id="7e543-130">**Enforce For Replication**</span></span>|  
    |<span data-ttu-id="7e543-131">Applicare il vincolo ogni qualvolta una riga di questa tabella viene inserita o viene aggiornata</span><span class="sxs-lookup"><span data-stu-id="7e543-131">Enforce the constraint whenever a row of this table is inserted or updated</span></span>|<span data-ttu-id="7e543-132">**Attiva per istruzioni INSERTs e UPDATEs**</span><span class="sxs-lookup"><span data-stu-id="7e543-132">**Enforce For INSERTs And UPDATEs**</span></span>|  
  
7.  <span data-ttu-id="7e543-133">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="7e543-133">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7e543-134">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e543-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="7e543-135">Per creare un nuovo vincolo CHECK</span><span class="sxs-lookup"><span data-stu-id="7e543-135">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="7e543-136">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e543-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7e543-137">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="7e543-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7e543-138">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="7e543-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
       ADD ColumnD int NULL   
       CONSTRAINT CHK_ColumnD_DocExc   
       CHECK (ColumnD > 10 AND ColumnD < 50);  
    GO  
    -- Adding values that will pass the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (49);  
    GO  
    -- Adding values that will fail the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (55);  
    GO  
  
    ```  
  
 <span data-ttu-id="7e543-139">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7e543-139">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
