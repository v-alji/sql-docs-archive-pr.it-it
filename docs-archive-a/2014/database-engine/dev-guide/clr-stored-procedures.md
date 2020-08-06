---
title: Stored procedure CLR | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration], stored procedures
- stored procedures [CLR integration]
- common language runtime [SQL Server], stored procedures
- building database objects [CLR integration], stored procedures
- output parameters [CLR integration]
- tabular results
ms.assetid: bbdd51b2-a9b4-4916-ba6f-7957ac6c3f33
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f8c69435e28bfa67c72e26b7a54e419cd91ef220
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626248"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="d1340-102">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="d1340-102">CLR Stored Procedures</span></span>
  <span data-ttu-id="d1340-103">Le stored procedure sono routine che non possono essere utilizzate in espressioni scalari.</span><span class="sxs-lookup"><span data-stu-id="d1340-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="d1340-104">Diversamente dalle funzioni scalari, possono restituire risultati tabulari e messaggi al client, richiamare istruzioni DDL (Data Definition Language) e DML (Data Manipulation Language) e restituire parametri di output.</span><span class="sxs-lookup"><span data-stu-id="d1340-104">Unlike scalar functions, they can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span> <span data-ttu-id="d1340-105">Per informazioni sui vantaggi dell'integrazione con CLR e sulla scelta tra codice gestito e [!INCLUDE[tsql](../../includes/tsql-md.md)] , vedere [Cenni preliminari sull'integrazione con CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d1340-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-stored-procedures"></a><span data-ttu-id="d1340-106">Requisiti per le stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="d1340-106">Requirements for CLR Stored Procedures</span></span>  
 <span data-ttu-id="d1340-107">Nel Common Language Runtime (CLR), le stored procedure vengono implementate come metodi statici pubblici su una classe in un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly.</span><span class="sxs-lookup"><span data-stu-id="d1340-107">In the common language runtime (CLR), stored procedures are implemented as public static methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly.</span></span> <span data-ttu-id="d1340-108">Il metodo statico può essere dichiarato come void o restituisce un valore integer.</span><span class="sxs-lookup"><span data-stu-id="d1340-108">The static method can either be declared as void, or return an integer value.</span></span> <span data-ttu-id="d1340-109">Se restituisce un valore integer, il numero intero restituito viene considerato come codice restituito dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="d1340-109">If it returns an integer value, the integer returned is treated as the return code from the procedure.</span></span> <span data-ttu-id="d1340-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d1340-110">For example:</span></span>  
  
 `EXECUTE @return_status = procedure_name`  
  
 <span data-ttu-id="d1340-111">La @return_status variabile conterrà il valore restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="d1340-111">The @return_status variable will contain the value returned by the method.</span></span> <span data-ttu-id="d1340-112">Se il metodo viene dichiarato come void, il codice restituito è 0.</span><span class="sxs-lookup"><span data-stu-id="d1340-112">If the method is declared void, the return code is 0.</span></span>  
  
 <span data-ttu-id="d1340-113">Se il metodo accetta parametri, il numero di parametri nell'implementazione di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] deve coincidere con il numero di parametri utilizzato nella dichiarazione [!INCLUDE[tsql](../../includes/tsql-md.md)] della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d1340-113">If the method takes parameters, the number of parameters in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] implementation should be the same as the number of parameters used in the [!INCLUDE[tsql](../../includes/tsql-md.md)] declaration of the stored procedure.</span></span>  
  
 <span data-ttu-id="d1340-114">I parametri passati a una stored procedure possono essere di uno dei tipi nativi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per cui è presente un equivalente nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="d1340-114">Parameters passed to a CLR stored procedure can be any of the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types that have an equivalent in managed code.</span></span> <span data-ttu-id="d1340-115">Affinché la sintassi [!INCLUDE[tsql](../../includes/tsql-md.md)] crei la procedura, questi tipi devono essere specificati con l'equivalente più appropriato del tipo nativo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1340-115">For the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax to create the procedure, these types should be specified with the most appropriate native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type equivalent.</span></span> <span data-ttu-id="d1340-116">Per ulteriori informazioni sulle conversioni di tipi, vedere [mapping dei dati dei parametri CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="d1340-116">For more information about type conversions, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="d1340-117">Parametri valutati a livello di tabella</span><span class="sxs-lookup"><span data-stu-id="d1340-117">Table-Valued Parameters</span></span>  
 <span data-ttu-id="d1340-118">I parametri con valori di tabella, ovvero tipi di tabella definiti dall'utente passati in una procedura o in una funzione, consentono di passare in modo efficiente più righe di dati al server.</span><span class="sxs-lookup"><span data-stu-id="d1340-118">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="d1340-119">Pur essendo caratterizzati da funzionalità simili alle matrici di parametri, i parametri con valori di tabella offrono più flessibilità e una maggiore integrazione con [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1340-119">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d1340-120">Consentono inoltre di ottenere prestazioni potenzialmente migliori.</span><span class="sxs-lookup"><span data-stu-id="d1340-120">They also provide the potential for better performance.</span></span> <span data-ttu-id="d1340-121">I parametri con valori di tabella consentono inoltre di ridurre il numero di round trip al server.</span><span class="sxs-lookup"><span data-stu-id="d1340-121">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="d1340-122">Anziché inviare più richieste al server, ad esempio con un elenco di parametri scalari, è possibile inviare i dati al server sotto forma di parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="d1340-122">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="d1340-123">Un tipo di tabella definito dall'utente non può essere passato come parametro con valori di tabella a una stored procedure gestita o a una funzione in esecuzione nel processo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], né può essere restituito dalle stesse.</span><span class="sxs-lookup"><span data-stu-id="d1340-123">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="d1340-124">Per altre informazioni su TVP, vedere [usare i parametri con valori di tabella &#40;motore di database&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="d1340-124">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="returning-results-from-clr-stored-procedures"></a><span data-ttu-id="d1340-125">Restituzione di risultati da stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="d1340-125">Returning Results from CLR Stored Procedures</span></span>  
 <span data-ttu-id="d1340-126">Le informazioni possono essere restituite in diversi modi dalle stored procedure [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)],</span><span class="sxs-lookup"><span data-stu-id="d1340-126">Information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures in several ways.</span></span> <span data-ttu-id="d1340-127">ad esempio come parametri di output, risultati tabulari e messaggi.</span><span class="sxs-lookup"><span data-stu-id="d1340-127">This includes output parameters, tabular results, and messages.</span></span>  
  
