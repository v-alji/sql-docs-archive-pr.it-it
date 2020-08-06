---
title: Restituire dati da una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], returning data
- returning data from stored procedure
ms.assetid: 7a428ffe-cd87-4f42-b3f1-d26aa8312bf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 472ca5cf27f7e7ea2b18daa961c19faadcf2251f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638363"
---
# <a name="return-data-from-a-stored-procedure"></a><span data-ttu-id="e37f5-102">Restituire dati da una stored procedure</span><span class="sxs-lookup"><span data-stu-id="e37f5-102">Return Data from a Stored Procedure</span></span>
  <span data-ttu-id="e37f5-103">Sono disponibili due modalità di restituzione di set di risultati o di dati da una procedura a un programma chiamante, cioè i parametri di output e i codici restituiti.</span><span class="sxs-lookup"><span data-stu-id="e37f5-103">There are two ways of returning result sets or data from a procedure to a calling program: output parameters and return codes.</span></span> <span data-ttu-id="e37f5-104">In questo argomento vengono fornite informazioni su entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="e37f5-104">This topic provides information on both approaches.</span></span>  
  
## <a name="returning-data-using-an-output-parameter"></a><span data-ttu-id="e37f5-105">Restituzione di dati tramite un parametro di output</span><span class="sxs-lookup"><span data-stu-id="e37f5-105">Returning Data Using an Output Parameter</span></span>  
 <span data-ttu-id="e37f5-106">Se si specifica la parola chiave OUTPUT per un parametro nella definizione della procedura, il valore corrente del parametro può essere restituito al programma chiamante dalla procedura, se quest'ultima è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e37f5-106">If you specify the OUTPUT keyword for a parameter in the procedure definition, the procedure can return the current value of the parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="e37f5-107">Per salvare il valore del parametro in una variabile che può essere utilizzata nel programma chiamante, in tale programma deve essere utilizzata la parola chiave OUTPUT durante l'esecuzione della procedura.</span><span class="sxs-lookup"><span data-stu-id="e37f5-107">To save the value of the parameter in a variable that can be used in the calling program, the calling program must use the OUTPUT keyword when executing the procedure.</span></span> <span data-ttu-id="e37f5-108">Per altre informazioni sui tipi di dati che possono essere usati come parametri di output, vedere [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e37f5-108">For more information about what data types can be used as output parameters, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
### <a name="examples-of-output-parameter"></a><span data-ttu-id="e37f5-109">Esempi di parametri di output</span><span class="sxs-lookup"><span data-stu-id="e37f5-109">Examples of Output Parameter</span></span>  
 <span data-ttu-id="e37f5-110">Nell'esempio seguente viene illustrata una procedura con un parametro di input e uno di output.</span><span class="sxs-lookup"><span data-stu-id="e37f5-110">The following example shows a procedure with an input and an output parameter.</span></span> <span data-ttu-id="e37f5-111">Il parametro `@SalesPerson` riceve un valore di input specificato dal programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-111">The `@SalesPerson` parameter would receive an input value specified by the calling program.</span></span> <span data-ttu-id="e37f5-112">L'istruzione SELECT usa il valore passato nel parametro di input per ottenere il valore `SalesYTD` corretto.</span><span class="sxs-lookup"><span data-stu-id="e37f5-112">The SELECT statement uses the value passed into the input parameter to obtain the correct `SalesYTD` value.</span></span> <span data-ttu-id="e37f5-113">Assegna anche il valore al parametro di output `@SalesYTD` che restituisce il valore al programma chiamante al termine della procedura.</span><span class="sxs-lookup"><span data-stu-id="e37f5-113">The SELECT statement also assigns the value to the `@SalesYTD` output parameter, which returns the value to the calling program when the procedure exits.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetEmployeeSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetEmployeeSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetEmployeeSalesYTD  
@SalesPerson nvarchar(50),  
@SalesYTD money OUTPUT  
AS    
  
    SET NOCOUNT ON;  
    SELECT @SalesYTD = SalesYTD  
    FROM Sales.SalesPerson AS sp  
    JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
    WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="e37f5-114">Nell'esempio seguente viene chiamata la procedura creata nel primo esempio e viene salvato il valore di output restituito dalla procedura chiamata nella variabile `@SalesYTD` , che è locale nel programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-114">The following example calls the procedure created in the first example and saves the output value returned from the called procedure in the `@SalesYTD` variable, which is local to the calling program.</span></span>  
  
```  
-- Declare the variable to receive the output value of the procedure.  
DECLARE @SalesYTDBySalesPerson money;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTDBySalesPerson  
EXECUTE Sales.uspGetEmployeeSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDBySalesPerson OUTPUT;  
-- Display the value returned by the procedure.  
PRINT 'Year-to-date sales for this employee is ' +   
    convert(varchar(10),@SalesYTDBySalesPerson);  
GO  
  
```  
  
 <span data-ttu-id="e37f5-115">Inoltre, è possibile specificare valori di input per i parametri OUTPUT quando la procedura viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="e37f5-115">Input values can also be specified for OUTPUT parameters when the procedure is executed.</span></span> <span data-ttu-id="e37f5-116">Questa operazione consente alla procedura di ricevere un valore dal programma chiamante, modificare o eseguire operazioni con il valore, quindi restituire il nuovo valore al programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-116">This allows the procedure to receive a value from the calling program, change or perform operations with the value, and then return the new value to the calling program.</span></span> <span data-ttu-id="e37f5-117">Nell'esempio precedente, è possibile assegnare un valore alla variabile `@SalesYTDBySalesPerson` prima che il programma chiami la procedura `Sales.uspGetEmployeeSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="e37f5-117">In the previous example, the `@SalesYTDBySalesPerson` variable can be assigned a value before the program calls the `Sales.uspGetEmployeeSalesYTD` procedure.</span></span> <span data-ttu-id="e37f5-118">L'istruzione di esecuzione passa il valore della variabile `@SalesYTDBySalesPerson` nel parametro OUTPUT `@SalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="e37f5-118">The execute statement would pass the `@SalesYTDBySalesPerson` variable value into the `@SalesYTD` OUTPUT parameter.</span></span> <span data-ttu-id="e37f5-119">Nel corpo della procedura il valore può quindi essere utilizzato per calcoli che consentono di generare un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="e37f5-119">Then in the procedure body, the value could be used for calculations that generate a new value.</span></span> <span data-ttu-id="e37f5-120">Il nuovo valore viene passato di nuovo alla procedura tramite il parametro OUTPUT, aggiornando il valore nella variabile `@SalesYTDBySalesPerson` al termine della procedura.</span><span class="sxs-lookup"><span data-stu-id="e37f5-120">The new value would be passed back out of the procedure through the OUTPUT parameter, updating the value in the `@SalesYTDBySalesPerson` variable when the procedure exits.</span></span> <span data-ttu-id="e37f5-121">Questa funzionalità viene in genere denominata "funzionalità di passaggio per riferimento".</span><span class="sxs-lookup"><span data-stu-id="e37f5-121">This is often referred to as "pass-by-reference capability."</span></span>  
  
 <span data-ttu-id="e37f5-122">Se si specifica OUTPUT per un parametro quando si chiama una procedura e tale parametro non è stato definito utilizzando OUTPUT nella definizione della procedura, viene restituito un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="e37f5-122">If you specify OUTPUT for a parameter when you call a procedure and that parameter is not defined by using OUTPUT in the procedure definition, you get an error message.</span></span> <span data-ttu-id="e37f5-123">Tuttavia, è possibile eseguire una procedura con i parametri di output e non specificare OUTPUT in fase di esecuzione della procedura.</span><span class="sxs-lookup"><span data-stu-id="e37f5-123">However, you can execute a procedure with output parameters and not specify OUTPUT when executing the procedure.</span></span> <span data-ttu-id="e37f5-124">Non viene restituito alcun errore, ma non è possibile utilizzare il valore di output nel programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-124">No error is returned, but you cannot use the output value in the calling program.</span></span>  
  
### <a name="using-the-cursor-data-type-in-output-parameters"></a><span data-ttu-id="e37f5-125">Utilizzo del tipo di dati cursor nei parametri OUTPUT</span><span class="sxs-lookup"><span data-stu-id="e37f5-125">Using the Cursor Data Type in OUTPUT Parameters</span></span>  
 [!INCLUDE[tsql](../../../includes/tsql-md.md)]<span data-ttu-id="e37f5-126">le routine possono utilizzare il `cursor` tipo di dati solo per i parametri di output.</span><span class="sxs-lookup"><span data-stu-id="e37f5-126">procedures can use the `cursor` data type only for OUTPUT parameters.</span></span> <span data-ttu-id="e37f5-127">Se `cursor` per un parametro viene specificato il tipo di dati, è necessario specificare entrambe le parole chiave VARYING e output per tale parametro nella definizione della procedura.</span><span class="sxs-lookup"><span data-stu-id="e37f5-127">If the `cursor` data type is specified for a parameter, both the VARYING and OUTPUT keywords must be specified for that parameter in the procedure definition.</span></span> <span data-ttu-id="e37f5-128">Un parametro può essere specificato solo come OUTPUT, ma se nella dichiarazione del parametro è specificata la parola chiave VARYing, il tipo di dati deve essere `cursor` e deve essere specificata anche la parola chiave output.</span><span class="sxs-lookup"><span data-stu-id="e37f5-128">A parameter can be specified as only OUTPUT but if the VARYING keyword is specified in the parameter declaration, the data type must be `cursor` and the OUTPUT keyword must also be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e37f5-129">Il tipo di dati `cursor` non può essere associato a variabili di applicazione tramite le API di database, quali OLE DB, ODBC, ADO e DB-Library.</span><span class="sxs-lookup"><span data-stu-id="e37f5-129">The `cursor` data type cannot be bound to application variables through the database APIs such as OLE DB, ODBC, ADO, and DB-Library.</span></span> <span data-ttu-id="e37f5-130">Poiché in un'applicazione è possibile eseguire una procedura solo in seguito all'associazione dei parametri OUTPUT, le procedure con parametri OUTPUT di tipo `cursor` non possono essere chiamate dalle API di database.</span><span class="sxs-lookup"><span data-stu-id="e37f5-130">Because OUTPUT parameters must be bound before an application can execute a procedure, procedures with `cursor` OUTPUT parameters cannot be called from the database APIs.</span></span> <span data-ttu-id="e37f5-131">È possibile chiamare queste procedure da trigger, procedure o batch [!INCLUDE[tsql](../../../includes/tsql-md.md)] solo quando la variabile OUTPUT di tipo `cursor` è assegnata a una variabile locale [!INCLUDE[tsql](../../../includes/tsql-md.md)] di tipo `cursor`.</span><span class="sxs-lookup"><span data-stu-id="e37f5-131">These procedures can be called from [!INCLUDE[tsql](../../../includes/tsql-md.md)] batches, procedures, or triggers only when the `cursor` OUTPUT variable is assigned to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] local `cursor` variable.</span></span>  
  
### <a name="rules-for-cursor-output-parameters"></a><span data-ttu-id="e37f5-132">Regole per parametri di output di tipo cursor</span><span class="sxs-lookup"><span data-stu-id="e37f5-132">Rules for Cursor Output Parameters</span></span>  
 <span data-ttu-id="e37f5-133">Quando si esegue la procedura, per i parametri di output di tipo `cursor` vengono applicate le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="e37f5-133">The following rules pertain to `cursor` output parameters when the procedure is executed:</span></span>  
  
-   <span data-ttu-id="e37f5-134">Con cursori forward-only, nel set di risultati del cursore sono incluse solo le righe che al completamento della procedura si trovano oltre la posizione del cursore, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e37f5-134">For a forward-only cursor, the rows returned in the cursor's result set are only those rows at and beyond the position of the cursor at the conclusion of the procedure execution, for example:</span></span>  
  
    -   <span data-ttu-id="e37f5-135">Un cursore non scorrevole viene aperto in una procedura in un set di risultati di 100 righe denominato RS.</span><span class="sxs-lookup"><span data-stu-id="e37f5-135">A nonscrollable cursor is opened in a procedure on a result set named RS of 100 rows.</span></span>  
  
    -   <span data-ttu-id="e37f5-136">La procedura recupera le prime 5 righe del set di risultati RS.</span><span class="sxs-lookup"><span data-stu-id="e37f5-136">The procedure fetches the first 5 rows of result set RS.</span></span>  
  
    -   <span data-ttu-id="e37f5-137">La procedura restituisce il set di risultati al chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-137">The procedure returns to its caller.</span></span>  
  
    -   <span data-ttu-id="e37f5-138">Il set di risultati RS restituito al chiamante include le righe comprese tra la riga 6 e la riga 100 di RS e la posizione del cursore nel chiamante precede la prima riga di RS.</span><span class="sxs-lookup"><span data-stu-id="e37f5-138">The result set RS returned to the caller consists of rows from 6 through 100 of RS, and the cursor in the caller is positioned before the first row of RS.</span></span>  
  
-   <span data-ttu-id="e37f5-139">Con cursori forward-only, se il cursore precede la prima riga quando la procedura è disponibile, l'intero set di risultati viene restituito al trigger, alla procedura o al batch chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-139">For a forward-only cursor, if the cursor is positioned before the first row when the procedure exits, the entire result set is returned to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="e37f5-140">Quando viene restituito, il cursore è posizionato prima della prima riga.</span><span class="sxs-lookup"><span data-stu-id="e37f5-140">When returned, the cursor position is set before the first row.</span></span>  
  
-   <span data-ttu-id="e37f5-141">Con cursori forward-only, se il cursore è posizionato oltre l'ultima riga quando la procedura è disponibile, viene restituito un set di risultati vuoto al trigger, alla procedura o al batch chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-141">For a forward-only cursor, if the cursor is positioned beyond the end of the last row when the procedure exits, an empty result set is returned to the calling batch, procedure, or trigger.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e37f5-142">Un set di risultati vuoto non equivale a un valore Null.</span><span class="sxs-lookup"><span data-stu-id="e37f5-142">An empty result set is not the same as a null value.</span></span>  
  
-   <span data-ttu-id="e37f5-143">Con cursori scorrevoli, quando è disponibile la procedura, tutte le righe del set di risultati vengono restituite al trigger, alla procedura o al batch chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-143">For a scrollable cursor, all the rows in the result set are returned to the calling batch, procedure, or trigger when the procedure exits.</span></span> <span data-ttu-id="e37f5-144">Quando viene restituito, il cursore è nella stessa posizione in cui si trovava durante l'ultima operazione di recupero eseguita dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="e37f5-144">When returned, the cursor position is left at the position of the last fetch executed in the procedure.</span></span>  
  
-   <span data-ttu-id="e37f5-145">Con qualsiasi tipo di cursore, se il cursore è chiuso, viene restituito un valore Null al trigger, alla procedura o al batch chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-145">For any type of cursor, if the cursor is closed, then a null value is passed back to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="e37f5-146">Questa situazione si verifica anche quando un cursore viene assegnato a un parametro, ma non viene mai aperto.</span><span class="sxs-lookup"><span data-stu-id="e37f5-146">This will also be the case if a cursor is assigned to a parameter, but that cursor is never opened.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e37f5-147">Lo stato chiuso di un cursore è rilevante solo in fase di restituzione.</span><span class="sxs-lookup"><span data-stu-id="e37f5-147">The closed state matters only at return time.</span></span> <span data-ttu-id="e37f5-148">È possibile, ad esempio, chiudere un cursore nel corso di una procedura, riaprirlo in una fase successiva e restituire il set di risultati di tale cursore al trigger, alla procedura o al batch chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-148">For example, it is valid to close a cursor part of the way through the procedure, to open it again later in the procedure, and return that cursor's result set to the calling batch, procedure, or trigger.</span></span>  
  
### <a name="examples-of-cursor-output-parameters"></a><span data-ttu-id="e37f5-149">Esempi di parametri di output di tipo cursor</span><span class="sxs-lookup"><span data-stu-id="e37f5-149">Examples of Cursor Output Parameters</span></span>  
 <span data-ttu-id="e37f5-150">Nell'esempio seguente viene creata una stored procedure che specifica un parametro di output `@currency` _ `cursor` utilizzando il `cursor` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e37f5-150">In the following example, a procedure is created that specified an output parameter, `@currency`_`cursor` using the `cursor` data type.</span></span> <span data-ttu-id="e37f5-151">La procedura viene quindi chiamata in un batch.</span><span class="sxs-lookup"><span data-stu-id="e37f5-151">The procedure is then called in a batch.</span></span>  
  
 <span data-ttu-id="e37f5-152">Creare innanzitutto la procedura per la dichiarazione e l'apertura di un cursore per la tabella Currency.</span><span class="sxs-lookup"><span data-stu-id="e37f5-152">First, create the procedure that declares and then opens a cursor on the Currency table.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspCurrencyCursor', 'P' ) IS NOT NULL  
    DROP PROCEDURE dbo.uspCurrencyCursor;  
