---
title: Visualizzare le proprietà delle guide di piano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.planguideprop.general.f1
helpviewer_keywords:
- plan guides [SQL Server], view plan guide properties
- viewing plan guide properties
ms.assetid: 8c0d2f39-59c1-4168-a649-65473f6a771b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af29c66690a43f89106c1f77aca8c3a02eff2ba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715231"
---
# <a name="view-plan-guide-properties"></a><span data-ttu-id="5b12f-102">Visualizzare le proprietà delle guide di piano</span><span class="sxs-lookup"><span data-stu-id="5b12f-102">View Plan Guide Properties</span></span>
  <span data-ttu-id="5b12f-103">È possibile visualizzare le proprietà delle guide di piano in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b12f-103">You can view the properties of plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="5b12f-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5b12f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b12f-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5b12f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b12f-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5b12f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b12f-107">**Per visualizzare le proprietà delle guide di piano utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="5b12f-107">**To view the properties of plan guides, using:**</span></span>  
  
     [<span data-ttu-id="5b12f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b12f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b12f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b12f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b12f-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5b12f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b12f-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5b12f-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b12f-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5b12f-112">Permissions</span></span>  
 <span data-ttu-id="5b12f-113">La visibilità dei metadati nelle viste del catalogo è limitata alle entità a protezione diretta di cui un utente è proprietario o per le quali dispone di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5b12f-113">The visibility of the metadata in catalog views is limited to securables that either a user owns or on which the user has been granted some permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b12f-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b12f-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="5b12f-115">Per visualizzare le proprietà di una guida di piano</span><span class="sxs-lookup"><span data-stu-id="5b12f-115">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="5b12f-116">Fare clic sul segno più per espandere il database in cui si desidera visualizzare le proprietà di una guida di piano, quindi fare clic sul segno più per espandere la cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="5b12f-116">Click the plus sign to expand the database in which you want to view the properties of a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="5b12f-117">Fare clic sul segno più per espandere la cartella **Guide di piano** .</span><span class="sxs-lookup"><span data-stu-id="5b12f-117">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="5b12f-118">Fare clic con il pulsante destro del mouse sulla guida di piano di cui visualizzare le proprietà e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5b12f-118">Right-click the plan guide of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="5b12f-119">Le seguenti proprietà vengono visualizzate nella finestra di dialogo **Proprietà guida di piano** .</span><span class="sxs-lookup"><span data-stu-id="5b12f-119">The following properties show in the **Plan Guide Properties** dialog box.</span></span>  
  
     <span data-ttu-id="5b12f-120">**Hint**</span><span class="sxs-lookup"><span data-stu-id="5b12f-120">**Hints**</span></span>  
     <span data-ttu-id="5b12f-121">Vengono visualizzati gli hint per la query o il piano di query da applicare all'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b12f-121">Displays the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="5b12f-122">Quando un piano di query viene specificato come un hint, viene visualizzato l'output di Showplan XML per il piano.</span><span class="sxs-lookup"><span data-stu-id="5b12f-122">When a query plan is specified as a hint, the XML Showplan output for the plan is displayed.</span></span>  
  
     <span data-ttu-id="5b12f-123">**Disabilitato**</span><span class="sxs-lookup"><span data-stu-id="5b12f-123">**Is disabled**</span></span>  
     <span data-ttu-id="5b12f-124">Visualizza lo stato della guida di piano.</span><span class="sxs-lookup"><span data-stu-id="5b12f-124">Displays the status of the plan guide.</span></span> <span data-ttu-id="5b12f-125">I valori possibili sono **True** e **False**.</span><span class="sxs-lookup"><span data-stu-id="5b12f-125">Possible values are **True** and **False**.</span></span>  
  
     <span data-ttu-id="5b12f-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5b12f-126">**Name**</span></span>  
     <span data-ttu-id="5b12f-127">Visualizza il nome della guida di piano.</span><span class="sxs-lookup"><span data-stu-id="5b12f-127">Displays the name of the plan guide.</span></span>  
  
     <span data-ttu-id="5b12f-128">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="5b12f-128">**Parameters**</span></span>  
     <span data-ttu-id="5b12f-129">Quando il tipo di ambito è SQL o TEMPLATE, vengono visualizzati il nome e il tipo di dati di tutti i parametri incorporati nell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b12f-129">When the scope type is SQL or TEMPLATE, displays the name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="5b12f-130">**Batch ambito**</span><span class="sxs-lookup"><span data-stu-id="5b12f-130">**Scope batch**</span></span>  
     <span data-ttu-id="5b12f-131">Visualizza il testo del batch nel quale viene visualizzata l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b12f-131">Displays the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="5b12f-132">**Nome oggetto dell'ambito**</span><span class="sxs-lookup"><span data-stu-id="5b12f-132">**Scope object name**</span></span>  
     <span data-ttu-id="5b12f-133">Quando il tipo di ambito è OBJECT, viene visualizzato il nome della stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] , della funzione scalare definita dall'utente o del trigger DML in cui viene visualizzata l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b12f-133">When the scope type is OBJECT, displays the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="5b12f-134">**Nome schema ambito**</span><span class="sxs-lookup"><span data-stu-id="5b12f-134">**Scope schema name**</span></span>  
     <span data-ttu-id="5b12f-135">Quando il tipo di ambito è OBJECT, viene visualizzato il nome dello schema che contiene l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5b12f-135">When the scope type is OBJECT, displays the name of the schema in which the object is contained.</span></span>  
  
     <span data-ttu-id="5b12f-136">**Tipo di ambito**</span><span class="sxs-lookup"><span data-stu-id="5b12f-136">**Scope type**</span></span>  
     <span data-ttu-id="5b12f-137">Visualizza il tipo di entità nel quale viene visualizzata l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b12f-137">Displays the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="5b12f-138">Viene specificato il contesto per adeguare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] alla guida di piano.</span><span class="sxs-lookup"><span data-stu-id="5b12f-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="5b12f-139">I valori possibili sono **OBJECT**, **SQL**e **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="5b12f-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
     <span data-ttu-id="5b12f-140">**Istruzione**</span><span class="sxs-lookup"><span data-stu-id="5b12f-140">**Statement**</span></span>  
     <span data-ttu-id="5b12f-141">Viene visualizzata l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] sulla quale deve essere applicata la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="5b12f-141">Displays the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is applied.</span></span>  
  