### <a name="output-parameters-and-clr-stored-procedures"></a><span data-ttu-id="d1340-128">Parametri di output e stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="d1340-128">OUTPUT Parameters and CLR Stored Procedures</span></span>  
 <span data-ttu-id="d1340-129">Analogamente alle stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)], le informazioni possono essere restituite dalle stored procedure [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] utilizzando parametri OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="d1340-129">As with [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures using OUTPUT parameters.</span></span> <span data-ttu-id="d1340-130">La sintassi DML di [!INCLUDE[tsql](../../includes/tsql-md.md)] utilizzata per la creazione di stored procedure [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] è la stessa utilizzata per la creazione di stored procedure scritte in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1340-130">The [!INCLUDE[tsql](../../includes/tsql-md.md)] DML syntax used for creating [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures is the same as that used for creating stored procedures written in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d1340-131">Il parametro corrispondente nel codice di implementazione nella classe [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] deve utilizzare un parametro di passaggio per riferimento come argomento.</span><span class="sxs-lookup"><span data-stu-id="d1340-131">The corresponding parameter in the implementation code in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="d1340-132">Si noti che Visual Basic non supporta i parametri di output nello stesso modo in cui avviene in C#.</span><span class="sxs-lookup"><span data-stu-id="d1340-132">Note that Visual Basic does not support output parameters in the same way that C# does.</span></span> <span data-ttu-id="d1340-133">È necessario specificare il parametro per riferimento e applicare l' \<Out()> attributo per rappresentare un parametro di output, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d1340-133">You must specify the parameter by reference and apply the \<Out()> attribute to represent an OUTPUT parameter, as in the following:</span></span>  
  
```vb
Imports System.Runtime.InteropServices  
...  
Public Shared Sub PriceSum ( <Out()> ByRef value As SqlInt32)  
```  
  
 <span data-ttu-id="d1340-134">Nell'esempio seguente viene illustrata una stored procedure che restituisce informazioni tramite un parametro OUTPUT:</span><span class="sxs-lookup"><span data-stu-id="d1340-134">The following shows a stored procedure returning information through an OUTPUT parameter:</span></span>  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void PriceSum(out SqlInt32 value)  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         value = 0;  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT Price FROM Products", connection);  
         SqlDataReader reader = command.ExecuteReader();  
  
         using (reader)  
         {  
            while( reader.Read() )  
            {  
               value += reader.GetSqlInt32(0);  
            }  
         }           
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Runtime.InteropServices  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Executes a query and iterates over the results to perform a summation.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
  
        Using connection As New SqlConnection("context connection=true")  
           value = 0  
           Connection.Open()  
           Dim command As New SqlCommand("SELECT Price FROM Products", connection)  
           Dim reader As SqlDataReader  
           reader = command.ExecuteReader()  
  
           Using reader  
              While reader.Read()  
                 value += reader.GetSqlInt32(0)  
              End While  
           End Using  
        End Using          
    End Sub  
End Class  
```  
  
 <span data-ttu-id="d1340-135">Dopo che l'assembly contenente il stored procedure CLR precedente è stato compilato e creato nel server, [!INCLUDE[tsql](../../includes/tsql-md.md)] per creare la stored procedure nel database viene utilizzato il codice seguente e viene specificato *Sum* come parametro di output.</span><span class="sxs-lookup"><span data-stu-id="d1340-135">Once the assembly containing the above CLR stored procedure has been built and created on the server, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] is used to create the procedure in the database, and specifies *sum* as an OUTPUT parameter.</span></span>  
  
```sql
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
-- if StoredProcedures class was inside a namespace, called MyNS,  
-- you would use:  
-- AS EXTERNAL NAME TestStoredProc.[MyNS.StoredProcedures].PriceSum  
```  
  
 <span data-ttu-id="d1340-136">Si noti che *Sum* viene dichiarato come `int` tipo di dati SQL Server e che il parametro *value* definito nel stored procedure CLR viene specificato come tipo di `SqlInt32` dati CLR.</span><span class="sxs-lookup"><span data-stu-id="d1340-136">Note that *sum* is declared as an `int` SQL Server data type, and that the *value* parameter defined in the CLR stored procedure is specified as a `SqlInt32` CLR data type.</span></span> <span data-ttu-id="d1340-137">Quando un programma chiamante esegue la stored procedure CLR, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] converte automaticamente il `SqlInt32` tipo di dati CLR in un `int` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d1340-137">When a calling program executes the CLR stored procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically converts the `SqlInt32` CLR data type to an `int`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  <span data-ttu-id="d1340-138">Per ulteriori informazioni sui tipi di dati CLR che possono e non possono essere convertiti, vedere [mapping dei dati dei parametri CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="d1340-138">For more information about which CLR data types can and cannot be converted, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="d1340-139">Restituzione di risultati tabulari e messaggi</span><span class="sxs-lookup"><span data-stu-id="d1340-139">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="d1340-140">La restituzione di risultati tabulari e messaggi al client viene eseguita tramite l'oggetto `SqlPipe`, ottenuto tramite la proprietà `Pipe` della classe `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="d1340-140">Returning tabular results and messages to the client is done through the `SqlPipe` object, which is obtained by using the `Pipe` property of the `SqlContext` class.</span></span> <span data-ttu-id="d1340-141">L'oggetto `SqlPipe` include un metodo `Send`.</span><span class="sxs-lookup"><span data-stu-id="d1340-141">The `SqlPipe` object has a `Send` method.</span></span> <span data-ttu-id="d1340-142">Chiamando il metodo `Send`, è possibile trasmettere dati tramite la pipe all'applicazione chiamante.</span><span class="sxs-lookup"><span data-stu-id="d1340-142">By calling the `Send` method, you can transmit data through the pipe to the calling application.</span></span>  
  
 <span data-ttu-id="d1340-143">Sono disponibili diversi overload del metodo `SqlPipe.Send`, incluso uno che invia un oggetto `SqlDataReader` e un altro che invia semplicemente una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="d1340-143">These are several overloads of the `SqlPipe.Send` method, including one that sends a `SqlDataReader` and another that simply sends a text string.</span></span>  
  
###### <a name="returning-messages"></a><span data-ttu-id="d1340-144">Restituzione di messaggi</span><span class="sxs-lookup"><span data-stu-id="d1340-144">Returning Messages</span></span>  
 <span data-ttu-id="d1340-145">Utilizzare `SqlPipe.Send(string)` per inviare messaggi all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="d1340-145">Use `SqlPipe.Send(string)` to send messages to the client application.</span></span> <span data-ttu-id="d1340-146">Il testo del messaggio ha un limite di 8000 caratteri.</span><span class="sxs-lookup"><span data-stu-id="d1340-146">The text of the message is limited to 8000 characters.</span></span> <span data-ttu-id="d1340-147">Se il messaggio supera 8000 caratteri, verrà troncato.</span><span class="sxs-lookup"><span data-stu-id="d1340-147">If the message exceeds 8000 characters, it will be truncated.</span></span>  
  
###### <a name="returning-tabular-results"></a><span data-ttu-id="d1340-148">Restituzione di risultati tabulari</span><span class="sxs-lookup"><span data-stu-id="d1340-148">Returning Tabular Results</span></span>  
 <span data-ttu-id="d1340-149">Per inviare i risultati di una query direttamente al client, utilizzare uno degli overload del metodo `Execute` sull'oggetto `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="d1340-149">To send the results of a query directly to the client, use one of the overloads of the `Execute` method on the `SqlPipe` object.</span></span> <span data-ttu-id="d1340-150">Si tratta della soluzione più efficiente per restituire risultati al client, in quanto i dati vengono trasferiti ai buffer di rete senza essere copiati nella memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="d1340-150">This is the most efficient way to return results to the client, since the data is transferred to the network buffers without being copied into managed memory.</span></span> <span data-ttu-id="d1340-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d1340-151">For example:</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the results to the client directly.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void ExecuteToClient()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version", connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub ExecuteToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="d1340-152">Per inviare i risultati di una query eseguita in precedenza tramite il provider in-process, o per pre-elaborare i dati utilizzando un'implementazione personalizzata di `SqlDataReader`, utilizzare l'overload del metodo `Send` che accetta un oggetto `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="d1340-152">To send the results of a query that was executed previously through the in-process provider (or to pre-process the data using a custom implementation of `SqlDataReader`), use the overload of the `Send` method that takes a `SqlDataReader`.</span></span> <span data-ttu-id="d1340-153">Questo metodo è leggermente più lento del metodo diretto descritto in precedenza, ma offre una maggiore flessibilità per modificare i dati prima di inviarli al client.</span><span class="sxs-lookup"><span data-stu-id="d1340-153">This method is slightly slower than the direct method described previously, but it offers greater flexibility to manipulate the data before it is sent to the client.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the resulting reader to the client  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendReaderToClient()  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("select @@version", connection);  
         SqlDataReader r = command.ExecuteReader();  
         SqlContext.Pipe.Send(r);  
      }  
   }  
}  
```  
 
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendReaderToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="d1340-154">Per creare un set di risultati dinamico, popolarlo e inviarlo al client, è possibile creare record dalla connessione corrente e inviarli tramite `SqlPipe.Send`.</span><span class="sxs-lookup"><span data-stu-id="d1340-154">To create a dynamic result set, populate it and send it to the client, you can create records from the current connection and send them using `SqlPipe.Send`.</span></span>  
  
```csharp  
using System.Data;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
using System.Data.SqlTypes;  
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Create a result set on the fly and send it to the client.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendTransientResultSet()  
   {  
      // Create a record object that represents an individual row, including it's metadata.  
      SqlDataRecord record = new SqlDataRecord(new SqlMetaData("stringcol", SqlDbType.NVarChar, 128));  
  
      // Populate the record.  
      record.SetSqlString(0, "Hello World!");  
  
      // Send the record to the client.  
      SqlContext.Pipe.Send(record);  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Create a result set on the fly and send it to the client.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendTransientResultSet()  
        ' Create a record object that represents an individual row, including it's metadata.  
        Dim record As New SqlDataRecord(New SqlMetaData("stringcol", SqlDbType.NVarChar, 128) )  
  
        ' Populate the record.  
        record.SetSqlString(0, "Hello World!")  
  
        ' Send the record to the client.  
        SqlContext.Pipe.Send(record)          
    End Sub  
End Class   
```  
  
 <span data-ttu-id="d1340-155">Di seguito viene fornito un esempio di invio di un risultato tabulare e di un messaggio tramite `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="d1340-155">Here is an example of sending a tabular result and a message through `SqlPipe`.</span></span>  
  
```csharp  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void HelloWorld()  
   {  
      SqlContext.Pipe.Send("Hello world! It's now " + System.DateTime.Now.ToString()+"\n");  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT ProductNumber FROM ProductMaster", connection);  
         SqlDataReader reader = command.ExecuteReader();  
         SqlContext.Pipe.Send(reader);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub HelloWorld()  
        SqlContext.Pipe.Send("Hello world! It's now " & System.DateTime.Now.ToString() & "\n")  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT ProductNumber FROM ProductMaster", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class   
```  
  
 <span data-ttu-id="d1340-156">Il primo metodo `Send` invia un messaggio al client, mentre il secondo invia un risultato tabulare tramite `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="d1340-156">The first `Send` sends a message to the client, while the second sends a tabular result using `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="d1340-157">Si noti che questi esempi vengono forniti esclusivamente a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="d1340-157">Note that these examples are for illustrative purposes only.</span></span> <span data-ttu-id="d1340-158">Le funzioni CLR sono più appropriate rispetto alle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] semplici per le applicazioni che richiedono un elevato carico di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d1340-158">CLR functions are more appropriate than simple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for computation-intensive applications.</span></span> <span data-ttu-id="d1340-159">Una stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] quasi equivalente all'esempio precedente è la seguente:</span><span class="sxs-lookup"><span data-stu-id="d1340-159">An almost equivalent [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure to the previous example is:</span></span>  
  
