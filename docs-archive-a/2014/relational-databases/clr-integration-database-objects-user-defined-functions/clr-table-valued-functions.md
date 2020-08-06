---
title: Funzioni CLR con valori di tabella | Microsoft Docs
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
- Transact-SQL table-valued functions
- table-valued functions [CLR integration]
- TVFs [CLR integration]
ms.assetid: 9a6133ea-36e9-45bf-b572-1c0df3d6c194
author: rothja
ms.author: jroth
ms.openlocfilehash: b700aba5a753ecd8ee50ee9b7679cafb2f1f8581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629439"
---
# <a name="clr-table-valued-functions"></a><span data-ttu-id="03dfc-102">Funzioni CLR con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="03dfc-102">CLR Table-Valued Functions</span></span>
  <span data-ttu-id="03dfc-103">Una funzione con valori di tabella è una funzione definita dall'utente che restituisce una tabella.</span><span class="sxs-lookup"><span data-stu-id="03dfc-103">A table-valued function is a user-defined function that returns a table.</span></span>  
  
 <span data-ttu-id="03dfc-104">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estende la funzionalità delle funzioni con valori di tabella consentendo la definizione di una funzione di questo tipo in qualsiasi linguaggio gestito.</span><span class="sxs-lookup"><span data-stu-id="03dfc-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extends the functionality of table-valued functions by allowing you to define a table-valued function in any managed language.</span></span> <span data-ttu-id="03dfc-105">I dati vengono restituiti da una funzione con valori di tabella tramite un oggetto `IEnumerable` o `IEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="03dfc-105">Data is returned from a table-valued function through an `IEnumerable` or `IEnumerator` object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03dfc-106">Per le funzioni con valori di tabella, le colonne del tipo di tabella restituito non possono includere colonne timestamp o colonne con tipo di dati string non Unicode, ad esempio `char`, `varchar` e `text`.</span><span class="sxs-lookup"><span data-stu-id="03dfc-106">For table-valued functions, the columns of the return table type cannot include timestamp columns or non-Unicode string data type columns (such as `char`, `varchar`, and `text`).</span></span> <span data-ttu-id="03dfc-107">Il vincolo NOT NULL non è supportato.</span><span class="sxs-lookup"><span data-stu-id="03dfc-107">The NOT NULL constraint is not supported.</span></span>  
  
## <a name="differences-between-transact-sql-and-clr-table-valued-functions"></a><span data-ttu-id="03dfc-108">Differenze tra funzioni con valori di tabella CLR e Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03dfc-108">Differences Between Transact-SQL and CLR Table-Valued Functions</span></span>  
 <span data-ttu-id="03dfc-109">Le funzioni con valori di tabella [!INCLUDE[tsql](../../includes/tsql-md.md)] materializzano i risultati della chiamata alla funzione in una tabella intermedia.</span><span class="sxs-lookup"><span data-stu-id="03dfc-109">[!INCLUDE[tsql](../../includes/tsql-md.md)] table-valued functions materialize the results of calling the function into an intermediate table.</span></span> <span data-ttu-id="03dfc-110">Poiché utilizzano una tabella intermedia, possono supportare vincoli e indici univoci sui risultati.</span><span class="sxs-lookup"><span data-stu-id="03dfc-110">Since they use an intermediate table, they can support constraints and unique indexes over the results.</span></span> <span data-ttu-id="03dfc-111">Queste caratteristiche possono rivelarsi estremamente utili quando vengono restituiti risultati di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="03dfc-111">These features can be extremely useful when large results are returned.</span></span>  
  
 <span data-ttu-id="03dfc-112">Le funzioni con valori di tabella CLR rappresentano invece un modello di flusso alternativo.</span><span class="sxs-lookup"><span data-stu-id="03dfc-112">In contrast, CLR table-valued functions represent a streaming alternative.</span></span> <span data-ttu-id="03dfc-113">Non è necessario che l'intero set di risultati venga materializzato in una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="03dfc-113">There is no requirement that the entire set of results be materialized in a single table.</span></span> <span data-ttu-id="03dfc-114">L'oggetto `IEnumerable` restituito dalla funzione gestita viene chiamato direttamente dal piano di esecuzione della query che chiama la funzione con valori di tabella e i risultati vengono utilizzati in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="03dfc-114">The `IEnumerable` object returned by the managed function is directly called by the execution plan of the query that calls the table-valued function, and the results are consumed in an incremental manner.</span></span> <span data-ttu-id="03dfc-115">Questo modello di flusso consente di utilizzare i risultati non appena è disponibile la prima riga invece di dover attendere il popolamento dell'intera tabella.</span><span class="sxs-lookup"><span data-stu-id="03dfc-115">This streaming model ensures that results can be consumed immediately after the first row is available, instead of waiting for the entire table to be populated.</span></span> <span data-ttu-id="03dfc-116">Rappresenta inoltre un'alternativa migliore in presenza di grandi quantità di righe restituite, in quanto non devono essere materializzate interamente in memoria.</span><span class="sxs-lookup"><span data-stu-id="03dfc-116">It is also a better alternative if you have very large numbers of rows returned, because they do not have to be materialized in memory as a whole.</span></span> <span data-ttu-id="03dfc-117">Una funzione con valori di tabella gestita, ad esempio, può essere utilizzata per analizzare un file di testo e restituire ogni riga del file come riga di tabella.</span><span class="sxs-lookup"><span data-stu-id="03dfc-117">For example, a managed table-valued function could be used to parse a text file and return each line as a row.</span></span>  
  
