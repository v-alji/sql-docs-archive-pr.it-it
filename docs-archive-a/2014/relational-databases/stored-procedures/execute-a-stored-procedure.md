---
title: Eseguire una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.executeprocedure.f1
- sql12.swb.executeprocedure.general.f1
helpviewer_keywords:
- stored procedures [SQL Server], parameters
- extended stored procedures [SQL Server], executing
- system stored procedures [SQL Server], executing
- stored procedures [SQL Server], executing
- user-defined stored procedures [SQL Server]
ms.assetid: a0b1337d-2059-4872-8c62-3f967d8b170f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c679ba7af3ac9f60d312b33c0346e50687387476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636611"
---
# <a name="execute-a-stored-procedure"></a><span data-ttu-id="f8a92-102">Eseguire una stored procedure</span><span class="sxs-lookup"><span data-stu-id="f8a92-102">Execute a Stored Procedure</span></span>
  <span data-ttu-id="f8a92-103">In questo argomento viene illustrato come eseguire una stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8a92-103">This topic describes how to execute a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f8a92-104">Sono disponibili due modi diversi per eseguire una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f8a92-104">There are two different ways to execute a stored procedure.</span></span> <span data-ttu-id="f8a92-105">Il primo e più comune approccio consiste nella chiamata della stored procedure da parte di un'applicazione o un utente.</span><span class="sxs-lookup"><span data-stu-id="f8a92-105">The first and most common approach is for an application or user to call the procedure.</span></span> <span data-ttu-id="f8a92-106">Il secondo approccio consiste nell'impostare la stored procedure per l'esecuzione automatica all'avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8a92-106">The second approach is to set the procedure to run automatically when an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="f8a92-107">Quando una stored procedure viene chiamata da un'applicazione o da un utente, la parola chiave [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE o EXEC viene dichiarata in modo esplicito nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="f8a92-107">When a procedure is called by an application or user, the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE or EXEC keyword is explicitly stated in the call.</span></span> <span data-ttu-id="f8a92-108">In alternativa, è possibile chiamare ed eseguire la stored procedure senza la parola chiave se la stored procedure è la prima istruzione nel batch [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8a92-108">Alternatively, the procedure can be called and executed without the keyword if the procedure is the first statement in the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch.</span></span>  
  
 <span data-ttu-id="f8a92-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="f8a92-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f8a92-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="f8a92-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f8a92-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f8a92-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f8a92-112">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="f8a92-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f8a92-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f8a92-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f8a92-114">**Per eseguire una stored procedure tramite:**</span><span class="sxs-lookup"><span data-stu-id="f8a92-114">**To execute a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="f8a92-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f8a92-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f8a92-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f8a92-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f8a92-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f8a92-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f8a92-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f8a92-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f8a92-119">Le regole di confronto del database chiamante vengono utilizzate per la ricerca dei nomi delle stored procedure di sistema corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f8a92-119">The calling database collation is used when matching system procedure names.</span></span> <span data-ttu-id="f8a92-120">Nei nomi delle stored procedure di sistema nelle chiamate alle stored procedure è pertanto necessario utilizzare sempre la corretta combinazione di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f8a92-120">Therefore, always use the exact case of system procedure names in procedure calls.</span></span> <span data-ttu-id="f8a92-121">Ad esempio, il codice seguente, se eseguito nel contesto di un database con regole di confronto con distinzione tra maiuscole e minuscole, genererà un errore:</span><span class="sxs-lookup"><span data-stu-id="f8a92-121">For example, this code will fail if it is executed in the context of a database that has a case-sensitive collation:</span></span>  
  
    ```sql  
    EXEC SP_heLP; -- Will fail to resolve because SP_heLP does not equal sp_help  
    ```  
  
     <span data-ttu-id="f8a92-122">Per visualizzare i nomi esatti delle stored procedure di sistema, eseguire query nelle viste del catalogo [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) e [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="f8a92-122">To display the exact system procedure names, query the [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) and [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) catalog views.</span></span>  
  
-   <span data-ttu-id="f8a92-123">Se una stored procedure definita dall'utente ha lo stesso nome di una stored procedure di sistema, potrebbe non essere possibile eseguire la prima.</span><span class="sxs-lookup"><span data-stu-id="f8a92-123">If a user-defined procedure has the same name as a system procedure, the user-defined procedure might not ever execute.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f8a92-124">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="f8a92-124">Recommendations</span></span>  
  
-   <span data-ttu-id="f8a92-125">Esecuzione di stored procedure di sistema</span><span class="sxs-lookup"><span data-stu-id="f8a92-125">Executing System Stored Procedures</span></span>  
  
     <span data-ttu-id="f8a92-126">Le stored procedure di sistema iniziano con il prefisso **sp_** .</span><span class="sxs-lookup"><span data-stu-id="f8a92-126">System procedures begin with the prefix **sp_**.</span></span> <span data-ttu-id="f8a92-127">Poiché sono visualizzate logicamente in ogni database definito dall'utente e dal sistema, possono essere eseguite da qualsiasi database senza che sia necessario specificare il nome completo della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f8a92-127">Because they logically appear in all user- and system- defined databases, they can be executed from any database without having to fully quality the procedure name.</span></span> <span data-ttu-id="f8a92-128">È tuttavia consigliabile specificare lo schema in tutti i nomi di stored procedure di sistema con il nome dello schema **sys** per evitare conflitti.</span><span class="sxs-lookup"><span data-stu-id="f8a92-128">However, we recommend schema-qualifying all system procedure names with the **sys** schema name to prevent name conflicts.</span></span> <span data-ttu-id="f8a92-129">Nell'esempio seguente viene illustrato il metodo consigliato per la chiamata a una stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="f8a92-129">The following example demonstrates the recommended method of calling a system procedure.</span></span>  
  
    ```sql  
    EXEC sys.sp_who;  
    ```  
  
-   <span data-ttu-id="f8a92-130">Esecuzione di stored procedure definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="f8a92-130">Executing User-defined Stored Procedures</span></span>  
  
     <span data-ttu-id="f8a92-131">Quando si esegue una stored procedure definita dall'utente, si consiglia di specificare il nome completo della stored procedure con il nome di schema.</span><span class="sxs-lookup"><span data-stu-id="f8a92-131">When executing a user-defined procedure, we recommend qualifying the procedure name with the schema name.</span></span> <span data-ttu-id="f8a92-132">In questo modo, le prestazioni risulteranno leggermente migliorate poiché si evita che debbano essere eseguite ricerche in più schemi tramite il [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8a92-132">This practice gives a small performance boost because the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] does not have to search multiple schemas.</span></span> <span data-ttu-id="f8a92-133">Si evita inoltre che venga eseguita la stored procedure errata se un database dispone di stored procedure con lo stesso nome in più schemi.</span><span class="sxs-lookup"><span data-stu-id="f8a92-133">It also prevents executing the wrong procedure if a database has procedures with the same name in multiple schemas.</span></span>  
  
     <span data-ttu-id="f8a92-134">Nell'esempio seguente viene illustrato il metodo consigliato per l'esecuzione di una stored procedure definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f8a92-134">The following example demonstrates the recommended method to execute a user-defined procedure.</span></span> <span data-ttu-id="f8a92-135">Si noti che la stored procedure accetta un parametro di input.</span><span class="sxs-lookup"><span data-stu-id="f8a92-135">Notice that the procedure accepts one input parameter.</span></span> <span data-ttu-id="f8a92-136">Per informazioni su come specificare i parametri di input e di output, vedere [Specificare i parametri](specify-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f8a92-136">For information about specifying input and output parameters, see [Specify Parameters](specify-parameters.md).</span></span>  
  
    ```sql  
    USE AdventureWorks2012;  
    GO  
    EXEC dbo.uspGetEmployeeManagers @BusinessEntityID = 50;  
    ```  
  
     <span data-ttu-id="f8a92-137">Oppure</span><span class="sxs-lookup"><span data-stu-id="f8a92-137">-Or-</span></span>  
  
    ```sql  
    EXEC AdventureWorks2012.dbo.uspGetEmployeeManagers 50;  
    GO  
    ```  
  
     <span data-ttu-id="f8a92-138">Se si specifica una stored procedure non qualificata definita dall'utente, il [!INCLUDE[ssDE](../../../includes/ssde-md.md)] cerca la stored procedure nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="f8a92-138">If a nonqualified user-defined procedure is specified, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] searches for the procedure in the following order:</span></span>  
  
    1.  <span data-ttu-id="f8a92-139">Schema **sys** del database corrente.</span><span class="sxs-lookup"><span data-stu-id="f8a92-139">The **sys** schema of the current database.</span></span>  
  
    2.  <span data-ttu-id="f8a92-140">Schema predefinito del chiamante se eseguito in un batch o in SQL dinamico.</span><span class="sxs-lookup"><span data-stu-id="f8a92-140">The caller's default schema if it is executed in a batch or in dynamic SQL.</span></span> <span data-ttu-id="f8a92-141">In alternativa, se il nome della stored procedure non completo viene visualizzato all'interno del corpo di un'altra definizione di stored procedure, la ricerca viene eseguita nello schema che contiene quest'ultima subito dopo.</span><span class="sxs-lookup"><span data-stu-id="f8a92-141">Or, if the nonqualified procedure name appears inside the body of another procedure definition, the schema that contains this other procedure is searched next.</span></span>  
  
    3.  <span data-ttu-id="f8a92-142">Schema **dbo** nel database corrente.</span><span class="sxs-lookup"><span data-stu-id="f8a92-142">The **dbo** schema in the current database.</span></span>  
  
-   <span data-ttu-id="f8a92-143">Esecuzione automatica di stored procedure</span><span class="sxs-lookup"><span data-stu-id="f8a92-143">Executing Stored Procedures Automatically</span></span>  
  
     <span data-ttu-id="f8a92-144">Le stored procedure contrassegnate per l'esecuzione automatica vengono eseguite a ogni avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il database **master** viene recuperato durante il processo di avvio.</span><span class="sxs-lookup"><span data-stu-id="f8a92-144">Procedures marked for automatic execution are executed every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts and the **master** database is recovered during that startup process.</span></span> <span data-ttu-id="f8a92-145">L'impostazione di stored procedure per l'esecuzione automatica può essere utile per le operazioni di manutenzione del database o per l'esecuzione continua delle stored procedure come processi di background.</span><span class="sxs-lookup"><span data-stu-id="f8a92-145">Setting up procedures to execute automatically can be useful for performing database maintenance operations or for having procedures run continuously as background processes.</span></span> <span data-ttu-id="f8a92-146">È inoltre possibile utilizzare l'esecuzione automatica delle stored procedure per eseguire attività di sistema o di manutenzione in **tempdb**, ad esempio per creare una tabella temporanea globale.</span><span class="sxs-lookup"><span data-stu-id="f8a92-146">Another use for automatic execution is to have the procedure perform system or maintenance tasks in **tempdb**, such as creating a global temporary table.</span></span> <span data-ttu-id="f8a92-147">In questo modo si è sempre certi della disponibilità di una tabella temporanea quando **tempdb** viene ricreato durante l'avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8a92-147">This makes sure that such a temporary table will always exist when **tempdb** is re-created during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
     <span data-ttu-id="f8a92-148">Una stored procedure eseguita automaticamente utilizza le stesse autorizzazioni dei membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f8a92-148">A procedure that is automatically executed operates with the same permissions as members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="f8a92-149">I messaggi di errore generati dalla stored procedure vengono scritti nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8a92-149">Any error messages generated by the procedure are written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
     <span data-ttu-id="f8a92-150">Non è previsto alcun limite per le procedure di avvio, ma è necessario tenere presente che ogni procedura richiede un thread di lavoro per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f8a92-150">There is no limit to the number of startup procedures you can have, but be aware that each consumes one worker thread while executing.</span></span> <span data-ttu-id="f8a92-151">Se è necessario eseguire più procedure all'avvio, ma non necessariamente in parallelo, è possibile impostare una delle procedure come procedura di avvio che richiama le altre procedure.</span><span class="sxs-lookup"><span data-stu-id="f8a92-151">If you must execute multiple procedures at startup but do not need to execute them in parallel, make one procedure the startup procedure and have that procedure call the other procedures.</span></span> <span data-ttu-id="f8a92-152">In questo modo è sufficiente un solo thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f8a92-152">This uses only one worker thread.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="f8a92-153">Evitare di restituire set di risultati da una stored procedure eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f8a92-153">Do not return any result sets from a procedure that is executed automatically.</span></span> <span data-ttu-id="f8a92-154">Poiché la stored procedure viene eseguita da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anziché da un'applicazione o un utente, non è disponibile una destinazione per i set di risultati.</span><span class="sxs-lookup"><span data-stu-id="f8a92-154">Because the procedure is being executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instead of an application or user, there is nowhere for the result sets to go.</span></span>  
  
-   <span data-ttu-id="f8a92-155">Impostazione, annullamento e controllo dell'esecuzione automatica</span><span class="sxs-lookup"><span data-stu-id="f8a92-155">Setting, Clearing, and Controlling Automatic Execution</span></span>  
  
     <span data-ttu-id="f8a92-156">Solo l'amministratore di sistema (**sa**) può contrassegnare una stored procedure per l'esecuzione automatica.</span><span class="sxs-lookup"><span data-stu-id="f8a92-156">Only the system administrator (**sa**) can mark a procedure to execute automatically.</span></span> <span data-ttu-id="f8a92-157">La stored procedure, inoltre, deve essere nel database **master** , il proprietario deve essere **sa**e deve essere priva di parametri di input o output.</span><span class="sxs-lookup"><span data-stu-id="f8a92-157">In addition, the procedure must be in the **master** database, owned by **sa**, and cannot have input or output parameters.</span></span>  
  
     <span data-ttu-id="f8a92-158">Usare [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) per:</span><span class="sxs-lookup"><span data-stu-id="f8a92-158">Use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to:</span></span>  
  
    1.  <span data-ttu-id="f8a92-159">Designare una stored procedure esistente come procedura di avvio.</span><span class="sxs-lookup"><span data-stu-id="f8a92-159">Designate an existing procedure as a startup procedure.</span></span>  
  
    2.  <span data-ttu-id="f8a92-160">Arrestare l'esecuzione di una stored procedure all'avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8a92-160">Stop a procedure from executing at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f8a92-161">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f8a92-161">Security</span></span>  
 <span data-ttu-id="f8a92-162">Per altre informazioni, vedere [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) e [Clausola EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f8a92-162">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) and [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f8a92-163">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f8a92-163">Permissions</span></span>  
 <span data-ttu-id="f8a92-164">Per altre informazioni, vedere la sezione Autorizzazioni in [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f8a92-164">For more information, see the "Permissions" section in [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f8a92-165">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f8a92-165">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="f8a92-166">Per eseguire una stored procedure</span><span class="sxs-lookup"><span data-stu-id="f8a92-166">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="f8a92-167">In **Esplora oggetti**connettersi a un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], espandere tale istanza, quindi espandere **Database**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-167">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="f8a92-168">Espandere il database desiderato, espandere **Programmabilità**, quindi **Stored procedure**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-168">Expand the database that you want, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  
  
3.  <span data-ttu-id="f8a92-169">Fare clic con il pulsante destro del mouse sulla stored procedure definita dall'utente desiderata e scegliere **Esegui stored procedure**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-169">Right-click the user-defined stored procedure that you want and click **Execute Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="f8a92-170">Nella finestra di dialogo **Esegui stored procedure** specificare un valore per ogni parametro e indicare se deve essere passato un valore Null.</span><span class="sxs-lookup"><span data-stu-id="f8a92-170">In the **Execute Procedure** dialog box, specify a value for each parameter and whether it should pass a null value.</span></span>  
  
     <span data-ttu-id="f8a92-171">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="f8a92-171">**Parameter**</span></span>  
     <span data-ttu-id="f8a92-172">Indica il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="f8a92-172">Indicates the name of the parameter.</span></span>  
  
     <span data-ttu-id="f8a92-173">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="f8a92-173">**Data Type**</span></span>  
     <span data-ttu-id="f8a92-174">Indica il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="f8a92-174">Indicates the data type of the parameter.</span></span>  
  
     <span data-ttu-id="f8a92-175">**Parametro di output**</span><span class="sxs-lookup"><span data-stu-id="f8a92-175">**Output Parameter**</span></span>  
     <span data-ttu-id="f8a92-176">Indica se il parametro è un parametro di output.</span><span class="sxs-lookup"><span data-stu-id="f8a92-176">Indicates if this is an output parameter.</span></span>  
  
     <span data-ttu-id="f8a92-177">**Passa valore Null**</span><span class="sxs-lookup"><span data-stu-id="f8a92-177">**Pass Null Value**</span></span>  
     <span data-ttu-id="f8a92-178">Consente di passare NULL come valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="f8a92-178">Pass a NULL as the value of the parameter.</span></span>  
  
     <span data-ttu-id="f8a92-179">**Valore**</span><span class="sxs-lookup"><span data-stu-id="f8a92-179">**Value**</span></span>  
     <span data-ttu-id="f8a92-180">Digitare il valore del parametro al momento della chiamata alla procedura.</span><span class="sxs-lookup"><span data-stu-id="f8a92-180">Type the value for the parameter when calling the procedure.</span></span>  
  
5.  <span data-ttu-id="f8a92-181">Per eseguire la stored procedure, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-181">To execute the stored procedure, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f8a92-182">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f8a92-182">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="f8a92-183">Per eseguire una stored procedure</span><span class="sxs-lookup"><span data-stu-id="f8a92-183">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="f8a92-184">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8a92-184">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f8a92-185">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-185">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f8a92-186">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-186">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f8a92-187">In questo esempio viene illustrato come eseguire una stored procedure che prevede un parametro.</span><span class="sxs-lookup"><span data-stu-id="f8a92-187">This example shows how to execute a stored procedure that expects one parameter.</span></span> <span data-ttu-id="f8a92-188">Nell'esempio viene eseguita la stored procedure `uspGetEmployeeManagers` con il valore  `6` specificato come parametro `@EmployeeID` .</span><span class="sxs-lookup"><span data-stu-id="f8a92-188">The example executes the `uspGetEmployeeManagers` stored procedure with the value  `6` specified as the `@EmployeeID` parameter.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC dbo.uspGetEmployeeManagers 6;  
GO  
```  
  
#### <a name="to-set-or-clear-a-procedure-for-executing-automatically"></a><span data-ttu-id="f8a92-189">Per impostare o annullare l'esecuzione automatica di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="f8a92-189">To set or clear a procedure for executing automatically</span></span>  
  
1.  <span data-ttu-id="f8a92-190">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8a92-190">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f8a92-191">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-191">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f8a92-192">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-192">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f8a92-193">Questo esempio mostra come usare [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) per impostare una stored procedure per l'esecuzione automatica.</span><span class="sxs-lookup"><span data-stu-id="f8a92-193">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to set a procedure for automatic execution.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionName = ] 'startup'   
    , @OptionValue = 'on';  
```  
  
#### <a name="to-stop-a-procedure-from-executing-automatically"></a><span data-ttu-id="f8a92-194">Per arrestare l'esecuzione automatica di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="f8a92-194">To stop a procedure from executing automatically</span></span>  
  
1.  <span data-ttu-id="f8a92-195">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8a92-195">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f8a92-196">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-196">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f8a92-197">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f8a92-197">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f8a92-198">Questo esempio mostra come usare [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) per arrestare l'esecuzione automatica di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f8a92-198">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to stop a procedure from executing automatically.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionValue = 'off';  
```  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="f8a92-199">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f8a92-199">Example (Transact-SQL)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a92-200">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8a92-200">See Also</span></span>  
 <span data-ttu-id="f8a92-201">[Specificare i parametri](specify-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="f8a92-201">[Specify Parameters](specify-parameters.md) </span></span>  
 <span data-ttu-id="f8a92-202">[Configurare l'opzione di configurazione del server scan for startup procs](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="f8a92-202">[Configure the scan for startup procs Server Configuration Option](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span></span>  
 <span data-ttu-id="f8a92-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f8a92-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="f8a92-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f8a92-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="f8a92-205">Stored procedure &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="f8a92-205">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures-database-engine.md)  
  
  