GO  
CREATE PROCEDURE dbo.uspCurrencyCursor   
    @CurrencyCursor CURSOR VARYING OUTPUT  
AS  
    SET NOCOUNT ON;  
    SET @CurrencyCursor = CURSOR  
    FORWARD_ONLY STATIC FOR  
      SELECT CurrencyCode, Name  
      FROM Sales.Currency;  
    OPEN @CurrencyCursor;  
GO  
  
```  
  
 <span data-ttu-id="e37f5-153">Eseguire quindi un batch che consenta di dichiarare una variabile locale di cursore, eseguire la procedura per assegnare il cursore alla variabile locale e recuperare le righe dal cursore.</span><span class="sxs-lookup"><span data-stu-id="e37f5-153">Next, execute a batch that declares a local cursor variable, executes the procedure to assign the cursor to the local variable, and then fetches the rows from the cursor.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @MyCursor CURSOR;  
EXEC dbo.uspCurrencyCursor @CurrencyCursor = @MyCursor OUTPUT;  
WHILE (@@FETCH_STATUS = 0)  
BEGIN;  
     FETCH NEXT FROM @MyCursor;  
END;  
CLOSE @MyCursor;  
DEALLOCATE @MyCursor;  
GO  
  
```  
  
## <a name="returning-data-using-a-return-code"></a><span data-ttu-id="e37f5-154">Restituzione di dati tramite un codice restituito</span><span class="sxs-lookup"><span data-stu-id="e37f5-154">Returning Data Using a Return Code</span></span>  
 <span data-ttu-id="e37f5-155">Una procedura può restituire un valore intero, denominato codice restituito, per indicare lo stato di esecuzione di una procedura.</span><span class="sxs-lookup"><span data-stu-id="e37f5-155">A procedure can return an integer value called a return code to indicate the execution status of a procedure.</span></span> <span data-ttu-id="e37f5-156">Per specificare il codice restituito per una procedura, utilizzare l'istruzione RETURN.</span><span class="sxs-lookup"><span data-stu-id="e37f5-156">You specify the return code for a procedure using the RETURN statement.</span></span> <span data-ttu-id="e37f5-157">Come per i parametri OUTPUT, è necessario salvare il codice restituito in una variabile quando la procedura viene eseguita per utilizzare il valore del codice restituito nel programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="e37f5-157">As with OUTPUT parameters, you must save the return code in a variable when the procedure is executed in order to use the return code value in the calling program.</span></span> <span data-ttu-id="e37f5-158">La variabile `@result` di assegnazione del tipo di dati, ad esempio, `int` viene utilizzata per archiviare il codice restituito dalla procedura `my_proc` , ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e37f5-158">For example, the assignment variable `@result` of data type `int` is used to store the return code from the procedure `my_proc`, such as:</span></span>  
  
