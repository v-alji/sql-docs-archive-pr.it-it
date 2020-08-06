---
title: Ottenere informazioni su una vista | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.viewproperties.general.f1
helpviewer_keywords:
- views [SQL Server], status information
- metadata [SQL Server], views
- dependencies [SQL Server], views
- displaying view information
- views [SQL Server], metadata
- viewing view information
- status information [SQL Server], views
- view dependencies
ms.assetid: 05a73e33-8f85-4fb6-80c1-1b659e753403
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4277aad4c1de0140606575c7ba437408518b3c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623969"
---
# <a name="get-information-about-a-view"></a><span data-ttu-id="cb032-102">Ottenere informazioni su una vista</span><span class="sxs-lookup"><span data-stu-id="cb032-102">Get Information About a View</span></span>
  <span data-ttu-id="cb032-103">Tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] è possibile acquisire informazioni sulla definizione o sulle proprietà di una vista in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb032-103">You can gain information about a view's definition or properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cb032-104">Potrebbe essere necessario visualizzare la definizione della vista per determinare come vengono derivati i dati dalle tabelle di origine o per visualizzare i dati definiti dalla vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-104">You may need to see the definition of the view to understand how its data is derived from the source tables or to see the data defined by the view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cb032-105">Se si cambia il nome di un oggetto a cui viene fatto riferimento da una vista, è necessario modificare la vista in modo che per il relativo testo venga fatto riferimento al nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="cb032-105">If you change the name of an object referenced by a view, you must modify the view so that its text reflects the new name.</span></span> <span data-ttu-id="cb032-106">Prima di rinominare un oggetto, visualizzare innanzitutto le relative dipendenze per determinare se la modifica proposta interessa le viste.</span><span class="sxs-lookup"><span data-stu-id="cb032-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any views are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="cb032-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="cb032-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cb032-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="cb032-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cb032-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cb032-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cb032-110">**Per acquisire informazioni su una vista tramite:**</span><span class="sxs-lookup"><span data-stu-id="cb032-110">**To get information about a view, using:**</span></span>  
  
     [<span data-ttu-id="cb032-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb032-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cb032-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb032-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cb032-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="cb032-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cb032-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cb032-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cb032-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cb032-115">Permissions</span></span>  
 <span data-ttu-id="cb032-116">L'utilizzo di `sp_helptext` per restituire la definizione di una vista richiede l'appartenenza al ruolo **pubblico** .</span><span class="sxs-lookup"><span data-stu-id="cb032-116">Using `sp_helptext` to return the definition of a view requires membership in the **public** role.</span></span> <span data-ttu-id="cb032-117">L'utilizzo di `sys.sql_expression_dependencies` per individuare tutte le dipendenze in una vista richiede l'autorizzazione VIEW DEFINITION sul database e l'autorizzazione SELECT su `sys.sql_expression_dependencies` per il database.</span><span class="sxs-lookup"><span data-stu-id="cb032-117">Using `sys.sql_expression_dependencies` to find all the dependencies on a view requires VIEW DEFINITION permission on the database and SELECT permission on `sys.sql_expression_dependencies` for the database.</span></span> <span data-ttu-id="cb032-118">Le definizioni dell'oggetto di sistema, come quelle restituite in SELECT OBJECT_DEFINITION sono visibili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="cb032-118">System object definitions, like the ones returned in SELECT OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cb032-119">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb032-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="get-view-properties-by-using-object-explorer"></a><span data-ttu-id="cb032-120">Acquisire le proprietà di visualizzazione tramite Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="cb032-120">Get view properties by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="cb032-121">In **Esplora oggetti**fare clic sul segno più accanto al database contenente la vista in cui si desidera visualizzare le proprietà, quindi fare di nuovo clic sul segno più per espandere la cartella **Viste** .</span><span class="sxs-lookup"><span data-stu-id="cb032-121">In **Object Explorer**, click the plus sign next to the database that contains the view to which you want to view the properties, and then click the plus sign to expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="cb032-122">Fare clic con il pulsante destro del mouse sulla vista di cui si vogliono visualizzare le proprietà e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cb032-122">Right-click the view of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="cb032-123">Le seguenti proprietà vengono visualizzate nella finestra di dialogo **Proprietà vista** .</span><span class="sxs-lookup"><span data-stu-id="cb032-123">The following properties show in the **View Properties** dialog box.</span></span>  
  
     <span data-ttu-id="cb032-124">**Database**</span><span class="sxs-lookup"><span data-stu-id="cb032-124">**Database**</span></span>  
     <span data-ttu-id="cb032-125">Nome del database contenente la vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-125">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="cb032-126">**Server**</span><span class="sxs-lookup"><span data-stu-id="cb032-126">**Server**</span></span>  
     <span data-ttu-id="cb032-127">Nome dell'istanza del server corrente.</span><span class="sxs-lookup"><span data-stu-id="cb032-127">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="cb032-128">**Utente**</span><span class="sxs-lookup"><span data-stu-id="cb032-128">**User**</span></span>  
     <span data-ttu-id="cb032-129">Nome dell'utente della connessione.</span><span class="sxs-lookup"><span data-stu-id="cb032-129">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="cb032-130">**Data creazione**</span><span class="sxs-lookup"><span data-stu-id="cb032-130">**Created date**</span></span>  
     <span data-ttu-id="cb032-131">Indica la data di creazione della vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-131">Displays the date the view was created.</span></span>  
  
     <span data-ttu-id="cb032-132">**Nome**</span><span class="sxs-lookup"><span data-stu-id="cb032-132">**Name**</span></span>  
     <span data-ttu-id="cb032-133">Nome della vista corrente.</span><span class="sxs-lookup"><span data-stu-id="cb032-133">The name of the current view.</span></span>  
  
     <span data-ttu-id="cb032-134">**Schema**</span><span class="sxs-lookup"><span data-stu-id="cb032-134">**Schema**</span></span>  
     <span data-ttu-id="cb032-135">Consente di visualizzare lo schema proprietario della vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-135">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="cb032-136">**Oggetto di sistema**</span><span class="sxs-lookup"><span data-stu-id="cb032-136">**System object**</span></span>  
     <span data-ttu-id="cb032-137">Indica se la vista è un oggetto di sistema.</span><span class="sxs-lookup"><span data-stu-id="cb032-137">Indicates whether the view is a system object.</span></span> <span data-ttu-id="cb032-138">I valori sono True e False.</span><span class="sxs-lookup"><span data-stu-id="cb032-138">Values are True and False.</span></span>  
  
     <span data-ttu-id="cb032-139">**ANSI NULLs**</span><span class="sxs-lookup"><span data-stu-id="cb032-139">**ANSI NULLs**</span></span>  
     <span data-ttu-id="cb032-140">Indica se l'oggetto è stato creato con l'opzione ANSI NULLs.</span><span class="sxs-lookup"><span data-stu-id="cb032-140">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="cb032-141">**Crittografata**</span><span class="sxs-lookup"><span data-stu-id="cb032-141">**Encrypted**</span></span>  
     <span data-ttu-id="cb032-142">Indica se la vista è crittografata.</span><span class="sxs-lookup"><span data-stu-id="cb032-142">Indicates whether the view is encrypted.</span></span> <span data-ttu-id="cb032-143">I valori sono True e False.</span><span class="sxs-lookup"><span data-stu-id="cb032-143">Values are True and False.</span></span>  
  
     <span data-ttu-id="cb032-144">**Identificatore delimitato**</span><span class="sxs-lookup"><span data-stu-id="cb032-144">**Quoted identifier**</span></span>  
     <span data-ttu-id="cb032-145">Indica se l'oggetto è stato creato con l'opzione quoted identifier.</span><span class="sxs-lookup"><span data-stu-id="cb032-145">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="cb032-146">**Associata a schema**</span><span class="sxs-lookup"><span data-stu-id="cb032-146">**Schema bound**</span></span>  
     <span data-ttu-id="cb032-147">Indica se la vista è associata a uno schema.</span><span class="sxs-lookup"><span data-stu-id="cb032-147">Indicates whether the view is schema-bound.</span></span> <span data-ttu-id="cb032-148">I valori sono True e False.</span><span class="sxs-lookup"><span data-stu-id="cb032-148">Values are True and False.</span></span> <span data-ttu-id="cb032-149">Per informazioni sulle viste associate a schemi, vedere la sezione SCHEMABINDING di[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cb032-149">For information about schema-bound views, see the SCHEMABINDING portion of [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
#### <a name="getting-view-properties-by-using-the-view-designer-tool"></a><span data-ttu-id="cb032-150">Acquisizione di proprietà delle viste tramite lo strumento Progettazione viste</span><span class="sxs-lookup"><span data-stu-id="cb032-150">Getting view properties by using the View Designer tool</span></span>  
  
1.  <span data-ttu-id="cb032-151">In **Esplora oggetti**espandere il database contenente la vista in cui si desidera visualizzare le proprietà, quindi espandere la cartella **Viste** .</span><span class="sxs-lookup"><span data-stu-id="cb032-151">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="cb032-152">Fare clic con il pulsante destro del mouse sulla vista di cui si vogliono visualizzare le proprietà e scegliere **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="cb032-152">Right-click the view of which you want to view the properties and select **Design**.</span></span>  
  
3.  <span data-ttu-id="cb032-153">Fare clic con il pulsante destro del mouse sullo spazio vuoto del riquadro Diagramma, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cb032-153">Right-click in the blank space of the Diagram pane and click **Properties**.</span></span>  
  
     <span data-ttu-id="cb032-154">Le seguenti proprietà vengono visualizzate nel riquadro **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="cb032-154">The following properties show in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="cb032-155">**(Nome)**</span><span class="sxs-lookup"><span data-stu-id="cb032-155">**(Name)**</span></span>  
     <span data-ttu-id="cb032-156">Nome della vista corrente.</span><span class="sxs-lookup"><span data-stu-id="cb032-156">The name of the current view.</span></span>  
  
     <span data-ttu-id="cb032-157">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="cb032-157">**Database Name**</span></span>  
     <span data-ttu-id="cb032-158">Nome del database contenente la vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-158">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="cb032-159">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cb032-159">**Description**</span></span>  
     <span data-ttu-id="cb032-160">Breve descrizione della vista corrente.</span><span class="sxs-lookup"><span data-stu-id="cb032-160">A brief description of the current view.</span></span>  
  
     <span data-ttu-id="cb032-161">**Schema**</span><span class="sxs-lookup"><span data-stu-id="cb032-161">**Schema**</span></span>  
     <span data-ttu-id="cb032-162">Consente di visualizzare lo schema proprietario della vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-162">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="cb032-163">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="cb032-163">**Server Name**</span></span>  
     <span data-ttu-id="cb032-164">Nome dell'istanza del server corrente.</span><span class="sxs-lookup"><span data-stu-id="cb032-164">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="cb032-165">**Associa a schema**</span><span class="sxs-lookup"><span data-stu-id="cb032-165">**Bind to Schema**</span></span>  
     <span data-ttu-id="cb032-166">Con questa proprietà gli utenti non possono modificare in alcun modo gli oggetti sottostanti che contribuiscono a questa vista per evitare di invalidare la relativa definizione.</span><span class="sxs-lookup"><span data-stu-id="cb032-166">Prevents users from modifying the underlying objects that contribute to this view in any way that would invalidate the view definition.</span></span>  
  
     <span data-ttu-id="cb032-167">**Deterministico**</span><span class="sxs-lookup"><span data-stu-id="cb032-167">**Deterministic**</span></span>  
     <span data-ttu-id="cb032-168">Indica se il tipo di dati della colonna selezionata può essere determinato con certezza</span><span class="sxs-lookup"><span data-stu-id="cb032-168">Shows whether the data type of the selected column can be determined with certainty</span></span>  
  
     <span data-ttu-id="cb032-169">**Valori Distinct**</span><span class="sxs-lookup"><span data-stu-id="cb032-169">**Distinct Values**</span></span>  
     <span data-ttu-id="cb032-170">Viene specificato che tramite la query verranno esclusi i duplicati nella vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-170">Specifies that the query will filter out duplicates in the view.</span></span> <span data-ttu-id="cb032-171">Questa opzione risulta utile quando si utilizzano solo alcune colonne di una tabella e in queste colonne potrebbero essere contenuti valori duplicati. L'opzione è inoltre utile quando dalla creazione di un join di due o più tabelle vengono generate righe duplicate nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="cb032-171">This option is useful when you are using only some of the columns from a table and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="cb032-172">Selezionare questa opzione equivale a inserire la parola chiave DISTINCT nell'istruzione del riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="cb032-172">Choosing this option is equivalent to inserting the keyword DISTINCT into the statement in the SQL pane.</span></span>  
  
     <span data-ttu-id="cb032-173">**Estensione GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="cb032-173">**GROUP BY Extension**</span></span>  
     <span data-ttu-id="cb032-174">Viene specificato che sono disponibili opzioni aggiuntive per le viste basate su query di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="cb032-174">Specifies that additional options for views based on aggregate queries are available.</span></span>  
  
     <span data-ttu-id="cb032-175">**Tutte le colonne**</span><span class="sxs-lookup"><span data-stu-id="cb032-175">**Output All Columns**</span></span>  
     <span data-ttu-id="cb032-176">Viene mostrato se tutte le colonne vengono restituite dalla vista selezionata.</span><span class="sxs-lookup"><span data-stu-id="cb032-176">Shows whether all columns are returned by the selected view.</span></span> <span data-ttu-id="cb032-177">Questa proprietà viene impostata durante la creazione della vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-177">This is set at the time the view is created.</span></span>  
  
     <span data-ttu-id="cb032-178">**Commento SQL**</span><span class="sxs-lookup"><span data-stu-id="cb032-178">**SQL Comment**</span></span>  
     <span data-ttu-id="cb032-179">Visualizza una descrizione delle istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="cb032-179">Shows a description of the SQL statements.</span></span> <span data-ttu-id="cb032-180">Per visualizzare la descrizione completa o modificarla, fare clic su di essa e quindi sui puntini di sospensione **(...)** a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="cb032-180">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="cb032-181">Nei commenti è possibile specificare, ad esempio, quali utenti utilizzano la vista e quando.</span><span class="sxs-lookup"><span data-stu-id="cb032-181">Your comments might include information such as who uses the view and when they use it.</span></span>  
  
     <span data-ttu-id="cb032-182">**Specifica TOP**</span><span class="sxs-lookup"><span data-stu-id="cb032-182">**Top Specification**</span></span>  
     <span data-ttu-id="cb032-183">Si espande per visualizzare le proprietà **Top**, **Espressione**, **Percentuale**e **With Ties**</span><span class="sxs-lookup"><span data-stu-id="cb032-183">Expands to show properties for the **Top**, **Expression**, **Percent**, and **With Ties** properties.</span></span>  
  
     <span data-ttu-id="cb032-184">**(In alto)**</span><span class="sxs-lookup"><span data-stu-id="cb032-184">**(Top)**</span></span>  
     <span data-ttu-id="cb032-185">Specifica che la vista includerà una clausola TOP che restituirà soltanto le prime n righe o il primo n% delle righe del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="cb032-185">Specifies that the view will include a TOP clause, which returns only the first n rows or first n percentage of rows in the result set.</span></span> <span data-ttu-id="cb032-186">Per impostazione predefinita, nella vista vengono restituite le prime 10 righe del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="cb032-186">The default is that the view returns the first 10 rows in the result set.</span></span> <span data-ttu-id="cb032-187">Utilizzare questa proprietà per modificare il numero di righe restituito o specificare una percentuale diversa</span><span class="sxs-lookup"><span data-stu-id="cb032-187">Use this to change the number of rows to return or to specify a different percentage</span></span>  
  
     <span data-ttu-id="cb032-188">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="cb032-188">**Expression**</span></span>  
     <span data-ttu-id="cb032-189">Visualizza la percentuale (se l'opzione **Percentuale** è impostata su **Sì**) o i record (se l'opzione **Percentuale** è impostata su **No**) restituiti dalla vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-189">Shows what percent (if **Percent** is set to **Yes**) or records (if **Percent** is set to **No**) that the view will return.</span></span>  
  
     <span data-ttu-id="cb032-190">**Percentuale**</span><span class="sxs-lookup"><span data-stu-id="cb032-190">**Percent**</span></span>  
     <span data-ttu-id="cb032-191">Specifica che la query includerà una clausola **TOP** che restituirà soltanto il primo n percento di righe del set di risultati</span><span class="sxs-lookup"><span data-stu-id="cb032-191">Specifies that the query will include a **TOP** clause, returning only the first n percentage of rows in the result set</span></span>  
  
     <span data-ttu-id="cb032-192">**Con valori equivalenti**</span><span class="sxs-lookup"><span data-stu-id="cb032-192">**With Ties**</span></span>  
     <span data-ttu-id="cb032-193">Specifica che la vista includerà una clausola **WITH TIES** .</span><span class="sxs-lookup"><span data-stu-id="cb032-193">Specifies that the view will include a **WITH TIES** clause.</span></span> <span data-ttu-id="cb032-194">**WITH TIES** è utile se nella vista sono incluse anche una clausola **ORDER BY** e una **TOP** basate sulla percentuale.</span><span class="sxs-lookup"><span data-stu-id="cb032-194">**WITH TIES** is useful if a view includes an **ORDER BY** clause and a **TOP** clause based on percentage.</span></span> <span data-ttu-id="cb032-195">Se questa opzione è impostata e la percentuale limite specificata rientra in un set di righe con valori identici nella clausola **ORDER BY** , la vista verrà estesa fino a includere tutte queste righe.</span><span class="sxs-lookup"><span data-stu-id="cb032-195">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the **ORDER BY** clause, the view is extended to include all such rows.</span></span>  
  
     <span data-ttu-id="cb032-196">**Specifica aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="cb032-196">**Update Specification**</span></span>  
     <span data-ttu-id="cb032-197">Si espande per visualizzare le proprietà **Aggiorna in base alle regole della vista** e **Opzione Check** .</span><span class="sxs-lookup"><span data-stu-id="cb032-197">Expands to show properties for the **Update Using View Rules** and **Check Option** properties.</span></span>  
  
     <span data-ttu-id="cb032-198">**(Aggiorna in base alle regole della vista)**</span><span class="sxs-lookup"><span data-stu-id="cb032-198">**(Update Using View Rules)**</span></span>  
     <span data-ttu-id="cb032-199">Viene indicato che tutti gli aggiornamenti e gli inserimenti nella vista saranno convertiti da Microsoft Data Access Components (MDAC) in istruzioni SQL che fanno riferimento alla vista piuttosto che alle tabelle di base della vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-199">Indicates that all updates and insertions to the view will be translated by Microsoft Data Access Components (MDAC) into SQL statements that refer to the view, rather than into SQL statements that refer directly to the view's base tables.</span></span>  
  
     <span data-ttu-id="cb032-200">In alcuni casi, in MDAC le operazioni di aggiornamento e inserimento nella vista vengono presentate come aggiornamenti e inserimenti nelle tabelle di base sottostanti della vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-200">In some cases, MDAC manifests view update and view insert operations as updates and inserts against the view's underlying base tables.</span></span> <span data-ttu-id="cb032-201">Selezionando **Aggiorna in base alle regole della vista**è possibile assicurarsi che tramite MDAC le operazioni di aggiornamento e inserimento vengano generate nella vista stessa.</span><span class="sxs-lookup"><span data-stu-id="cb032-201">By selecting **Update Using View Rules**, you can ensure that MDAC generates update and insert operations against the view itself.</span></span>  
  
     <span data-ttu-id="cb032-202">**Opzione Check**</span><span class="sxs-lookup"><span data-stu-id="cb032-202">**Check Option**</span></span>  
     <span data-ttu-id="cb032-203">Indica che quando si apre questa vista e si modifica il riquadro **Risultati** l'origine dati verifica se i dati aggiunti o modificati soddisfano la clausola **WHERE** della definizione della vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-203">Indicates that when you open this view and modify the **Results** pane, the data source checks whether the added or modified data satisfies the **WHERE** clause of the view definition.</span></span> <span data-ttu-id="cb032-204">Se la modifica non soddisfa la clausola **WHERE** , verrà visualizzato un errore con ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="cb032-204">If your modification do not satisfy the **WHERE** clause, you will see an error with more information.</span></span>  
  
#### <a name="to-get-dependencies-on-the-view"></a><span data-ttu-id="cb032-205">Per acquisire dipendenze dalla vista</span><span class="sxs-lookup"><span data-stu-id="cb032-205">To get dependencies on the view</span></span>  
  
1.  <span data-ttu-id="cb032-206">In **Esplora oggetti**espandere il database contenente la vista in cui si desidera visualizzare le proprietà, quindi espandere la cartella **Viste** .</span><span class="sxs-lookup"><span data-stu-id="cb032-206">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="cb032-207">Fare clic con il pulsante destro del mouse sulla vista di cui si vogliono visualizzare le proprietà e selezionare **Visualizza dipendenze**.</span><span class="sxs-lookup"><span data-stu-id="cb032-207">Right-click the view of which you want to view the properties and select **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="cb032-208">Selezionare **Oggetti che dipendono da [nome vista]** per visualizzare gli oggetti che fanno riferimento alla vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-208">Select **Objects that depend on [view name]** to display the objects that refer to the view.</span></span>  
  
4.  <span data-ttu-id="cb032-209">Selezionare **Oggetti da cui dipende [nome vista]** per visualizzare gli oggetti a cui viene fatto riferimento dalla vista.</span><span class="sxs-lookup"><span data-stu-id="cb032-209">Select **Objects on which [view name] depends** to display the objects that are referenced by the view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cb032-210">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb032-210">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-view"></a><span data-ttu-id="cb032-211">Per acquisire la definizione e le proprietà di una vista</span><span class="sxs-lookup"><span data-stu-id="cb032-211">To get the definition and properties of a view</span></span>  
  
1.  <span data-ttu-id="cb032-212">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb032-212">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cb032-213">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="cb032-213">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cb032-214">Copiare e incollare uno degli esempi seguenti nella finestra della query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="cb032-214">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition, uses_ansi_nulls, uses_quoted_identifier, is_schema_bound  
    FROM sys.sql_modules  
    WHERE object_id = OBJECT_ID('HumanResources.vEmployee');   
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID('HumanResources.vEmployee')) AS ObjectDefinition;   
    GO  
    ```  
  
    ```  
    EXEC sp_helptext 'HumanResources.vEmployee';  
    ```  
  
 <span data-ttu-id="cb032-215">Per altre informazioni, vedere [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) e [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cb032-215">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) and [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-view"></a><span data-ttu-id="cb032-216">Per acquisire le dipendenze di una vista</span><span class="sxs-lookup"><span data-stu-id="cb032-216">To get the dependencies of a view</span></span>  
  
1.  <span data-ttu-id="cb032-217">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb032-217">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cb032-218">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="cb032-218">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cb032-219">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="cb032-219">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');  
    GO  
    ```  
  
 <span data-ttu-id="cb032-220">Per altre informazioni, vedere [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) e [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cb032-220">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
