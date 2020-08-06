---
title: Manipolazione dei dati UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- CAST function
- data deletions [CLR integration]
- data insertions [CLR integration]
- CONVERT function
- data updates [CLR integration]
- comparing data
- updating data [CLR integration]
- removing data
- IsByteOrdered property
- variables [CLR integration]
- data manipulation [CLR integration]
- user-defined types [CLR integration], data manipulation
- deleting data
- UDTs [CLR integration], data manipulation
- invoking UDT methods
- inserting data
ms.assetid: 51b1a5f2-7591-4e11-bfe2-d88e0836403f
author: rothja
ms.author: jroth
ms.openlocfilehash: 75810a2ffd92130e45025f742d43ba7917d73992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714427"
---
# <a name="manipulating-udt-data"></a><span data-ttu-id="11d8a-102">Manipolazione dei dati UDT</span><span class="sxs-lookup"><span data-stu-id="11d8a-102">Manipulating UDT Data</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="11d8a-103">non fornisce una sintassi specifica per l'istruzione INSERT, UPDATE o DELETE quando si modificano i dati nelle colonne con tipo definito dall'utente (UDT).</span><span class="sxs-lookup"><span data-stu-id="11d8a-103">provides no specialized syntax for INSERT, UPDATE, or DELETE statements when modifying data in user-defined type (UDT) columns.</span></span> <span data-ttu-id="11d8a-104">Le funzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST o CONVERT vengono utilizzate per eseguire il cast dei tipi di dati nativi al tipo UDT.</span><span class="sxs-lookup"><span data-stu-id="11d8a-104">The [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST or CONVERT functions are used to cast native data types to the UDT type.</span></span>  
  
## <a name="inserting-data-in-a-udt-column"></a><span data-ttu-id="11d8a-105">Inserimento di dati in una colonna con tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="11d8a-105">Inserting Data in a UDT Column</span></span>  
 <span data-ttu-id="11d8a-106">Le istruzioni seguenti consentono [!INCLUDE[tsql](../../includes/tsql-md.md)] di inserire tre righe di dati di esempio nella tabella **Points** .</span><span class="sxs-lookup"><span data-stu-id="11d8a-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements insert three rows of sample data into the **Points** table.</span></span> <span data-ttu-id="11d8a-107">Il tipo di dati **Point** è costituito da valori integer X e Y esposti come proprietà del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="11d8a-107">The **Point** data type consists of X and Y integer values that are exposed as properties of the UDT.</span></span> <span data-ttu-id="11d8a-108">È necessario utilizzare la funzione CAST o CONVERT per eseguire il cast dei valori X e Y delimitati da virgole al tipo di **punto** .</span><span class="sxs-lookup"><span data-stu-id="11d8a-108">You must use either the CAST or CONVERT function to cast the comma-delimited X and Y values to the **Point** type.</span></span> <span data-ttu-id="11d8a-109">Le prime due istruzioni utilizzano la funzione CONVERT per convertire un valore stringa nel tipo **Point** e la terza istruzione utilizza la funzione cast:</span><span class="sxs-lookup"><span data-stu-id="11d8a-109">The first two statements use the CONVERT function to convert a string value to the **Point** type, and the third statement uses the CAST function:</span></span>  
  
```  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '3,4'));  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '1,5'));  
INSERT INTO dbo.Points (PointValue) VALUES (CAST ('1,99' AS Point));  
```  
  
## <a name="selecting-data"></a><span data-ttu-id="11d8a-110">Selezione dei dati</span><span class="sxs-lookup"><span data-stu-id="11d8a-110">Selecting Data</span></span>  
 <span data-ttu-id="11d8a-111">L'istruzione SELECT seguente consente di selezionare il valore binario del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="11d8a-111">The following SELECT statement selects the binary value of the UDT.</span></span>  
  
```  
SELECT ID, PointValue FROM dbo.Points  
```  
  
 <span data-ttu-id="11d8a-112">Per visualizzare l'output visualizzato in un formato leggibile, chiamare il `ToString` metodo del tipo definito dall'utente **Point** , che converte il valore nella relativa rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="11d8a-112">To see the output displayed in a readable format, call the `ToString` method of the **Point** UDT, which converts the value to its string representation.</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="11d8a-113">Vengono prodotti i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="11d8a-113">This produces the following results.</span></span>  
  
```  
IDPointValue  
----------  
13,4  
21,5  
31,99  
```  
  
 <span data-ttu-id="11d8a-114">Per ottenere gli stessi risultati, è anche possibile utilizzare le funzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST e CONVERT.</span><span class="sxs-lookup"><span data-stu-id="11d8a-114">You can also use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST and CONVERT functions to achieve the same results.</span></span>  
  
