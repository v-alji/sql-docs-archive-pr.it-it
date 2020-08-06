---
title: Specificare i parametri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], stored procedures
- stored procedures [SQL Server], parameters
- output parameters [SQL Server]
- input parameters [SQL Server]
ms.assetid: 902314fe-5f9c-4d0d-a0b7-27e67c9c70ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: d93a04281839c4db26cbab16ac166af3cdb7c9a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638362"
---
# <a name="specify-parameters"></a><span data-ttu-id="0f6ef-102">Specificare i parametri</span><span class="sxs-lookup"><span data-stu-id="0f6ef-102">Specify Parameters</span></span>
  <span data-ttu-id="0f6ef-103">Se si specificano parametri di procedura, i programmi chiamanti sono in grado di passare i valori nel corpo della procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-103">By specifying procedure parameters, calling programs are able to pass values into the body of the procedure.</span></span> <span data-ttu-id="0f6ef-104">Tali valori possono essere utilizzati per diversi scopi durante l'esecuzione della procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-104">Those values can be used for a variety of purposes during procedure execution.</span></span> <span data-ttu-id="0f6ef-105">Inoltre, i parametri di procedura possono restituire valori al programma chiamante se il parametro è contrassegnato come parametro OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-105">Procedure parameters can also return values to the calling program if the parameter is marked as an OUTPUT parameter.</span></span>  
  
 <span data-ttu-id="0f6ef-106">Una procedura può disporre al massimo di 2100 parametri, a ciascuno dei quali vengono assegnati un nome, un tipo di dati e una direzione.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-106">A procedure can have a maximum of 2100 parameters; each assigned a name, data type, and direction.</span></span> <span data-ttu-id="0f6ef-107">Facoltativamente, ai parametri possono essere assegnati i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-107">Optionally, parameters can be assigned default values.</span></span>  
  
 <span data-ttu-id="0f6ef-108">Nella sezione seguente vengono fornite informazioni sul passaggio dei valori nei parametri e sulla modalità di utilizzo di ognuno degli attributi di parametro durante una chiamata alla procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-108">The following section provides information about passing values into parameters and about how each of the parameter attributes is used during a procedure call.</span></span>  
  
## <a name="passing-values-into-parameters"></a><span data-ttu-id="0f6ef-109">Passaggio dei valori nei parametri</span><span class="sxs-lookup"><span data-stu-id="0f6ef-109">Passing Values into Parameters</span></span>  
 <span data-ttu-id="0f6ef-110">I valori dei parametri forniti con una chiamata alla procedura devono essere costanti o una variabile. Non è possibile utilizzare un nome di funzione come valore di parametro.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-110">The parameter values supplied with a procedure call must be constants or a variable; a function name cannot be used as a parameter value.</span></span> <span data-ttu-id="0f6ef-111">Le variabili possono essere definite dall'utente oppure di sistema, ad esempio \@\@spid.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-111">Variables can be user-defined or system variables such as \@\@spid.</span></span>  
  
 <span data-ttu-id="0f6ef-112">Negli esempi seguenti viene illustrato il passaggio dei valori dei parametri alla procedura `uspGetWhereUsedProductID`.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-112">The following examples demonstrate passing parameter values to the procedure `uspGetWhereUsedProductID`.</span></span> <span data-ttu-id="0f6ef-113">Viene illustrato come passare i parametri come costanti e variabili e utilizzare una variabile per passare il valore di una funzione.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-113">They illustrate how to pass parameters as constants and variables and also how to use a variable to pass the value of a function.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Passing values as constants.  