```  
DECLARE @result int;  
EXECUTE @result = my_proc;  
```  
  
 <span data-ttu-id="e37f5-159">I codici restituiti vengono in genere utilizzati nei blocchi per il controllo di flusso all'interno delle procedure per impostare il valore del codice restituito per ogni possibile situazione di errore.</span><span class="sxs-lookup"><span data-stu-id="e37f5-159">Return codes are commonly used in control-of-flow blocks within procedures to set the return code value for each possible error situation.</span></span> <span data-ttu-id="e37f5-160">È possibile usare la funzione @@ERROR dopo un'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] per rilevare se si è verificato un errore durante l'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="e37f5-160">You can use the @@ERROR function after a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to detect whether an error occurred during the execution of the statement.</span></span>  
  
### <a name="examples-of-return-codes"></a><span data-ttu-id="e37f5-161">Esempi di codici restituiti</span><span class="sxs-lookup"><span data-stu-id="e37f5-161">Examples of Return Codes</span></span>  
 <span data-ttu-id="e37f5-162">Nell'esempio seguente viene illustrata la procedura `usp_GetSalesYTD` con una modalità di gestione degli errori che consente di impostare valori speciali del codice restituito per errori diversi.</span><span class="sxs-lookup"><span data-stu-id="e37f5-162">The following example shows the `usp_GetSalesYTD` procedure with error handling that sets special return code values for various errors.</span></span> <span data-ttu-id="e37f5-163">Nella tabella seguente sono inclusi i valori interi assegnati dalla procedura a ogni possibile errore e viene indicato il significato di ogni valore.</span><span class="sxs-lookup"><span data-stu-id="e37f5-163">The following table shows the integer value that is assigned by the procedure to each possible error, and the corresponding meaning for each value.</span></span>  
  
