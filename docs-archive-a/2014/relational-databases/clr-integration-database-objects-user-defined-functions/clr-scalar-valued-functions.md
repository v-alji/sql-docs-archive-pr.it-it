---
title: Funzioni a valori scalari CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- SVF
- scalar-valued functions
ms.assetid: 20dcf802-c27d-4722-9cd3-206b1e77bee0
author: rothja
ms.author: jroth
ms.openlocfilehash: be8f9616fb285d6a68d6734924874ded06fb3bd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714431"
---
# <a name="clr-scalar-valued-functions"></a><span data-ttu-id="2abd8-102">Funzioni a valori scalari CLR</span><span class="sxs-lookup"><span data-stu-id="2abd8-102">CLR Scalar-Valued Functions</span></span>
  <span data-ttu-id="2abd8-103">Una funzione a valori scalari restituisce un valore singolo, come una stringa un Integer o un valore di bit. È possibile creare funzioni a valori scalari definite dall'utente nel codice gestito utilizzando qualsiasi linguaggio di programmazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2abd8-103">A scalar-valued function (SVF) returns a single value, such as a string, integer, or bit value.You can create scalar-valued user-defined functions in managed code using any .NET Framework programming language.</span></span> <span data-ttu-id="2abd8-104">Queste funzioni sono accessibili a [!INCLUDE[tsql](../../includes/tsql-md.md)] o ad altro codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2abd8-104">These functions are accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span> <span data-ttu-id="2abd8-105">Per informazioni sui vantaggi dell'integrazione con CLR e sulla scelta tra codice gestito e [!INCLUDE[tsql](../../includes/tsql-md.md)] , vedere [Cenni preliminari sull'integrazione con CLR](../clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2abd8-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-scalar-valued-functions"></a><span data-ttu-id="2abd8-106">Requisiti per le funzioni a valori scalari CLR</span><span class="sxs-lookup"><span data-stu-id="2abd8-106">Requirements for CLR Scalar-Valued Functions</span></span>  
 <span data-ttu-id="2abd8-107">Le funzioni a valori scalari di .NET Framework vengono implementate come metodi in una classe di un assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2abd8-107">.NET Framework SVFs are implemented as methods on a class in a .NET Framework assembly.</span></span> <span data-ttu-id="2abd8-108">I parametri di input e il tipo restituiti da un SVF possono essere uno qualsiasi dei tipi di dati scalari supportati da, ad eccezione di,,,,, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `varchar` `char` `rowversion` `text` `ntext` `image` , `timestamp` , `table` o `cursor` .</span><span class="sxs-lookup"><span data-stu-id="2abd8-108">The input parameters and the type returned from a SVF can be any of the scalar data types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except `varchar`, `char`, `rowversion`, `text`, `ntext`, `image`, `timestamp`, `table`, or `cursor`.</span></span> <span data-ttu-id="2abd8-109">Le funzioni a valori scalari devono assicurare una corrispondenza tra il tipo di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il tipo dati restituito del metodo di implementazione.</span><span class="sxs-lookup"><span data-stu-id="2abd8-109">SVFs must ensure a match between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type and the return data type of the implementation method.</span></span> <span data-ttu-id="2abd8-110">Per ulteriori informazioni sulle conversioni di tipi, vedere [mapping dei dati dei parametri CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="2abd8-110">For more information about type conversions, see [Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
 <span data-ttu-id="2abd8-111">In caso di implementazione di una funzione a valore scalare di .NET Framework in un linguaggio di .NET Framework, è possibile specificare l'attributo personalizzato `SqlFunction` per includere informazioni aggiuntive sulla funzione.</span><span class="sxs-lookup"><span data-stu-id="2abd8-111">When implementing a .NET Framework SVF in a .NET Framework language, the `SqlFunction` custom attribute can be specified to include additional information about the function.</span></span> <span data-ttu-id="2abd8-112">L'attributo `SqlFunction` indica se la funzione accede ai dati o li modifica, se è deterministica e se comporta operazioni a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="2abd8-112">The `SqlFunction` attribute indicates whether or not the function accesses or modifies data, if it is deterministic, and if the function involves floating point operations.</span></span>  
  
 <span data-ttu-id="2abd8-113">Le funzioni definite dall'utente a valori scalari possono essere deterministiche o non deterministiche.</span><span class="sxs-lookup"><span data-stu-id="2abd8-113">Scalar-valued user-defined functions may be deterministic or non-deterministic.</span></span> <span data-ttu-id="2abd8-114">Una funzione deterministica restituisce sempre lo stesso risultato quando viene chiamata con un set specifico di parametri di input.</span><span class="sxs-lookup"><span data-stu-id="2abd8-114">A deterministic function always returns the same result when it is called with a specific set of input parameters.</span></span> <span data-ttu-id="2abd8-115">Una funzione non deterministica può restituire risultati diversi quando viene chiamata con un set specifico di parametri di input.</span><span class="sxs-lookup"><span data-stu-id="2abd8-115">A non-deterministic function may return different results when it is called with a specific set of input parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2abd8-116">Non contrassegnare una funzione come deterministica se non produce sempre gli stessi valori di output, dati gli stessi valori di input e lo stesso stato del database.</span><span class="sxs-lookup"><span data-stu-id="2abd8-116">Do not mark a function as deterministic if the function does not always produces the same output values, given the same input values and the same database state.</span></span> <span data-ttu-id="2abd8-117">Una funzione non propriamente deterministica ma contrassegnata come tale può causare danni a viste indicizzate e colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="2abd8-117">Marking a function as deterministic, when the function isn't truly deterministic can result in corrupted indexed views and computed columns.</span></span> <span data-ttu-id="2abd8-118">Per contrassegnare una funzione come deterministica, impostare la proprietà `IsDeterministic` su true.</span><span class="sxs-lookup"><span data-stu-id="2abd8-118">You mark a function as deterministic by setting the `IsDeterministic` property to true.</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="2abd8-119">Parametri valutati a livello di tabella</span><span class="sxs-lookup"><span data-stu-id="2abd8-119">Table-Valued Parameters</span></span>  
 <span data-ttu-id="2abd8-120">I parametri con valori di tabella, ovvero tipi di tabella definiti dall'utente passati in una procedura o in una funzione, consentono di passare in modo efficiente più righe di dati al server.</span><span class="sxs-lookup"><span data-stu-id="2abd8-120">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="2abd8-121">Pur essendo caratterizzati da funzionalità simili alle matrici di parametri, i parametri con valori di tabella offrono più flessibilità e una maggiore integrazione con [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2abd8-121">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2abd8-122">Consentono inoltre di ottenere prestazioni potenzialmente migliori.</span><span class="sxs-lookup"><span data-stu-id="2abd8-122">They also provide the potential for better performance.</span></span> <span data-ttu-id="2abd8-123">I parametri con valori di tabella consentono inoltre di ridurre il numero di round trip al server.</span><span class="sxs-lookup"><span data-stu-id="2abd8-123">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="2abd8-124">Anziché inviare più richieste al server, ad esempio con un elenco di parametri scalari, è possibile inviare i dati al server sotto forma di parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="2abd8-124">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="2abd8-125">Un tipo di tabella definito dall'utente non può essere passato come parametro con valori di tabella a una stored procedure gestita o a una funzione in esecuzione nel processo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], né può essere restituito dalle stesse.</span><span class="sxs-lookup"><span data-stu-id="2abd8-125">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="2abd8-126">Per altre informazioni su TVP, vedere [usare i parametri con valori di tabella &#40;motore di database&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="2abd8-126">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="example-of-a-clr-scalar-valued-function"></a><span data-ttu-id="2abd8-127">Esempio di una funzione a valori scalari CLR</span><span class="sxs-lookup"><span data-stu-id="2abd8-127">Example of a CLR Scalar-Valued Function</span></span>  
 <span data-ttu-id="2abd8-128">Di seguito è riportata una semplice funzione a valori scalari che accede ai dati e restituisce un valore integer:</span><span class="sxs-lookup"><span data-stu-id="2abd8-128">Here is a simple SVF that accesses data and returns an integer value:</span></span>  
  
```csharp  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public class T  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static int ReturnOrderCount()  
    {  
        using (SqlConnection conn   
            = new SqlConnection("context connection=true"))  
        {  
            conn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
            return (int)cmd.ExecuteScalar();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public Class T  
    <SqlFunction(DataAccess:=DataAccessKind.Read)> _  
    Public Shared Function ReturnOrderCount() As Integer  
        Using conn As New SqlConnection("context connection=true")  
            conn.Open()  
            Dim cmd As New SqlCommand("SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
            Return CType(cmd.ExecuteScalar(), Integer)  
        End Using  
    End Function  
End Class  
```  
  
 <span data-ttu-id="2abd8-129">La prima riga di codice fa riferimento a `Microsoft.SqlServer.Server` per accedere ad attributi e a `System.Data.SqlClient` per accedere allo spazio dei nomi ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2abd8-129">The first line of code references `Microsoft.SqlServer.Server` to access attributes and `System.Data.SqlClient` to access the ADO.NET namespace.</span></span> <span data-ttu-id="2abd8-130">Questo spazio dei nomi contiene `SqlClient`, il provider di dati .NET Framework per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2abd8-130">(This namespace contains `SqlClient`, the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="2abd8-131">Dopodiché, la funzione riceve l'attributo personalizzato `SqlFunction`, presente nello spazio dei nomi `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="2abd8-131">Next, the function receives the `SqlFunction` custom attribute, which is found in the `Microsoft.SqlServer.Server` namespace.</span></span> <span data-ttu-id="2abd8-132">L'attributo personalizzato indica se la funzione definita dall'utente utilizza il provider in-process per leggere dati nel server.</span><span class="sxs-lookup"><span data-stu-id="2abd8-132">The custom attribute indicates whether or not the user-defined function (UDF) uses the in-process provider to read data in the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2abd8-133">non consente alle Funzioni definite dall'utente di aggiornare, inserire o eliminare dati.</span><span class="sxs-lookup"><span data-stu-id="2abd8-133">does not allow UDFs to update, insert, or delete data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2abd8-134">possono ottimizzare l'esecuzione di una UDF che non utilizza il provider in-process.</span><span class="sxs-lookup"><span data-stu-id="2abd8-134">can optimize execution of a UDF that does not use the in-process provider.</span></span> <span data-ttu-id="2abd8-135">Questa possibilità viene indicata impostando `DataAccessKind` su `DataAccessKind.None`.</span><span class="sxs-lookup"><span data-stu-id="2abd8-135">This is indicated by setting `DataAccessKind` to `DataAccessKind.None`.</span></span> <span data-ttu-id="2abd8-136">Sulla riga successiva il metodo di destinazione è un metodo statico pubblico (condiviso in Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="2abd8-136">On the next line, the target method is a public static (shared in Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="2abd8-137">La classe `SqlContext`, che si trova nello spazio dei nomi `Microsoft.SqlServer.Server`, può quindi accedere a un oggetto `SqlCommand` con una connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] già configurata.</span><span class="sxs-lookup"><span data-stu-id="2abd8-137">The `SqlContext` class, located in the `Microsoft.SqlServer.Server` namespace, can then access a `SqlCommand` object with a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is already set up.</span></span> <span data-ttu-id="2abd8-138">Sebbene non venga utilizzato qui, il contesto della transazione corrente è disponibile anche tramite l'API (Application Programming Interface) di `System.Transactions`.</span><span class="sxs-lookup"><span data-stu-id="2abd8-138">Although not used here, the current transaction context is also available through the `System.Transactions` application programming interface (API).</span></span>  
  
 <span data-ttu-id="2abd8-139">La maggior parte delle righe di codice nel corpo della funzione è già nota agli sviluppatori che hanno scritto applicazioni client che utilizzano i tipi presenti nello spazio dei nomi `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="2abd8-139">Most of the lines of code in the function body should look familiar to developers who have written client applications that use the types found in the `System.Data.SqlClient` namespace.</span></span>  
  
 <span data-ttu-id="2abd8-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="2abd8-140">[C#]</span></span>  
  
```  
using(SqlConnection conn = new SqlConnection("context connection=true"))   
{  
   conn.Open();  
   SqlCommand cmd = new SqlCommand(  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
   return (int) cmd.ExecuteScalar();  
}    
```  
  
 <span data-ttu-id="2abd8-141">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="2abd8-141">[Visual Basic]</span></span>  
  
```  
Using conn As New SqlConnection("context connection=true")  
   conn.Open()  
   Dim cmd As New SqlCommand( _  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
   Return CType(cmd.ExecuteScalar(), Integer)  
End Using  
```  
  
 <span data-ttu-id="2abd8-142">Il testo del comando appropriato viene specificato inizializzando l'oggetto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="2abd8-142">The appropriate command text is specified by initializing the `SqlCommand` object.</span></span> <span data-ttu-id="2abd8-143">Nell'esempio precedente viene contato il numero di righe nella tabella `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="2abd8-143">The previous example counts the number of rows in table `SalesOrderHeader`.</span></span> <span data-ttu-id="2abd8-144">Dopodiché, viene chiamato il metodo `ExecuteScalar` dell'oggetto `cmd`.</span><span class="sxs-lookup"><span data-stu-id="2abd8-144">Next, the `ExecuteScalar` method of the `cmd` object is called.</span></span> <span data-ttu-id="2abd8-145">Viene quindi restituito un valore di tipo `int` basato sulla query.</span><span class="sxs-lookup"><span data-stu-id="2abd8-145">This returns a value of type `int` based on the query.</span></span> <span data-ttu-id="2abd8-146">Infine, il numero di ordini viene restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="2abd8-146">Finally, the order count is returned to the caller.</span></span>  
  
 <span data-ttu-id="2abd8-147">Se questo codice viene salvato in un file chiamato FirstUdf.cs, può essere compilato come assembly nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="2abd8-147">If this code is saved in a file called FirstUdf.cs, it could be compiled into as assembly as follows:</span></span>  
  
 <span data-ttu-id="2abd8-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="2abd8-148">[C#]</span></span>  
  
```  
csc.exe /t:library /out:FirstUdf.dll FirstUdf.cs   
```  
  
 <span data-ttu-id="2abd8-149">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="2abd8-149">[Visual Basic]</span></span>  
  
```  
vbc.exe /t:library /out:FirstUdf.dll FirstUdf.vb  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2abd8-150">`/t:library` indica che è necessario generare una libreria anziché un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="2abd8-150">`/t:library` indicates that a library, rather than an executable, should be produced.</span></span> <span data-ttu-id="2abd8-151">I file eseguibili non possono essere registrati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2abd8-151">Executables cannot be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2abd8-152">L'esecuzione degli oggetti di database Visual C++ compilati con `/clr:pure` non è più supportata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2abd8-152">Visual C++ database objects compiled with `/clr:pure` are not supported for execution on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2abd8-153">Questo tipo di oggetti di database include, ad esempio, funzioni a valori scalari.</span><span class="sxs-lookup"><span data-stu-id="2abd8-153">For example, such database objects include scalar-valued functions.</span></span>  
  
 <span data-ttu-id="2abd8-154">Di seguito sono riportate la query [!INCLUDE[tsql](../../includes/tsql-md.md)] e una chiamata di esempio per registrare l'assembly e la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2abd8-154">The [!INCLUDE[tsql](../../includes/tsql-md.md)] query and a sample invocation to register the assembly and UDF are:</span></span>  
  
```  
CREATE ASSEMBLY FirstUdf FROM 'FirstUdf.dll';  
GO  
  
CREATE FUNCTION CountSalesOrderHeader() RETURNS INT   
AS EXTERNAL NAME FirstUdf.T.ReturnOrderCount;   
GO  
  
SELECT dbo.CountSalesOrderHeader();  
GO  
  
```  
  
 <span data-ttu-id="2abd8-155">Si noti che il nome della funzione esposto in [!INCLUDE[tsql](../../includes/tsql-md.md)] non dovere corrispondere al nome del metodo statico pubblico di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2abd8-155">Note that the function name as exposed in [!INCLUDE[tsql](../../includes/tsql-md.md)] does not need to match the name of the target public static method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2abd8-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2abd8-156">See Also</span></span>  
 <span data-ttu-id="2abd8-157">[Mapping dei dati dei parametri CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span><span class="sxs-lookup"><span data-stu-id="2abd8-157">[Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span></span>  
 <span data-ttu-id="2abd8-158">[Panoramica degli attributi personalizzati dell'integrazione con CLR](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="2abd8-158">[Overview of CLR Integration Custom Attributes](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span></span>  
 <span data-ttu-id="2abd8-159">[Funzioni definite dall'utente](../user-defined-functions/user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="2abd8-159">[User-Defined Functions](../user-defined-functions/user-defined-functions.md) </span></span>  
 [<span data-ttu-id="2abd8-160">Accesso ai dati da oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="2abd8-160">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