```  
SELECT ID, CAST(PointValue AS varchar)   
FROM dbo.Points;  
  
SELECT ID, CONVERT(varchar, PointValue)   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="11d8a-115">Il tipo definito dall'utente **Point** espone le coordinate X e Y come proprietà, che è quindi possibile selezionare singolarmente.</span><span class="sxs-lookup"><span data-stu-id="11d8a-115">The **Point** UDT exposes its X and Y coordinates as properties, which you can then select individually.</span></span> <span data-ttu-id="11d8a-116">L'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente consente di selezionare le coordinate X e Y separatamente:</span><span class="sxs-lookup"><span data-stu-id="11d8a-116">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects the X and Y coordinates separately:</span></span>  
  
```  
SELECT ID, PointValue.X AS xVal, PointValue.Y AS yVal   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="11d8a-117">Le proprietà X e Y restituiscono un valore integer visualizzato nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="11d8a-117">The X and Y properties return an integer value, which is displayed in the result set.</span></span>  
  
```  
IDxValyVal  
----------  
134  
215  
3199  
```  
  
## <a name="working-with-variables"></a><span data-ttu-id="11d8a-118">Gestione delle variabili</span><span class="sxs-lookup"><span data-stu-id="11d8a-118">Working with Variables</span></span>  
 <span data-ttu-id="11d8a-119">È possibile utilizzare le variabili specificando l'istruzione DECLARE per assegnare una variabile a un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="11d8a-119">You can work with variables using the DECLARE statement to assign a variable to a UDT type.</span></span> <span data-ttu-id="11d8a-120">Le istruzioni seguenti consentono di assegnare un valore utilizzando l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] SET nonché visualizzare i risultati chiamando il metodo `ToString` del tipo definito dall'utente sulla variabile:</span><span class="sxs-lookup"><span data-stu-id="11d8a-120">The following statements assign a value using the [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement and display the results by calling the UDT's `ToString` method on the variable:</span></span>  
  
```  
DECLARE @PointValue Point;  
SET @PointValue = (SELECT PointValue FROM dbo.Points  
    WHERE ID = 2);  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="11d8a-121">Nel set di risultati viene visualizzato il valore della variabile:</span><span class="sxs-lookup"><span data-stu-id="11d8a-121">The result set displays the variable value:</span></span>  
  
```  
PointValue  
----------  
-1,5  
```  
  
 <span data-ttu-id="11d8a-122">Le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti consentono di ottenere lo stesso risultato utilizzando SELECT anziché SET per l'assegnazione delle variabili:</span><span class="sxs-lookup"><span data-stu-id="11d8a-122">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements achieve the same result using SELECT rather than SET for the variable assignment:</span></span>  
  
```  
DECLARE @PointValue Point;  
SELECT @PointValue = PointValue FROM dbo.Points  
    WHERE ID = 2;  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="11d8a-123">La differenza tra l'utilizzo di SELECT e di SET per l'assegnazione delle variabili sta nel fatto che SELECT consente di assegnare più variabili in un'istruzione SELECT, mentre la sintassi di SET richiede che ogni assegnazione di variabile contenga la relativa istruzione SET.</span><span class="sxs-lookup"><span data-stu-id="11d8a-123">The difference between using SELECT and SET for variable assignment is that SELECT allows you to assign multiple variables in one SELECT statement, whereas the SET syntax requires each variable assignment to have its own SET statement.</span></span>  
  
## <a name="comparing-data"></a><span data-ttu-id="11d8a-124">Confronto dei dati</span><span class="sxs-lookup"><span data-stu-id="11d8a-124">Comparing Data</span></span>  
 <span data-ttu-id="11d8a-125">È possibile utilizzare gli operatori di confronto per confrontare i valori nel tipo definito dall'utente se la proprietà `IsByteOrdered` è stata impostata su `true` durante la definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="11d8a-125">You can use comparison operators to compare values in your UDT if you have set the `IsByteOrdered` property to `true` when defining the class.</span></span> <span data-ttu-id="11d8a-126">Per ulteriori informazioni, vedere [creazione di un tipo definito dall'utente](creating-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="11d8a-126">For more information, see [Creating a User-Defined Type](creating-user-defined-types.md).</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Points   
FROM dbo.Points  
WHERE PointValue > CONVERT(Point, '2,2');  
```  
  
 <span data-ttu-id="11d8a-127">È possibile confrontare i valori interni del tipo definito dall'utente indipendentemente dall'impostazione di `IsByteOrdered` se i valori stessi sono confrontabili.</span><span class="sxs-lookup"><span data-stu-id="11d8a-127">You can compare internal values of the UDT regardless of the `IsByteOrdered` setting if the values themselves are comparable.</span></span> <span data-ttu-id="11d8a-128">L'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente consente di selezionare le righe in cui X è maggiore di Y:</span><span class="sxs-lookup"><span data-stu-id="11d8a-128">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects rows where X is greater than Y:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points  
WHERE PointValue.X < PointValue.Y;  
```  
  
 <span data-ttu-id="11d8a-129">È anche possibile utilizzare gli operatori di confronto con le variabili, come mostrato in questa query che esegue la ricerca di un valore PointValue corrispondente.</span><span class="sxs-lookup"><span data-stu-id="11d8a-129">You can also use comparison operators with variables, as shown in this query that searches for a matching PointValue.</span></span>  
  
```  
DECLARE @ComparePoint Point;  
SET @ComparePoint = CONVERT(Point, '3,4');  
SELECT ID, PointValue.ToString() AS MatchingPoint   
FROM dbo.Points  
WHERE PointValue = @ComparePoint;  
```  
  
## <a name="invoking-udt-methods"></a><span data-ttu-id="11d8a-130">Chiamata dei metodi UDT</span><span class="sxs-lookup"><span data-stu-id="11d8a-130">Invoking UDT Methods</span></span>  
 <span data-ttu-id="11d8a-131">È anche possibile richiamare i metodi definiti nel tipo definito dall'utente in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11d8a-131">You can also invoke methods that are defined in your UDT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="11d8a-132">La classe **Point** contiene tre metodi, `Distance` , `DistanceFrom` e `DistanceFromXY` .</span><span class="sxs-lookup"><span data-stu-id="11d8a-132">The **Point** class contains three methods, `Distance`, `DistanceFrom`, and `DistanceFromXY`.</span></span> <span data-ttu-id="11d8a-133">Per gli elenchi di codice che definiscono questi tre metodi, vedere [codifica di tipi definiti dall'utente](creating-user-defined-types-coding.md).</span><span class="sxs-lookup"><span data-stu-id="11d8a-133">For the code listings defining these three methods, see [Coding User-Defined Types](creating-user-defined-types-coding.md).</span></span>  
  
 <span data-ttu-id="11d8a-134">Nell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente viene chiamato il metodo `PointValue.Distance`:</span><span class="sxs-lookup"><span data-stu-id="11d8a-134">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement calls the `PointValue.Distance` method:</span></span>  
  