4.  <span data-ttu-id="5b12f-142">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b12f-142">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b12f-143">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b12f-143">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="5b12f-144">Per visualizzare le proprietà di una guida di piano</span><span class="sxs-lookup"><span data-stu-id="5b12f-144">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="5b12f-145">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b12f-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b12f-146">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5b12f-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b12f-147">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5b12f-147">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- If a plan guide named "Guide1" already exists in the AdventureWorks2012 database, delete it.  
    USE AdventureWorks2012;  
    GO  
    IF OBJECT_ID(N'Guide1') IS NOT NULL  
       EXEC sp_control_plan_guide N'DROP', N'Guide1';  
    GO  
    -- creates a plan guide named Guide1 based on a SQL statement  
    EXEC sp_create_plan_guide   
        @name = N'Guide1',   
        @stmt = N'SELECT TOP 1 *   
                  FROM Sales.SalesOrderHeader   
                  ORDER BY OrderDate DESC',   
        @type = N'SQL',  
        @module_or_batch = NULL,   
        @params = NULL,   
        @hints = N'OPTION (MAXDOP 1)';  
    GO  
    -- Gets the name, created date, and all other relevant property information on the plan guide created above.   
    SELECT name AS plan_guide_name,  
       create_date,  
       query_text,  
       scope_type_desc,  
       OBJECT_NAME(scope_object_id) AS scope_object_name,  
       scope_batch,  
       parameters,  
       hints,  
       is_disabled  
    FROM sys.plan_guides  
    WHERE name = N'Guide1';  
    GO  
    ```  
  
 <span data-ttu-id="5b12f-148">Per altre informazioni, vedere [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b12f-148">For more information, see [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span></span>  
  
  