EXEC dbo.uspGetWhereUsedProductID 819, '20050225';  
GO  
-- Passing values as variables.  
DECLARE @ProductID int, @CheckDate datetime;  
SET @ProductID = 819;  
SET @CheckDate = '20050225';  
EXEC dbo.uspGetWhereUsedProductID @ProductID, @CheckDate;  
GO  
-- Try to use a function as a parameter value.  
-- This produces an error message.  
EXEC dbo.uspGetWhereUsedProductID 819, GETDATE();  
GO  
-- Passing the function value as a variable.  
DECLARE @CheckDate datetime;  
SET @CheckDate = GETDATE();  
EXEC dbo.uspGetWhereUsedProductID 819, @CheckDate;  
GO  
```  
  
## <a name="specifying-parameter-names"></a><span data-ttu-id="0f6ef-114">Specifica dei nomi di parametri</span><span class="sxs-lookup"><span data-stu-id="0f6ef-114">Specifying Parameter Names</span></span>  
 <span data-ttu-id="0f6ef-115">Quando si crea una procedura e si dichiara un nome di parametro, tale nome deve iniziare con un singolo carattere \@ e deve essere univoco nell'ambito della procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-115">When creating a procedure and declaring a parameter name, the parameter name must begin with a single \@ character and must be unique in the scope of the procedure.</span></span>  
  
 <span data-ttu-id="0f6ef-116">La denominazione dei parametri e l'assegnazione dei valori appropriati in modo esplicito a ogni parametro in una chiamata alla procedura consentono ai parametri di essere forniti in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-116">Explicitly naming the parameters and assigning the appropriate values to each parameter in a procedure call allows the parameters to be supplied in any order.</span></span> <span data-ttu-id="0f6ef-117">Se ad esempio per la procedura **my_proc** sono previsti tre parametri denominati **\@first**, **\@second** e **\@third**, i valori passati alla procedura possono essere assegnati ai nomi dei parametri, ad esempio: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span><span class="sxs-lookup"><span data-stu-id="0f6ef-117">For example, if the procedure **my_proc** expects three parameters named **\@first**, **\@second**, and **\@third**, the values passed to the procedure can be assigned to the parameter names, such as: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f6ef-118">Se un valore del parametro viene specificato nel formato **\@parametro =** _valore_, tutti i parametri successivi devono essere specificati in questo modo.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-118">If one parameter value is supplied in the form **\@parameter =**_value_, all subsequent parameters must be supplied in this manner.</span></span> <span data-ttu-id="0f6ef-119">Se i valori dei parametri non vengono passati nel formato **\@parametro =** _valore_, devono essere specificati nello stesso ordine, da sinistra a destra, dei parametri elencati nell'istruzione CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-119">If the parameter values are not passed in the form **\@parameter =**_value_, the values must be supplied in the identical order (left to right) as the parameters are listed in the CREATE PROCEDURE statement.</span></span>  
> 
> [!WARNING]
>  <span data-ttu-id="0f6ef-120">Qualsiasi parametro passato nel formato **\@parametro =** _valore_ contenente un errore di ortografia causerà la generazione di un errore in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e impedirà l'esecuzione della procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-120">Any parameter passed in the form **\@parameter =**_value_ with the parameter misspelled, will cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate an error and prevent procedure execution.</span></span>  
  
## <a name="specifying-parameter-data-types"></a><span data-ttu-id="0f6ef-121">Specifica dei tipi di dati per i parametri</span><span class="sxs-lookup"><span data-stu-id="0f6ef-121">Specifying Parameter Data Types</span></span>  
 <span data-ttu-id="0f6ef-122">I parametri devono essere definiti con un tipo di dati quando vengono dichiarati in un'istruzione CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-122">Parameters must be defined with a data type when they are declared in a CREATE PROCEDURE statement.</span></span> <span data-ttu-id="0f6ef-123">Il tipo di dati di un parametro consente di determinare il tipo e l'intervallo di valori accettati per il parametro quando viene chiamata la procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-123">The data type of a parameter determines the type and range of values that are accepted for the parameter when the procedure is called.</span></span> <span data-ttu-id="0f6ef-124">Se, ad esempio, si definisce un parametro con un tipo di dati `tinyint`, verranno accettati soltanto i valori numerici nell'intervallo compreso tra 0 e 255 quando passati in tale parametro.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-124">For example, if you define a parameter with a `tinyint` data type, only numeric values ranging from 0 to 255 are accepted when passed into that parameter.</span></span> <span data-ttu-id="0f6ef-125">Se una procedura viene eseguita con un valore incompatibile con il tipo di dati, verrà restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-125">An error is returned if a procedure is executed with a value incompatible with the data type.</span></span>  
  
## <a name="specifying-parameter-default-values"></a><span data-ttu-id="0f6ef-126">Specifica dei valori predefiniti per i parametri</span><span class="sxs-lookup"><span data-stu-id="0f6ef-126">Specifying Parameter Default Values</span></span>  
 <span data-ttu-id="0f6ef-127">Un parametro è considerato facoltativo se dispone di un valore predefinito specificato al momento della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-127">A parameter is considered optional if the parameter has a default value specified when it is declared.</span></span> <span data-ttu-id="0f6ef-128">Non è necessario fornire un valore per un parametro facoltativo in una chiamata alla procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-128">It is not necessary to provide a value for an optional parameter in a procedure call.</span></span>  
  
 <span data-ttu-id="0f6ef-129">Il valore predefinito di un parametro viene utilizzato quando:</span><span class="sxs-lookup"><span data-stu-id="0f6ef-129">The default value of a parameter is used when:</span></span>  
  
-   <span data-ttu-id="0f6ef-130">Non viene specificato alcun valore nella chiamata alla procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-130">No value for the parameter is specified in the procedure call.</span></span>  
  
-   <span data-ttu-id="0f6ef-131">Viene specificata la parola chiave DEFAULT come valore nella chiamata alla procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-131">The DEFAULT keyword is specified as the value in the procedure call.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f6ef-132">Se il valore predefinito è una stringa di caratteri contenente spazi vuoti o punteggiatura o se inizia con un numero, ad esempio 6xxx, è necessario racchiuderlo tra virgolette singole.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-132">If the default value is a character string that contains embedded blanks or punctuation, or if it starts with a number (for example, 6xxx), it must be enclosed in single, straight quotation marks.</span></span>  
  
 <span data-ttu-id="0f6ef-133">Se per il parametro non può essere specificato in modo appropriato alcun valore come predefinito, specificare come tale NULL.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-133">If no value can be specified appropriately as a default for the parameter, specify NULL as the default.</span></span> <span data-ttu-id="0f6ef-134">È consigliabile la restituzione di un messaggio personalizzato da parte della procedura se quest'ultima viene eseguita senza un valore per il parametro.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-134">It is a good idea to have the procedure return a customized message if the procedure is executed without a value for the parameter.</span></span>  
  
 <span data-ttu-id="0f6ef-135">Nell'esempio seguente viene creata la procedura `usp_GetSalesYTD` con un parametro di input, `@SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-135">The following example creates the `usp_GetSalesYTD` procedure with one input parameter, `@SalesPerson`.</span></span> <span data-ttu-id="0f6ef-136">NULL viene assegnato come valore predefinito per il parametro e utilizzato nelle istruzioni di gestione degli errori per restituire un messaggio di errore personalizzato nei casi in cui la procedura venga eseguita senza un valore per il parametro `@SalesPerson` .</span><span class="sxs-lookup"><span data-stu-id="0f6ef-136">NULL is assigned as the default value for the parameter and is used in error handling statements to return a custom error message for cases when the procedure is executed without a value for the `@SalesPerson` parameter.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetSalesYTD  