```sql
CREATE PROCEDURE HelloWorld() AS  
BEGIN  
PRINT('Hello world!')  
SELECT ProductNumber FROM ProductMaster  
END;  
```  
  
> [!NOTE]  
>  <span data-ttu-id="d1340-160">Messaggi e set di risultati vengono recuperati in modo diverso nell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="d1340-160">Messages and result sets are retrieved differently in the client application.</span></span> <span data-ttu-id="d1340-161">I set di risultati, ad esempio, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] vengono visualizzati nella visualizzazione **risultati** e i messaggi vengono visualizzati nel riquadro **messaggi** .</span><span class="sxs-lookup"><span data-stu-id="d1340-161">For instance, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] result sets appear in the **Results** view, and messages appear in the **Messages** pane.</span></span>  
  
 <span data-ttu-id="d1340-162">Se il codice di Visual C# precedente viene salvato in un file MyFirstUdp.cs e compilato con:</span><span class="sxs-lookup"><span data-stu-id="d1340-162">If the above Visual C# code is saved in a file MyFirstUdp.cs and compiled with:</span></span>  
  
```console
csc /t:library /out:MyFirstUdp.dll MyFirstUdp.cs   
```  
  
 <span data-ttu-id="d1340-163">O se il codice di Visual Basic precedente viene salvato in un file MyFirstUdp.cs e compilato con:</span><span class="sxs-lookup"><span data-stu-id="d1340-163">Or, if the above Visual Basic code is saved in a file MyFirstUdp.vb and compiled with:</span></span>  
  