|<span data-ttu-id="e37f5-164">Valore del codice restituito</span><span class="sxs-lookup"><span data-stu-id="e37f5-164">Return code value</span></span>|<span data-ttu-id="e37f5-165">Significato</span><span class="sxs-lookup"><span data-stu-id="e37f5-165">Meaning</span></span>|  
|-----------------------|-------------|  
|<span data-ttu-id="e37f5-166">0</span><span class="sxs-lookup"><span data-stu-id="e37f5-166">0</span></span>|<span data-ttu-id="e37f5-167">L'esecuzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e37f5-167">Successful execution.</span></span>|  
|<span data-ttu-id="e37f5-168">1</span><span class="sxs-lookup"><span data-stu-id="e37f5-168">1</span></span>|<span data-ttu-id="e37f5-169">Non è stato specificato un valore obbligatorio per un parametro.</span><span class="sxs-lookup"><span data-stu-id="e37f5-169">Required parameter value is not specified.</span></span>|  
|<span data-ttu-id="e37f5-170">2</span><span class="sxs-lookup"><span data-stu-id="e37f5-170">2</span></span>|<span data-ttu-id="e37f5-171">Il valore specificato per il parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="e37f5-171">Specified parameter value is not valid.</span></span>|  
|<span data-ttu-id="e37f5-172">3</span><span class="sxs-lookup"><span data-stu-id="e37f5-172">3</span></span>|<span data-ttu-id="e37f5-173">Si è verificato un errore durante il recupero del valore delle vendite.</span><span class="sxs-lookup"><span data-stu-id="e37f5-173">Error has occurred getting sales value.</span></span>|  
|<span data-ttu-id="e37f5-174">4</span><span class="sxs-lookup"><span data-stu-id="e37f5-174">4</span></span>|<span data-ttu-id="e37f5-175">È stato trovato un valore delle vendite NULL per il venditore.</span><span class="sxs-lookup"><span data-stu-id="e37f5-175">NULL sales value found for the salesperson.</span></span>|  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.usp_GetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.usp_GetSalesYTD;  
GO  
CREATE PROCEDURE Sales.usp_GetSalesYTD  
@SalesPerson nvarchar(50) = NULL,  -- NULL default value  
@SalesYTD money = NULL OUTPUT  
AS    
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
   BEGIN  
       PRINT 'ERROR: You must specify a last name for the sales person.'  
       RETURN(1)  
   END  