@SalesPerson nvarchar(50) = NULL  -- NULL default value  
AS   
    SET NOCOUNT ON;   
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
BEGIN  
   PRINT 'ERROR: You must specify the last name of the sales person.'  
   RETURN  
END  
-- Get the sales for the specified sales person and   
-- assign it to the output parameter.  
SELECT SalesYTD  
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="0f6ef-137">Di seguito è riportato un esempio di esecuzione della procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-137">The following example executes the procedure.</span></span> <span data-ttu-id="0f6ef-138">Tramite la prima istruzione la procedura viene eseguita senza specificare un valore di input.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-138">The first statement executes the procedure without specifying an input value.</span></span> <span data-ttu-id="0f6ef-139">Tale operazione determina la restituzione del messaggio di errore personalizzato da parte delle istruzioni di gestione degli errori nella procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-139">This causes the error handling statements in the procedure to return the custom error message.</span></span> <span data-ttu-id="0f6ef-140">Tramite la seconda istruzione viene fornito un valore di input e viene restituito il set di risultati previsto.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-140">The second statement supplies an input value and returns the expected result set.</span></span>  
  
```  
-- Run the procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the procedure with an input value.  
EXEC Sales.usp_GetSalesYTD N'Blythe';  
GO  
```  
  
 <span data-ttu-id="0f6ef-141">Sebbene sia possibile omettere i parametri per cui sono stati forniti valori predefiniti, è possibile troncare soltanto l'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-141">Although parameters for which defaults have been supplied can be omitted, the list of parameters can only be truncated.</span></span> <span data-ttu-id="0f6ef-142">Ad esempio, se una procedura dispone di cinque parametri, è possibile omettere sia il quarto sia il quinto parametro.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-142">For example, if a procedure has five parameters, both the fourth and the fifth parameters can be omitted.</span></span> <span data-ttu-id="0f6ef-143">Non è tuttavia possibile ignorare il quarto parametro finché è incluso il quinto, a meno che i parametri non vengano specificati nel formato **\@parametro =** _valore_.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-143">However the fourth parameter cannot be skipped as long as the fifth parameter is included, unless the parameters are supplied in the form **\@parameter =**_value_.</span></span>  
  
