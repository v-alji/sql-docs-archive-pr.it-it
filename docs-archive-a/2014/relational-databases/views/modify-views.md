---
title: Modificare viste | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- views [SQL Server], modifying
- modifying views
- renaming views
ms.assetid: 2d3c14dc-43e5-4324-b8fb-f2692d330b16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10cf9ecc860d8f9b46a06ac679b0f1a8241000bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628564"
---
# <a name="modify-views"></a><span data-ttu-id="8ec3e-102">Modifica di viste</span><span class="sxs-lookup"><span data-stu-id="8ec3e-102">Modify Views</span></span>
  <span data-ttu-id="8ec3e-103">Dopo aver definito una vista, è possibile modificarne la definizione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , senza eliminare e ricreare la vista, utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ec3e-103">After you define a view, you can modify its definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] without dropping and re-creating the view by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8ec3e-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="8ec3e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8ec3e-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="8ec3e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8ec3e-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="8ec3e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8ec3e-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8ec3e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8ec3e-108">**Per modificare una vista tramite:**</span><span class="sxs-lookup"><span data-stu-id="8ec3e-108">**To modify a view, using:**</span></span>  
  
     [<span data-ttu-id="8ec3e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ec3e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8ec3e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ec3e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8ec3e-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8ec3e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8ec3e-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="8ec3e-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8ec3e-113">La modifica di una vista non influisce sugli oggetti dipendenti, ad esempio stored procedure o trigger, a meno che la definizione della vista non venga modificata in modo che l'oggetto dipendente non sia più valido.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-113">Modifying a view does not affect any dependent objects, such as stored procedures or triggers, unless the definition of the view changes in such a way that the dependent object is no longer valid.</span></span>  
  
-   <span data-ttu-id="8ec3e-114">Se si modifica una vista in uso con ALTER VIEW, nel [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene accettato un blocco di schema esclusivo sulla vista.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-114">If a view currently used is modified by using ALTER VIEW, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes an exclusive schema lock on the view.</span></span> <span data-ttu-id="8ec3e-115">Quando viene concesso il blocco e non esistono utenti attivi della vista, [!INCLUDE[ssDE](../../includes/ssde-md.md)] elimina tutte le copie della vista dalla cache delle procedure.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-115">When the lock is granted, and there are no active users of the view, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] deletes all copies of the view from the procedure cache.</span></span> <span data-ttu-id="8ec3e-116">I piani esistenti che fanno riferimento alla vista rimangono nella cache, ma vengono ricompilati per chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-116">Existing plans referencing the view remain in the cache but are recompiled when invoked.</span></span>  
  
-   <span data-ttu-id="8ec3e-117">È possibile utilizzare ALTER VIEW per viste indicizzate. Tuttavia, in questo caso vengono eliminati tutti gli indici nella vista, senza eccezioni.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-117">ALTER VIEW can be applied to indexed views; however, ALTER VIEW unconditionally drops all indexes on the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8ec3e-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8ec3e-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8ec3e-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8ec3e-119">Permissions</span></span>  
 <span data-ttu-id="8ec3e-120">Per eseguire ALTER VIEW, è richiesta come minimo l'autorizzazione ALTER per OBJECT.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-120">To execute ALTER VIEW, at a minimum, ALTER permission on OBJECT is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8ec3e-121">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ec3e-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="8ec3e-122">Per modificare una vista</span><span class="sxs-lookup"><span data-stu-id="8ec3e-122">To modify a view</span></span>  
  
1.  <span data-ttu-id="8ec3e-123">In **Esplora oggetti**fare clic sul segno più accanto al database in cui si trova la vista, quindi fare di nuovo clic sul segno più accanto alla cartella **Viste** .</span><span class="sxs-lookup"><span data-stu-id="8ec3e-123">In **Object Explorer**, click the plus sign next to the database where your view is located and then click the plus sign next to the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="8ec3e-124">Fare clic con il pulsante destro del mouse sulla vista che si desidera modificare, quindi scegliere **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-124">Right-click on the view you wish to modify and select **Design**.</span></span>  
  
3.  <span data-ttu-id="8ec3e-125">Nel riquadro del diagramma di Progettazione query, apportare le modifiche alla vista con uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-125">In the diagram pane of the query designer, make changes to the view in one or more of the following ways:</span></span>  
  
    1.  <span data-ttu-id="8ec3e-126">Selezionare o deselezionare le caselle di controllo di qualsiasi elemento che si desidera aggiungere o rimuovere.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-126">Select or clear the check boxes of any elements you wish to add or remove.</span></span>  
  
    2.  <span data-ttu-id="8ec3e-127">Fare clic con il pulsante destro del mouse all'interno del riquadro del diagramma, scegliere **Aggiungi tabella** e quindi selezionare le altre colonne da aggiungere alla vista nella finestra di dialogo **Aggiungi tabella**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-127">Right-click within the diagram pane, select **Add Table...**, and then select the additional columns you want to add to the view from the **Add Table** dialog box.</span></span>  
  
    3.  <span data-ttu-id="8ec3e-128">Fare clic con il pulsante destro del mouse sulla barra del titolo della tabella da rimuovere e selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-128">Right-click the title bar of the table you wish to remove and select **Remove**.</span></span>  
  
4.  <span data-ttu-id="8ec3e-129">Nel menu **File** scegliere **Salva**_view name_.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-129">On the **File** menu, click **Save**_view name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8ec3e-130">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ec3e-130">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="8ec3e-131">Per modificare una vista</span><span class="sxs-lookup"><span data-stu-id="8ec3e-131">To modify a view</span></span>  
  
1.  <span data-ttu-id="8ec3e-132">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ec3e-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8ec3e-133">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8ec3e-134">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8ec3e-135">Nell'esempio si crea innanzitutto una vista che, successivamente, viene modificata tramite ALTER VIEW.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-135">The example first creates a view and then modifies the view by using ALTER VIEW.</span></span> <span data-ttu-id="8ec3e-136">Una clausola WHERE viene aggiunta alla definizione della vista.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-136">A WHERE clause is added to the view definition.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    -- Create a view.  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
  
    -- Modify the view by adding a WHERE clause to limit the rows returned.  
    ALTER VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID  
    WHERE HireDate < CONVERT(DATETIME,'20020101',101) ;   
    GO  
    ```  
  
 <span data-ttu-id="8ec3e-137">Per altre informazioni, vedere [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ec3e-137">For more information, see [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span></span>  
  
  