ELSE  
   BEGIN  
   -- Make sure the value is valid.  
   IF (SELECT COUNT(*) FROM HumanResources.vEmployee  
          WHERE LastName = @SalesPerson) = 0  
      RETURN(2)  
   END  
-- Get the sales for the specified name and   
-- assign it to the output parameter.  
SELECT @SalesYTD = SalesYTD   
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
-- Check for SQL Server errors.  
IF @@ERROR <> 0   
   BEGIN  
      RETURN(3)  
   END  
ELSE  
   BEGIN  
   -- Check to see if the ytd_sales value is NULL.  
     IF @SalesYTD IS NULL  
       RETURN(4)   
     ELSE  
      -- SUCCESS!!  
        RETURN(0)  
   END  
-- Run the stored procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the stored procedure with an input value.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTD  
EXECUTE Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
PRINT N'Year-to-date sales for this employee is ' +  
    CONVERT(varchar(10), @SalesYTDForSalesPerson);  
  
```  
  
 <span data-ttu-id="e37f5-176">Nell'esempio seguente viene creato un programma per la gestione dei codici restituiti dalla procedura `usp_GetSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="e37f5-176">The following example creates a program to handle the return codes that are returned from the `usp_GetSalesYTD` procedure.</span></span>  
  
```  
-- Declare the variables to receive the output value and return code   
-- of the procedure.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
  
-- Execute the procedure with a title_id value  
-- and save the output value and return code in variables.  
EXECUTE @ret_code = Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
--  Check the return codes.  
IF @ret_code = 0  
BEGIN  
   PRINT 'Procedure executed successfully'  
   -- Display the value returned by the procedure.  
   PRINT 'Year-to-date sales for this employee is ' + CONVERT(varchar(10),@SalesYTDForSalesPerson)  
END  
ELSE IF @ret_code = 1  
   PRINT 'ERROR: You must specify a last name for the sales person.'  
ELSE IF @ret_code = 2   
   PRINT 'EERROR: You must enter a valid last name for the sales person.'  
ELSE IF @ret_code = 3  
   PRINT 'ERROR: An error occurred getting sales value.'  
ELSE IF @ret_code = 4  
   PRINT 'ERROR: No sales recorded for this employee.'     
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="e37f5-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e37f5-177">See Also</span></span>  
 <span data-ttu-id="e37f5-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e37f5-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="e37f5-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e37f5-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span></span>  
 <span data-ttu-id="e37f5-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e37f5-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="e37f5-181">[Cursori](../cursors.md) </span><span class="sxs-lookup"><span data-stu-id="e37f5-181">[Cursors](../cursors.md) </span></span>  
 <span data-ttu-id="e37f5-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e37f5-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span></span>  
 [<span data-ttu-id="e37f5-183">@@ERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e37f5-183">@@ERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/error-transact-sql)  
  
  