## <a name="specifying-parameter-direction"></a><span data-ttu-id="0f6ef-144">Specifica della direzione di un parametro</span><span class="sxs-lookup"><span data-stu-id="0f6ef-144">Specifying Parameter Direction</span></span>  
 <span data-ttu-id="0f6ef-145">La direzione di un parametro può essere input, cioè un valore viene passato nel corpo della procedura, o output, vale a dire che tramite la procedura viene restituito un valore al programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-145">The direction of a parameter is either input, a value is passed into the body of the procedure, or output, the procedure returns a value to the calling program.</span></span> <span data-ttu-id="0f6ef-146">Il parametro di input è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-146">The default is an input parameter.</span></span>  
  
 <span data-ttu-id="0f6ef-147">Per specificare un parametro di output, è necessario includere la parola chiave OUTPUT nella definizione del parametro nell'istruzione CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-147">To specify an output parameter, the OUTPUT keyword must be specified in the definition of the parameter in the CREATE PROCEDURE statement.</span></span> <span data-ttu-id="0f6ef-148">Tramite la procedura, al programma chiamante viene restituito il valore corrente del parametro di output quando la procedura è disponibile.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-148">The procedure returns the current value of the output parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="0f6ef-149">Nel programma chiamante deve inoltre essere utilizzata la parola chiave OUTPUT quando si esegue la procedura per salvare il valore del parametro in una variabile utilizzabile nel programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-149">The calling program must also use the OUTPUT keyword when executing the procedure to save the parameter's value in a variable that can be used in the calling program.</span></span>  
  
 <span data-ttu-id="0f6ef-150">Nell'esempio seguente viene creata la procedura `Production.usp`_`GetList` , mediante la quale viene restituito un elenco di prodotti i cui prezzi non superano un determinato importo.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-150">The following example creates the `Production.usp`_`GetList` procedure, which returns a list of products that have prices that do not exceed a specified amount.</span></span> <span data-ttu-id="0f6ef-151">Nell'esempio viene illustrato l'utilizzo di più istruzioni SELECT e di più parametri OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-151">The example shows using multiple SELECT statements and multiple OUTPUT parameters.</span></span> <span data-ttu-id="0f6ef-152">I parametri OUTPUT consentono a una procedura esterna, a un batch o a più istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] di accedere a un valore impostato durante l'esecuzione della procedura.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-152">OUTPUT parameters allow an external procedure, a batch, or more than one [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to access a value set during the procedure execution.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'Production.uspGetList', 'P' ) IS NOT NULL   
    DROP PROCEDURE Production.uspGetList;  