## <a name="implementing-table-valued-functions"></a><span data-ttu-id="03dfc-118">Implementazione di funzioni con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="03dfc-118">Implementing Table-Valued Functions</span></span>  
 <span data-ttu-id="03dfc-119">È possibile implementare funzioni con valori di tabella come metodi di una classe in un assembly [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03dfc-119">Implement table-valued functions as methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework assembly.</span></span> <span data-ttu-id="03dfc-120">Il codice della funzione con valori di tabella deve implementare l'interfaccia `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="03dfc-120">Your table-valued function code must implement the `IEnumerable` interface.</span></span> <span data-ttu-id="03dfc-121">L'interfaccia `IEnumerable` è definita in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03dfc-121">The `IEnumerable` interface is defined in the .NET Framework.</span></span> <span data-ttu-id="03dfc-122">I tipi che rappresentano matrici e raccolte in .NET Framework implementano già l'interfaccia `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="03dfc-122">Types representing arrays and collections in the .NET Framework already implement the `IEnumerable` interface.</span></span> <span data-ttu-id="03dfc-123">Questo semplifica la scrittura di funzioni con valori di tabella che convertono una raccolta o una matrice in un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="03dfc-123">This makes it easy for writing table-valued functions that convert a collection or an array into a result set.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="03dfc-124">Parametri valutati a livello di tabella</span><span class="sxs-lookup"><span data-stu-id="03dfc-124">Table-Valued Parameters</span></span>  
 <span data-ttu-id="03dfc-125">I parametri con valori di tabella sono tipi di tabella definiti dall'utente passati in una procedura o in una funzione che consentono di passare in modo efficiente più righe di dati al server.</span><span class="sxs-lookup"><span data-stu-id="03dfc-125">Table-valued parameters are user-defined table types that are passed into a procedure or function and provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="03dfc-126">I parametri con valori di tabella offrono funzionalità simili a quelle delle matrici di parametri, ma garantiscono più flessibilità e una maggiore integrazione con [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03dfc-126">Table-valued parameters provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="03dfc-127">Consentono inoltre di ottenere prestazioni potenzialmente migliori.</span><span class="sxs-lookup"><span data-stu-id="03dfc-127">They also provide the potential for better performance.</span></span> <span data-ttu-id="03dfc-128">I parametri con valori di tabella aiutano anche a ridurre il numero di round trip al server.</span><span class="sxs-lookup"><span data-stu-id="03dfc-128">Table-valued parameters also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="03dfc-129">Anziché inviare più richieste al server, ad esempio con un elenco di parametri scalari, è possibile inviare i dati al server sotto forma di parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="03dfc-129">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a table-valued parameter.</span></span> <span data-ttu-id="03dfc-130">Un tipo di tabella definito dall'utente non può essere passato come parametro con valori di tabella a una stored procedure gestita o a una funzione in esecuzione nel processo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], né può essere restituito dalle stesse.</span><span class="sxs-lookup"><span data-stu-id="03dfc-130">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="03dfc-131">Per altre informazioni sui parametri con valori di tabella, vedere [Usare parametri con valori di tabella &#40;motore di database&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="03dfc-131">For more information about table-valued parameters, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="output-parameters-and-table-valued-functions"></a><span data-ttu-id="03dfc-132">Parametri di output e funzioni con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="03dfc-132">Output Parameters and Table-Valued Functions</span></span>  
 <span data-ttu-id="03dfc-133">Le funzioni con valori di tabella possono restituire le informazioni tramite parametri di output.</span><span class="sxs-lookup"><span data-stu-id="03dfc-133">Information may be returned from table-valued functions using output parameters.</span></span> <span data-ttu-id="03dfc-134">Il parametro corrispondente nella funzione con valori di tabella nel codice di implementazione deve utilizzare un parametro di passaggio per riferimento come argomento.</span><span class="sxs-lookup"><span data-stu-id="03dfc-134">The corresponding parameter in the implementation code table-valued function should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="03dfc-135">Si noti che Visual Basic non supporta parametri di output nello stesso modo in cui tali parametri sono supportati in Visual C#.</span><span class="sxs-lookup"><span data-stu-id="03dfc-135">Note that Visual Basic does not support output parameters in the same way that Visual C# does.</span></span> <span data-ttu-id="03dfc-136">È necessario specificare il parametro per riferimento e applicare l' \<Out()> attributo per rappresentare un parametro di output, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="03dfc-136">You must specify the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
...  
Public Shared Sub FillRow ( <Out()> ByRef value As SqlInt32)  
```  
  
### <a name="defining-a-table-valued-function-in-transact-sql"></a><span data-ttu-id="03dfc-137">Definizione di una funzione con valori di tabella in Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03dfc-137">Defining a Table-Valued Function in Transact-SQL</span></span>  
 <span data-ttu-id="03dfc-138">La sintassi per la definizione di una funzione con valori di tabella CLR è simile a quella di una funzione con valori di tabella [!INCLUDE[tsql](../../includes/tsql-md.md)], con l'aggiunta della clausola `EXTERNAL NAME`.</span><span class="sxs-lookup"><span data-stu-id="03dfc-138">The syntax for defining a CLR table-valued function is similar to that of a [!INCLUDE[tsql](../../includes/tsql-md.md)] table-valued function, with the addition of the `EXTERNAL NAME` clause.</span></span> <span data-ttu-id="03dfc-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="03dfc-139">For example:</span></span>  
  
```  
CREATE FUNCTION GetEmpFirstLastNames()  
RETURNS TABLE (FirstName NVARCHAR(4000), LastName NVARCHAR(4000))  
EXTERNAL NAME MyDotNETAssembly.[MyNamespace.MyClassname]. GetEmpFirstLastNames;  
```  
  
 <span data-ttu-id="03dfc-140">Le funzioni con valori di tabella vengono utilizzate per rappresentare i dati in formato relazionale per un'ulteriore elaborazione nelle query, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="03dfc-140">Table-valued functions are used to represent data in relational form for further processing in queries such as:</span></span>  
  
```  
select * from function();  
select * from tbl join function() f on tbl.col = f.col;  
select * from table t cross apply function(t.column);  
```  
  
 <span data-ttu-id="03dfc-141">Le funzioni con valori di tabella possono restituire una tabella nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="03dfc-141">Table-valued functions can return a table when:</span></span>  
  
-   <span data-ttu-id="03dfc-142">Vengono create da argomenti di input scalari.</span><span class="sxs-lookup"><span data-stu-id="03dfc-142">Created from scalar input arguments.</span></span> <span data-ttu-id="03dfc-143">Una funzione con valori di tabella che utilizza, ad esempio, una stringa di numeri delimitati da virgole e trasforma i numeri in tabella tramite Pivot.</span><span class="sxs-lookup"><span data-stu-id="03dfc-143">For example, a table-valued function that takes a comma-delimited string of numbers and pivots them into a table.</span></span>  
  
-   <span data-ttu-id="03dfc-144">Vengono generate da dati esterni.</span><span class="sxs-lookup"><span data-stu-id="03dfc-144">Generated from external data.</span></span> <span data-ttu-id="03dfc-145">Una funzione con valori di tabella che legge, ad esempio, il log eventi e lo espone come tabella.</span><span class="sxs-lookup"><span data-stu-id="03dfc-145">For example, a table-valued function that reads the event log and exposes it as a table.</span></span>  
  
 <span data-ttu-id="03dfc-146">**Nota** Una funzione con valori di tabella può eseguire l'accesso ai dati solo tramite una [!INCLUDE[tsql](../../includes/tsql-md.md)] query nel `InitMethod` metodo e non nel `FillRow` metodo.</span><span class="sxs-lookup"><span data-stu-id="03dfc-146">**Note** A table-valued function can only perform data access through a [!INCLUDE[tsql](../../includes/tsql-md.md)] query in the `InitMethod` method, and not in the `FillRow` method.</span></span> <span data-ttu-id="03dfc-147">`InitMethod` deve essere contrassegnato con la proprietà dell'attributo `SqlFunction.DataAccess.Read` se viene eseguita una query [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03dfc-147">The `InitMethod` should be marked with the `SqlFunction.DataAccess.Read` attribute property if a [!INCLUDE[tsql](../../includes/tsql-md.md)] query is performed.</span></span>  
  
## <a name="a-sample-table-valued-function"></a><span data-ttu-id="03dfc-148">Funzione con valori di tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="03dfc-148">A Sample Table-Valued Function</span></span>  
 <span data-ttu-id="03dfc-149">La funzione con valori di tabella seguente restituisce informazioni dal registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="03dfc-149">The following table-valued function returns information from the system event log.</span></span> <span data-ttu-id="03dfc-150">La funzione accetta un singolo argomento stringa contenente il nome del registro eventi da leggere.</span><span class="sxs-lookup"><span data-stu-id="03dfc-150">The function takes a single string argument containing the name of the event log to read.</span></span>  
  
###### <a name="sample-code"></a><span data-ttu-id="03dfc-151">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="03dfc-151">Sample Code</span></span>  
  
```csharp  
using System;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Collections;  
using System.Data.SqlTypes;  
using System.Diagnostics;  
  
public class TabularEventLog  
{  
    [SqlFunction(FillRowMethodName = "FillRow")]  
    public static IEnumerable InitMethod(String logname)  
    {  
        return new EventLog(logname).Entries;    }  
  
    public static void FillRow(Object obj, out SqlDateTime timeWritten, out SqlChars message, out SqlChars category, out long instanceId)  
    {  
        EventLogEntry eventLogEntry = (EventLogEntry)obj;  
        timeWritten = new SqlDateTime(eventLogEntry.TimeWritten);  
        message = new SqlChars(eventLogEntry.Message);  
        category = new SqlChars(eventLogEntry.Category);  
        instanceId = eventLogEntry.InstanceId;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data.Sql  
Imports Microsoft.SqlServer.Server  
Imports System.Collections  
Imports System.Data.SqlTypes  
Imports System.Diagnostics  
Imports System.Runtime.InteropServices  
  
Public Class TabularEventLog  
    <SqlFunction(FillRowMethodName:="FillRow")> _  
    Public Shared Function InitMethod(ByVal logname As String) As IEnumerable  
        Return New EventLog(logname).Entries  
    End Function  
  
    Public Shared Sub FillRow(ByVal obj As Object, <Out()> ByRef timeWritten As SqlDateTime, <Out()> ByRef message As SqlChars, <Out()> ByRef category As SqlChars, <Out()> ByRef instanceId As Long)  
        Dim eventLogEnTry As EventLogEntry = CType(obj, EventLogEntry)  
        timeWritten = New SqlDateTime(eventLogEnTry.TimeWritten)  
        message = New SqlChars(eventLogEnTry.Message)  
        category = New SqlChars(eventLogEnTry.Category)  
        instanceId = eventLogEnTry.InstanceId  
    End Sub  
End Class  
```  
  
###### <a name="declaring-and-using-the-sample-table-valued-function"></a><span data-ttu-id="03dfc-152">Dichiarazione e utilizzo della funzione con valori di tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="03dfc-152">Declaring and Using the Sample Table-Valued Function</span></span>  
 <span data-ttu-id="03dfc-153">Dopo che la funzione con valori di tabella è stata compilata, può essere dichiarata in [!INCLUDE[tsql](../../includes/tsql-md.md)] nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="03dfc-153">After the sample table-valued function has been compiled, it can be declared in [!INCLUDE[tsql](../../includes/tsql-md.md)] like this:</span></span>  
  
```  
use master;  
-- Replace SQL_Server_logon with your SQL Server user credentials.  
GRANT EXTERNAL ACCESS ASSEMBLY TO [SQL_Server_logon];   
-- Modify the following line to specify a different database.  
ALTER DATABASE master SET TRUSTWORTHY ON;  
  
-- Modify the next line to use the appropriate database.  
CREATE ASSEMBLY tvfEventLog   
FROM 'D:\assemblies\tvfEventLog\tvfeventlog.dll'   
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
GO  
CREATE FUNCTION ReadEventLog(@logname nvarchar(100))  
RETURNS TABLE   
(logTime datetime,Message nvarchar(4000),Category nvarchar(4000),InstanceId bigint)  
AS   
EXTERNAL NAME tvfEventLog.TabularEventLog.InitMethod;  
GO  
```  
  
 <span data-ttu-id="03dfc-154">L'esecuzione degli oggetti di database Visual C++ compilati con /clr:pure non è più supportata in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03dfc-154">Visual C++ database objects compiled with /clr:pure are not supported for execution on [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="03dfc-155">Tali oggetti di database, ad esempio, includono funzioni con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="03dfc-155">For example, such database objects include table-valued functions.</span></span>  
  
 <span data-ttu-id="03dfc-156">Per testare l'esempio, provare a utilizzare il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="03dfc-156">To test the sample, try the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
```  
-- Select the top 100 events,  
SELECT TOP 100 *  
FROM dbo.ReadEventLog(N'Security') as T;  
go  
  
-- Select the last 10 login events.  
SELECT TOP 10 T.logTime, T.Message, T.InstanceId   
FROM dbo.ReadEventLog(N'Security') as T  
WHERE T.Category = N'Logon/Logoff';  
go  
```  
  
## <a name="sample-returning-the-results-of-a-sql-server-query"></a><span data-ttu-id="03dfc-157">Esempio: Restituzione dei risultati di una query di SQL Server</span><span class="sxs-lookup"><span data-stu-id="03dfc-157">Sample: Returning the Results of a SQL Server Query</span></span>  
 <span data-ttu-id="03dfc-158">Nell'esempio seguente viene illustrata una funzione con valori di tabella che esegue una query su un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03dfc-158">The following sample shows a table-valued function that queries a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="03dfc-159">In questo esempio viene utilizzato il database AdventureWorks Light di [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03dfc-159">This sample uses the AdventureWorks Light database from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="03dfc-160">[https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843)Per ulteriori informazioni sul download di AdventureWorks, vedere.</span><span class="sxs-lookup"><span data-stu-id="03dfc-160">See [https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843) for more information on downloading AdventureWorks.</span></span>  
  
 <span data-ttu-id="03dfc-161">Assegnare al file di codice sorgente il nome FindInvalidEmails.cs o FindInvalidEmails.vb.</span><span class="sxs-lookup"><span data-stu-id="03dfc-161">Name your source code file FindInvalidEmails.cs or FindInvalidEmails.vb.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
  
using Microsoft.SqlServer.Server;  
  
public partial class UserDefinedFunctions {  
   private class EmailResult {  
      public SqlInt32 CustomerId;  
      public SqlString EmailAdress;  
  
      public EmailResult(SqlInt32 customerId, SqlString emailAdress) {  
         CustomerId = customerId;  
         EmailAdress = emailAdress;  
      }  
   }  
  
   public static bool ValidateEmail(SqlString emailAddress) {  
      if (emailAddress.IsNull)  
         return false;  
  
      if (!emailAddress.Value.EndsWith("@adventure-works.com"))  
         return false;  
  
      // Validate the address. Put any more rules here.  
      return true;  
   }  
  
   [SqlFunction(  
       DataAccess = DataAccessKind.Read,  
       FillRowMethodName = "FindInvalidEmails_FillRow",  
       TableDefinition="CustomerId int, EmailAddress nvarchar(4000)")]  
   public static IEnumerable FindInvalidEmails(SqlDateTime modifiedSince) {  
      ArrayList resultCollection = new ArrayList();  
  
      using (SqlConnection connection = new SqlConnection("context connection=true")) {  
         connection.Open();  
  
         using (SqlCommand selectEmails = new SqlCommand(  
             "SELECT " +  
             "[CustomerID], [EmailAddress] " +  
             "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " +  
             "WHERE [ModifiedDate] >= @modifiedSince",  
             connection)) {  
            SqlParameter modifiedSinceParam = selectEmails.Parameters.Add(  
                "@modifiedSince",  
                SqlDbType.DateTime);  
            modifiedSinceParam.Value = modifiedSince;  
  
            using (SqlDataReader emailsReader = selectEmails.ExecuteReader()) {  
               while (emailsReader.Read()) {  
                  SqlString emailAddress = emailsReader.GetSqlString(1);  
                  if (ValidateEmail(emailAddress)) {  
                     resultCollection.Add(new EmailResult(  
                         emailsReader.GetSqlInt32(0),  
                         emailAddress));  
                  }  
               }  
            }  
         }  
      }  
  
      return resultCollection;  
   }  
  
   public static void FindInvalidEmails_FillRow(  
       object emailResultObj,  
       out SqlInt32 customerId,  
       out SqlString emailAdress) {  
      EmailResult emailResult = (EmailResult)emailResultObj;  
  
      customerId = emailResult.CustomerId;  
      emailAdress = emailResult.EmailAdress;  
   }  
};  
```  
  
```vb  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, ByRef customerId As SqlInt32, ByRef emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End ClassImports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, customerId As SqlInt32, emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End Class  
```  
  
 <span data-ttu-id="03dfc-162">Compilare il codice sorgente in una DLL e copiare la DLL nella directory radice dell'unità C.</span><span class="sxs-lookup"><span data-stu-id="03dfc-162">Compile the source code to a DLL and copy the DLL to the root directory of your C drive.</span></span>  <span data-ttu-id="03dfc-163">Eseguire quindi la query [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente.</span><span class="sxs-lookup"><span data-stu-id="03dfc-163">Then, execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] query.</span></span>  
  
```  
use AdventureWorksLT2008;  
go  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'FindInvalidEmails')  
   DROP FUNCTION FindInvalidEmails;  
go  
  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'MyClrCode')  
   DROP ASSEMBLY MyClrCode;  
go  
  
CREATE ASSEMBLY MyClrCode FROM 'C:\FindInvalidEmails.dll'  
WITH PERMISSION_SET = SAFE -- EXTERNAL_ACCESS;  
GO  
  
CREATE FUNCTION FindInvalidEmails(@ModifiedSince datetime)   
RETURNS TABLE (  
   CustomerId int,  
   EmailAddress nvarchar(4000)  
)  
AS EXTERNAL NAME MyClrCode.UserDefinedFunctions.[FindInvalidEmails];  
go  
  
SELECT * FROM FindInvalidEmails('2000-01-01');  
go  
```  
  
