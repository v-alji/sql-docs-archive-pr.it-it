---
title: Creare una nuova guida di piano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.designer.newplanguide.f1
helpviewer_keywords:
- creating plan guides
- plan guides [SQL Server]. creating
ms.assetid: e1ad78bb-4857-40ea-a0c6-dcf5c28aef2f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60ba31e2a63575a316db5befb397bea59c0ad1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637826"
---
# <a name="create-a-new-plan-guide"></a><span data-ttu-id="6feb1-102">Creare una nuova guida di piano</span><span class="sxs-lookup"><span data-stu-id="6feb1-102">Create a New Plan Guide</span></span>
  <span data-ttu-id="6feb1-103">È possibile creare una guida di piano in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6feb1-103">You can create a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6feb1-104">Le guide di piano influiscono sull'ottimizzazione delle query mediante l'aggiunta di hint o di un piano di query fisso.</span><span class="sxs-lookup"><span data-stu-id="6feb1-104">Plan guides influence query optimization by attaching query hints or a fixed query plan to them.</span></span> <span data-ttu-id="6feb1-105">Nel piano di guida si specifica l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] da ottimizzare e la clausola OPTION che contiene gli hint che si desidera utilizzare per l'ottimizzazione della query o un piano di query specifico che si desidera utilizzare per ottimizzare la query.</span><span class="sxs-lookup"><span data-stu-id="6feb1-105">In the plan guide, you specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that you want optimized and either an OPTION clause that contains the query hints you want to use or a specific query plan you want to use to optimize the query.</span></span> <span data-ttu-id="6feb1-106">Quando viene eseguita la query, in Query Optimizer è possibile far corrispondere l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] alla guida di piano e associare la clausola OPTION alla query in fase di esecuzione oppure utilizzare il piano di query specificato.</span><span class="sxs-lookup"><span data-stu-id="6feb1-106">When the query executes, the query optimizer matches the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide and either attaches the OPTION clause to the query at run time or uses the specified query plan.</span></span>  
  
 <span data-ttu-id="6feb1-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6feb1-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6feb1-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="6feb1-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6feb1-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6feb1-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6feb1-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6feb1-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6feb1-111">**Per creare una guida di piano utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="6feb1-111">**To create a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="6feb1-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6feb1-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6feb1-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6feb1-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6feb1-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6feb1-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6feb1-115">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6feb1-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6feb1-116">Gli argomenti per sp_create_plan_guide devono essere inseriti nell'ordine illustrato.</span><span class="sxs-lookup"><span data-stu-id="6feb1-116">The arguments to sp_create_plan_guide must be provided in the order that is shown.</span></span> <span data-ttu-id="6feb1-117">Quando si specificano valori per i parametri di `sp_create_plan_guide`, è necessario specificare in modo esplicito tutti i nomi dei parametri oppure nessuno.</span><span class="sxs-lookup"><span data-stu-id="6feb1-117">When you supply values for the parameters of `sp_create_plan_guide`, all parameter names must be specified explicitly, or none at all.</span></span> <span data-ttu-id="6feb1-118">Se ad esempio si specifica `@name =`, è necessario specificare anche `@stmt =`, `@type =` e così via.</span><span class="sxs-lookup"><span data-stu-id="6feb1-118">For example, if `@name =` is specified, then `@stmt =` , `@type =`, and so on, must also be specified.</span></span> <span data-ttu-id="6feb1-119">Analogamente, se `@name =` viene omesso e viene specificato soltanto il valore del parametro, è necessario omettere anche i nomi dei parametri restanti e specificarne solo il valore.</span><span class="sxs-lookup"><span data-stu-id="6feb1-119">Likewise, if `@name =` is omitted and only the parameter value is provided, the remaining parameter names must also be omitted, and only their values provided.</span></span> <span data-ttu-id="6feb1-120">I nomi degli argomenti hanno scopo esclusivamente descrittivo, per facilitare la comprensione della sintassi.</span><span class="sxs-lookup"><span data-stu-id="6feb1-120">Argument names are for descriptive purposes only, to help understand the syntax.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6feb1-121">non verifica che il nome di parametro specificato corrisponda al nome del parametro nella posizione in cui il nome viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6feb1-121">does not verify that the specified parameter name matches the name for the parameter in the position where the name is used.</span></span>  
  