GO  
CREATE PROCEDURE Production.uspGetList @Product varchar(40)   
    , @MaxPrice money   
    , @ComparePrice money OUTPUT  
    , @ListPrice money OUT  
AS  
    SET NOCOUNT ON;  
    SELECT p.[Name] AS Product, p.ListPrice AS 'List Price'  
    FROM Production.Product AS p  
    JOIN Production.ProductSubcategory AS s   
      ON p.ProductSubcategoryID = s.ProductSubcategoryID  
    WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice;  
-- Populate the output variable @ListPprice.  
SET @ListPrice = (SELECT MAX(p.ListPrice)  
        FROM Production.Product AS p  
        JOIN  Production.ProductSubcategory AS s   
          ON p.ProductSubcategoryID = s.ProductSubcategoryID  
        WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice);  
-- Populate the output variable @compareprice.  
SET @ComparePrice = @MaxPrice;  
GO  
  
```  
  
 <span data-ttu-id="0f6ef-153">Eseguire `usp_GetList` per restituire un elenco dei prodotti di [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] (biciclette) con un prezzo inferiore a 700 dollari.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-153">Execute `usp_GetList` to return a list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] products (Bikes) that cost less than $700.</span></span> <span data-ttu-id="0f6ef-154">I parametri OUTPUT **\@cost** e **\@compareprices** vengono usati con elementi del linguaggio per il controllo di flusso per restituire un messaggio nella finestra **Messaggi**.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-154">The OUTPUT parameters **\@cost** and **\@compareprices** are used with control-of-flow language to return a message in the **Messages** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f6ef-155">La variabile OUTPUT deve essere definita durante la creazione della procedura e durante l'utilizzo della variabile.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-155">The OUTPUT variable must be defined during the procedure creation and also during the use of the variable.</span></span> <span data-ttu-id="0f6ef-156">Il nome di parametro e quello della variabile non devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-156">The parameter name and variable name do not have to match.</span></span> <span data-ttu-id="0f6ef-157">Il tipo di dati e la posizione del parametro devono tuttavia corrispondere, a meno che non si usi **\@listprice=** _variabile_.</span><span class="sxs-lookup"><span data-stu-id="0f6ef-157">However, the data type and parameter positioning must match (unless **\@listprice=** _variable_ is used).</span></span>  
  
```  
DECLARE @ComparePrice money, @Cost money ;  
EXECUTE Production.uspGetList '%Bikes%', 700,   
    @ComparePrice OUT,   
    @Cost OUTPUT  
IF @Cost <= @ComparePrice   
BEGIN  
    PRINT 'These products can be purchased for less than   
    $'+RTRIM(CAST(@ComparePrice AS varchar(20)))+'.'  
END  
ELSE  
    PRINT 'The prices for all products in this category exceed   
    $'+ RTRIM(CAST(@ComparePrice AS varchar(20)))+'.';  
  
```  
  
 <span data-ttu-id="0f6ef-158">Di seguito è riportato il set di risultati parziale:</span><span class="sxs-lookup"><span data-stu-id="0f6ef-158">Here is the partial result set:</span></span>  
  
```  
Product                                            List Price  
-------------------------------------------------- ------------------  
Road-750 Black, 58                                 539.99  
Mountain-500 Silver, 40                            564.99  
Mountain-500 Silver, 42                            564.99  
...  
Road-750 Black, 48                                 539.99  
Road-750 Black, 52                                 539.99  
  
(14 row(s) affected)  
  
These items can be purchased for less than $700.00.  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f6ef-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f6ef-159">See Also</span></span>  
 [<span data-ttu-id="0f6ef-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f6ef-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