```console
vbc /t:library /out:MyFirstUdp.dll MyFirstUdp.vb   
```  
  
> [!NOTE]  
>  <span data-ttu-id="d1340-164">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], l'esecuzione di oggetti di database Visual C++, ad esempio le stored procedure, compilati con `/clr:pure` non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="d1340-164">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], Visual C++ database objects (such as stored procedures) compiled with `/clr:pure` are not supported for execution.</span></span>  
  
 <span data-ttu-id="d1340-165">L'assembly risultante può essere registrato e il punto di ingresso richiamato utilizzando l'istruzione DDL seguente:</span><span class="sxs-lookup"><span data-stu-id="d1340-165">The resulting assembly can be registered, and the entry point invoked, with the following DDL:</span></span>  
  
```sql
CREATE ASSEMBLY MyFirstUdp FROM 'C:\Programming\MyFirstUdp.dll';  
CREATE PROCEDURE HelloWorld  
AS EXTERNAL NAME MyFirstUdp.StoredProcedures.HelloWorld;  
EXEC HelloWorld;  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1340-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1340-166">See Also</span></span>  
 <span data-ttu-id="d1340-167">[Funzioni CLR definite dall'utente](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="d1340-167">[CLR User-Defined Functions](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="d1340-168">[Tipi CLR definiti dall'utente](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="d1340-168">[CLR User-Defined Types](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 [<span data-ttu-id="d1340-169">Trigger CLR</span><span class="sxs-lookup"><span data-stu-id="d1340-169">CLR Triggers</span></span>](../../../2014/database-engine/dev-guide/clr-triggers.md)  
  
  