-   <span data-ttu-id="6feb1-122">È possibile creare più guide di piano OBJECT o SQL per la stessa query e batch o modulo.</span><span class="sxs-lookup"><span data-stu-id="6feb1-122">You can create more than one OBJECT or SQL plan guide for the same query and batch or module.</span></span> <span data-ttu-id="6feb1-123">Tuttavia è possibile abilitare una sola guida di piano alla volta.</span><span class="sxs-lookup"><span data-stu-id="6feb1-123">However, only one plan guide can be enabled at any given time.</span></span>  
  
-   <span data-ttu-id="6feb1-124">Non è possibile creare guide di piano di tipo OBJECT per un valore @module_or_batch che fa riferimento a una stored procedure, una funzione o un trigger DML che specifica la clausola WITH ENCRYPTION o che è temporaneo.</span><span class="sxs-lookup"><span data-stu-id="6feb1-124">Plan guides of type OBJECT cannot be created for an @module_or_batch value that references a stored procedure, function, or DML trigger that specifies the WITH ENCRYPTION clause or that is temporary.</span></span>  
  
-   <span data-ttu-id="6feb1-125">Se si tenta di eliminare o modificare una funzione, una stored procedure o un trigger DML a cui viene fatto riferimento in una guida di piano abilitata o disabilitata, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="6feb1-125">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="6feb1-126">Viene generato un errore anche se si cerca di eliminare una tabella per la quale è stato definito un trigger a cui una guida di piano fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="6feb1-126">Trying to drop a table that has a trigger defined on it that is referenced by a plan guide also causes an error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6feb1-127">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6feb1-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6feb1-128">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6feb1-128">Permissions</span></span>  
 <span data-ttu-id="6feb1-129">Per creare una guida di piano di tipo OBJECT, è necessario disporre dell'autorizzazione ALTER per l'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="6feb1-129">To create a plan guide of type OBJECT, requires ALTER permission on the referenced object.</span></span> <span data-ttu-id="6feb1-130">Per creare una guida di piano di tipo SQL o TEMPLATE, è necessario disporre dell'autorizzazione ALTER per il database corrente.</span><span class="sxs-lookup"><span data-stu-id="6feb1-130">To create a plan guide of type SQL or TEMPLATE, requires ALTER permission on the current database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6feb1-131">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6feb1-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="6feb1-132">Per creare una guida di piano</span><span class="sxs-lookup"><span data-stu-id="6feb1-132">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="6feb1-133">Fare clic sul segno più per espandere il database in cui si desidera creare una guida di piano, quindi fare clic sul segno più per espandere la cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="6feb1-133">Click the plus sign to expand the database in which you want to create a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="6feb1-134">Fare clic con il pulsante destro del mouse sulla cartella **guide di piano** e selezionare **nuova guida di piano..**..</span><span class="sxs-lookup"><span data-stu-id="6feb1-134">Right-click the **Plan Guides** folder and select **New Plan Guide...**.</span></span>  
  
3.  <span data-ttu-id="6feb1-135">Nella casella **Nome** della finestra di dialogo **Nuova guida di piano** immettere il nome della guida di piano.</span><span class="sxs-lookup"><span data-stu-id="6feb1-135">In the **New Plan Guide** dialog box, in the **Name** box, enter the name of the plan guide.</span></span>  
  
4.  <span data-ttu-id="6feb1-136">Nella casella **Istruzione** immettere l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] sulla quale deve essere applicata la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="6feb1-136">In the **Statement** box, enter the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is to be applied.</span></span>  
  