```  
SELECT ID, PointValue.X AS [Point.X],   
    PointValue.Y AS [Point.Y],  
    PointValue.Distance() AS DistanceFromZero   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="11d8a-135">I risultati vengono visualizzati nella `Distance` colonna:</span><span class="sxs-lookup"><span data-stu-id="11d8a-135">The results are displayed in the `Distance` column:</span></span>  
  
```  
IDXYDistance  
------------------------  
1345  
2155.09901951359278  
319999.0050503762308  
```  
  
 <span data-ttu-id="11d8a-136">Il `DistanceFrom` metodo accetta un argomento del tipo di dati **Point** e visualizza la distanza dal punto specificato a PointValue:</span><span class="sxs-lookup"><span data-stu-id="11d8a-136">The `DistanceFrom` method takes an argument of **Point** data type, and displays the distance from the specified point to the PointValue:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Pnt,  
   PointValue.DistanceFrom(CONVERT(Point, '1,99')) AS DistanceFromPoint  
FROM dbo.Points;  
```  
  
 <span data-ttu-id="11d8a-137">Per ogni riga della tabella vengono visualizzati i risultati del metodo `DistanceFrom`:</span><span class="sxs-lookup"><span data-stu-id="11d8a-137">The results display the results of the `DistanceFrom` method for each row in the table:</span></span>  
  
```  
ID PntDistanceFromPoint  
---------------------  
13,495.0210502993942  
21,594  
31,990  
```  
  
 <span data-ttu-id="11d8a-138">Il metodo `DistanceFromXY` accetta i singoli punti come argomenti:</span><span class="sxs-lookup"><span data-stu-id="11d8a-138">The `DistanceFromXY` method takes the points individually as arguments:</span></span>  
  
```  
SELECT ID, PointValue.X as X, PointValue.Y as Y,   
PointValue.DistanceFromXY(1, 99) AS DistanceFromXY   
FROM dbo.Points  
```  
  
 <span data-ttu-id="11d8a-139">Il set di risultati è identico a quello prodotto dal metodo `DistanceFrom`.</span><span class="sxs-lookup"><span data-stu-id="11d8a-139">The result set is the same as the `DistanceFrom` method.</span></span>  
  