5.  <span data-ttu-id="6feb1-137">Nell'elenco **Tipo di ambito** selezionare il tipo di entità in cui l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="6feb1-137">In the **Scope type** list, select the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="6feb1-138">Viene specificato il contesto per adeguare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] alla guida di piano.</span><span class="sxs-lookup"><span data-stu-id="6feb1-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="6feb1-139">I valori possibili sono **OBJECT**, **SQL**e **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="6feb1-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
6.  <span data-ttu-id="6feb1-140">Nella casella **Batch ambito** immettere il testo del batch in cui l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="6feb1-140">In the **Scope batch** box, enter the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="6feb1-141">Nel testo del batch non può essere inclusa un'istruzione USE\`\`*database* .</span><span class="sxs-lookup"><span data-stu-id="6feb1-141">The batch text cannot include a USE\`\`*database* statement.</span></span> <span data-ttu-id="6feb1-142">La casella **Batch ambito** è disponibile solo quando come tipo di ambito è selezionato **SQL** .</span><span class="sxs-lookup"><span data-stu-id="6feb1-142">The **Scope batch** box is only available when **SQL** is selected as a scope type.</span></span> <span data-ttu-id="6feb1-143">Se non è stato immesso alcun dato nella casella relativa al batch ambito quando SQL è il tipo di ambito, il valore del testo del batch viene impostato sullo stesso valore inserito nella casella **Istruzione** .</span><span class="sxs-lookup"><span data-stu-id="6feb1-143">If nothing is entered in the scope batch box when SQL is the scope type, then the value of the batch text is set to the same value as is in the **Statement** box.</span></span>  
  
7.  <span data-ttu-id="6feb1-144">Nell'elenco **Nome schema ambito** immettere il nome dello schema in cui è contenuto l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6feb1-144">In the **Scope schema name** list, enter the name of the schema in which the object is contained.</span></span> <span data-ttu-id="6feb1-145">La casella **Nome schema ambito** è disponibile solo quando come tipo di ambito è selezionato **Oggetto** .</span><span class="sxs-lookup"><span data-stu-id="6feb1-145">The **Scope schema name** box is only available when **Object** is selected as a scope type.</span></span>  
  
8.  <span data-ttu-id="6feb1-146">Nella casella **Nome oggetto ambito** immettere il nome della stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] , della funzione scalare definita dall'utente, della funzione con valori di tabella con istruzioni multiple o del trigger DML in cui viene visualizzata l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6feb1-146">In the **Scope object name** box, enter the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="6feb1-147">La casella **Nome oggetto ambito** è disponibile solo quando come tipo di ambito è selezionato **Oggetto** .</span><span class="sxs-lookup"><span data-stu-id="6feb1-147">The **Scope object name** box is only available when **Object** is selected as a scope type.</span></span>  
  
9. <span data-ttu-id="6feb1-148">Nella casella **Parametri** immettere il nome e il tipo di dati di tutti i parametri incorporati nell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6feb1-148">In the **Parameters** box, enter the parameter name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="6feb1-149">I parametri vengono applicati solo nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6feb1-149">Parameters apply only when either of the following is true:</span></span>  
  
    -   <span data-ttu-id="6feb1-150">Il tipo di ambito è **SQL** o **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="6feb1-150">The scope type is **SQL** or **TEMPLATE**.</span></span> <span data-ttu-id="6feb1-151">Se **TEMPLATE**, i parametri non devono essere NULL.</span><span class="sxs-lookup"><span data-stu-id="6feb1-151">If **TEMPLATE**, parameters must not be NULL.</span></span>  
  
    -   <span data-ttu-id="6feb1-152">L'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] viene sottomessa tramite sp_executesql e non viene specificato un valore per il parametro @params oppure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sottomette internamente un'istruzione dopo averla parametrizzata.</span><span class="sxs-lookup"><span data-stu-id="6feb1-152">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is submitted by using sp_executesql and a value for the parameter is specified, or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internally submits a statement after parameterizing it.</span></span>  
  
10. <span data-ttu-id="6feb1-153">Nella casella **Hint** immettere gli hint per la query o il piano di query da applicare all'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6feb1-153">In the **Hints** box, enter the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="6feb1-154">Per specificare uno o più hint per la query, immettere una clausola OPTION valida.</span><span class="sxs-lookup"><span data-stu-id="6feb1-154">To specify one or more query hints, enter a valid OPTION clause.</span></span>  
  
11. <span data-ttu-id="6feb1-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6feb1-155">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6feb1-156">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6feb1-156">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="6feb1-157">Per creare una guida di piano</span><span class="sxs-lookup"><span data-stu-id="6feb1-157">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="6feb1-158">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6feb1-158">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6feb1-159">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="6feb1-159">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6feb1-160">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="6feb1-160">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
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
  
    ```  
  
 <span data-ttu-id="6feb1-161">Per altre informazioni, vedere [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6feb1-161">For more information, see [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span></span>  
  
  