## <a name="updating-data-in-a-udt-column"></a><span data-ttu-id="11d8a-140">Aggiornamento dei dati in una colonna con tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="11d8a-140">Updating Data in a UDT Column</span></span>  
 <span data-ttu-id="11d8a-141">Per aggiornare i dati in una colonna con tipo definito dall'utente, utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE.</span><span class="sxs-lookup"><span data-stu-id="11d8a-141">To update data in a UDT column, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement.</span></span> <span data-ttu-id="11d8a-142">Per aggiornare lo stato dell'oggetto è anche possibile utilizzare un metodo del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="11d8a-142">You can also use a method of the UDT to update the state of the object.</span></span> <span data-ttu-id="11d8a-143">L'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente consente di aggiornare una singola riga nella tabella:</span><span class="sxs-lookup"><span data-stu-id="11d8a-143">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates a single row in the table:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = CAST('1,88' AS Point)  
WHERE ID = 3  
```  
  
 <span data-ttu-id="11d8a-144">È anche possibile aggiornare gli elementi UDT separatamente.</span><span class="sxs-lookup"><span data-stu-id="11d8a-144">You can also update UDT elements separately.</span></span> <span data-ttu-id="11d8a-145">L'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente consente di aggiornare solo la coordinata Y:</span><span class="sxs-lookup"><span data-stu-id="11d8a-145">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates only the Y coordinate:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="11d8a-146">Se il tipo definito dall'utente è stato definito con l'ordine dei byte impostato su `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] può valutare la colonna con tipo definito dall'utente in una clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="11d8a-146">If the UDT has been defined with byte ordering set to `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] can evaluate the UDT column in a WHERE clause.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = '4,5'  
WHERE PointValue = '3,4';  
```  
  
### <a name="updating-limitations"></a><span data-ttu-id="11d8a-147">Limitazioni relative all'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="11d8a-147">Updating Limitations</span></span>  
 <span data-ttu-id="11d8a-148">Non è possibile aggiornare più proprietà contemporaneamente utilizzando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11d8a-148">You cannot update multiple properties at once using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="11d8a-149">L'istruzione UPDATE seguente, ad esempio, ha esito negativo e restituisce un errore perché non è possibile utilizzare due volte lo stesso nome di colonna in un'istruzione UDATE.</span><span class="sxs-lookup"><span data-stu-id="11d8a-149">For example, the following UPDATE statement fails with an error because you cannot use the same column name twice in one UDATE statement.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.X = 5, PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="11d8a-150">Per aggiornare ogni punto singolarmente, è necessario creare un metodo mutatore nell'assembly del tipo definito dall'utente Point.</span><span class="sxs-lookup"><span data-stu-id="11d8a-150">To update each point individually, you would need to create a mutator method in the Point UDT assembly.</span></span> <span data-ttu-id="11d8a-151">È quindi possibile richiamare il metodo mutatore per aggiornare l'oggetto in un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="11d8a-151">You can then invoke the mutator method to update the object in a [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement, as in the following:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.SetXY(5, 99)  
WHERE ID = 3  
```  
  
## <a name="deleting-data-in-a-udt-column"></a><span data-ttu-id="11d8a-152">Eliminazione di dati in una colonna con tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="11d8a-152">Deleting Data in a UDT Column</span></span>  
 <span data-ttu-id="11d8a-153">Per eliminare dati in un tipo definito dall'utente, utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE.</span><span class="sxs-lookup"><span data-stu-id="11d8a-153">To delete data in a UDT, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span> <span data-ttu-id="11d8a-154">L'istruzione seguente consente di eliminare tutte le righe della tabella che corrispondono ai criteri specificati nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="11d8a-154">The following statement deletes all rows in the table that match the criteria specified in the WHERE clause.</span></span> <span data-ttu-id="11d8a-155">Se si omette la clausola WHERE in un'istruzione DELETE, verranno eliminate tutte le righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="11d8a-155">If you omit the WHERE clause in a DELETE statement, all rows in the table will be deleted.</span></span>  
  
```  
DELETE FROM dbo.Points  
WHERE PointValue = CAST('1,99' AS Point)  
```  
  
 <span data-ttu-id="11d8a-156">Utilizzare l'istruzione UPDATE se si desidera rimuovere i valori in una colonna con tipo definito dall'utente, senza tuttavia modificare i valori di altre righe.</span><span class="sxs-lookup"><span data-stu-id="11d8a-156">Use the UPDATE statement if you want to remove the values in a UDT column while leaving other row values intact.</span></span> <span data-ttu-id="11d8a-157">In questo esempio PointValue viene impostato su Null.</span><span class="sxs-lookup"><span data-stu-id="11d8a-157">This example sets the PointValue to null.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = null  
WHERE ID = 2  
```  
  
## <a name="see-also"></a><span data-ttu-id="11d8a-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11d8a-158">See Also</span></span>  
 [<span data-ttu-id="11d8a-159">Uso di tipi definiti dall'utente in SQL Server</span><span class="sxs-lookup"><span data-stu-id="11d8a-159">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
