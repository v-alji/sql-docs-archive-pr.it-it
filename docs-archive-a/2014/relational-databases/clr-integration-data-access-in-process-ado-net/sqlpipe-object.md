---
title: Oggetto SqlPipe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- custom result sets [CLR integration]
- SqlPipe object
- tabular results
ms.assetid: 3e090faf-085f-4c01-a565-79e3f1c36e3b
author: rothja
ms.author: jroth
ms.openlocfilehash: 0044815a0b20d72b48b87bfe8f693d7196aaeaf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629871"
---
# <a name="sqlpipe-object"></a><span data-ttu-id="319ab-102">Oggetto SqlPipe</span><span class="sxs-lookup"><span data-stu-id="319ab-102">SqlPipe Object</span></span>
  <span data-ttu-id="319ab-103">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è molto comune scrivere una stored procedure (o una stored procedure estesa) per l'invio di risultati o parametri di output al client chiamante.</span><span class="sxs-lookup"><span data-stu-id="319ab-103">In previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is very common to write a stored procedure (or an extended stored procedure) that sends results or output parameters to the calling client.</span></span>  
  
 <span data-ttu-id="319ab-104">In una stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] qualsiasi istruzione `SELECT` che restituisce zero o più righe invia i risultati alla "pipe" del chiamante connesso.</span><span class="sxs-lookup"><span data-stu-id="319ab-104">In a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, any `SELECT` statement that returns zero or more rows sends the results to the connected caller's "pipe."</span></span>  
  
 <span data-ttu-id="319ab-105">Per gli oggetti di database CLR (Common Language Runtime) in esecuzione in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è possibile inviare i risultati alla pipe connessa utilizzando i metodi `Send` dell'oggetto `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="319ab-105">For common language runtime (CLR) database objects running in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can send results to the connected pipe using the `Send` methods of the `SqlPipe` object.</span></span> <span data-ttu-id="319ab-106">Accedere alla proprietà `Pipe` dell'oggetto `SqlContext` per ottenere l'oggetto `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="319ab-106">Access the `Pipe` property of the `SqlContext` object to obtain the `SqlPipe` object.</span></span> <span data-ttu-id="319ab-107">Concettualmente la classe `SqlPipe` è simile alla classe `Response` di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="319ab-107">The `SqlPipe` class is conceptually similar to the `Response` class found in ASP.NET.</span></span> <span data-ttu-id="319ab-108">Per ulteriori informazioni, vedere documentazione di riferimento per la classe SqlPipe in .NET Framework SDK (Software Development Kit).</span><span class="sxs-lookup"><span data-stu-id="319ab-108">For more information, see the SqlPipe Class reference documentation in the .NET Framework software development kit.</span></span>  
  
## <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="319ab-109">Restituzione di risultati tabulari e messaggi</span><span class="sxs-lookup"><span data-stu-id="319ab-109">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="319ab-110">L'oggetto `SqlPipe` dispone di un metodo `Send` che presenta tre overload,</span><span class="sxs-lookup"><span data-stu-id="319ab-110">The `SqlPipe` has a `Send` method, which has three overloads.</span></span> <span data-ttu-id="319ab-111">ovvero:</span><span class="sxs-lookup"><span data-stu-id="319ab-111">They are:</span></span>  
  
-   `void Send(string message)`  
  
-   `void Send(SqlDataReader reader)`  
  
-   `void Send(SqlDataRecord record)`  
  
 <span data-ttu-id="319ab-112">Il metodo `Send` invia dati direttamente al client o al chiamante.</span><span class="sxs-lookup"><span data-stu-id="319ab-112">The `Send` method sends data straight to the client or caller.</span></span> <span data-ttu-id="319ab-113">In genere è il client che utilizza l'output proveniente dal metodo `SqlPipe`, ma nel caso di stored procedure CLR nidificate il consumer dell'output può anche essere una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="319ab-113">It is usually the client that consumes the output from the `SqlPipe`, but in the case of nested CLR stored procedures the output consumer can also be a stored procedure.</span></span> <span data-ttu-id="319ab-114">Procedure1 chiama ad esempio SqlCommand.ExecuteReader() con il testo del comando "EXEC Procedure2".</span><span class="sxs-lookup"><span data-stu-id="319ab-114">For example, Procedure1 calls SqlCommand.ExecuteReader() with the command text "EXEC Procedure2".</span></span> <span data-ttu-id="319ab-115">Procedure2 è anche una stored procedure gestita.</span><span class="sxs-lookup"><span data-stu-id="319ab-115">Procedure2 is also a managed stored procedure.</span></span> <span data-ttu-id="319ab-116">Se Procedure2 chiama il metodo SqlPipe.Send(SqlDataRecord), la riga verrà inviata al lettore di Procedure1, non al client.</span><span class="sxs-lookup"><span data-stu-id="319ab-116">If Procedure2 now calls SqlPipe.Send( SqlDataRecord ), the row is sent to Procedure1's reader, not the client.</span></span>  
  
 <span data-ttu-id="319ab-117">Il metodo `Send` invia un messaggio stringa che viene visualizzato sul client come messaggio informativo, equivalente a PRINT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="319ab-117">The `Send` method sends a string message that appears on the client as an information message, equivalent to PRINT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="319ab-118">Può inoltre inviare un set di risultati a riga singola utilizzando `SqlDataRecord` o un set di risultati a più righe utilizzando `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="319ab-118">It can also send a single-row result-set using `SqlDataRecord`, or a multi-row result-set using a `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="319ab-119">L'oggetto `SqlPipe` include inoltre un metodo `ExecuteAndSend`.</span><span class="sxs-lookup"><span data-stu-id="319ab-119">The `SqlPipe` object also has an `ExecuteAndSend` method.</span></span> <span data-ttu-id="319ab-120">Questo metodo può essere utilizzato per eseguire un comando (passato come oggetto `SqlCommand`) e per restituire i risultati direttamente al chiamante.</span><span class="sxs-lookup"><span data-stu-id="319ab-120">This method can be used to execute a command (passed as a `SqlCommand` object) and send results directly back to the caller.</span></span> <span data-ttu-id="319ab-121">Se sono presenti errori nel comando inviato, le eccezioni vengono inviate alla pipe, ma una copia viene inviata anche al codice gestito chiamante.</span><span class="sxs-lookup"><span data-stu-id="319ab-121">If there are errors in the command that was submitted, exceptions are sent to the pipe, but a copy is also sent to calling managed code.</span></span> <span data-ttu-id="319ab-122">Se il codice chiamante non rileva l'eccezione, lo stack verrà propagato al codice [!INCLUDE[tsql](../../includes/tsql-md.md)] e verrà visualizzato due volte nell'output.</span><span class="sxs-lookup"><span data-stu-id="319ab-122">If the calling code does not catch the exception, it propagates up the stack to the [!INCLUDE[tsql](../../includes/tsql-md.md)] code and appears in the output twice.</span></span> <span data-ttu-id="319ab-123">Se il codice chiamante rileva l'eccezione, il consumer della pipe visualizzerà l'errore, ma questo non verrà duplicato.</span><span class="sxs-lookup"><span data-stu-id="319ab-123">If the calling code does catch the exception, the pipe consumer still sees the error, but there is not a duplicate error.</span></span>  
  
 <span data-ttu-id="319ab-124">Il metodo può utilizzare solo un comando `SqlCommand` associato alla connessione con contesto e non un comando associato alla connessione senza contesto.</span><span class="sxs-lookup"><span data-stu-id="319ab-124">It can only take a `SqlCommand` that is associated with the context connection; it cannot take a command that is associated with the non-context connection.</span></span>  
  
## <a name="returning-custom-result-sets"></a><span data-ttu-id="319ab-125">Restituzione di set di risultati personalizzati</span><span class="sxs-lookup"><span data-stu-id="319ab-125">Returning Custom Result Sets</span></span>  
 <span data-ttu-id="319ab-126">Le stored procedure gestite possono inviare set di risultati che non provengono da un oggetto `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="319ab-126">Managed stored procedures can send result sets that do not come from a `SqlDataReader`.</span></span> <span data-ttu-id="319ab-127">Il metodo `SendResultsStart`, insieme ai metodi `SendResultsRow` e `SendResultsEnd`, consente alle stored procedure di inviare set di risultati personalizzati al client.</span><span class="sxs-lookup"><span data-stu-id="319ab-127">The `SendResultsStart` method, along with `SendResultsRow` and `SendResultsEnd`, allows stored procedures to send custom result sets to the client.</span></span>  
  
 <span data-ttu-id="319ab-128">`SendResultsStart` utilizza un oggetto `SqlDataRecord` come input.</span><span class="sxs-lookup"><span data-stu-id="319ab-128">`SendResultsStart` takes a `SqlDataRecord` as an input.</span></span> <span data-ttu-id="319ab-129">Indica l'inizio di un set di risultati e utilizza i metadati del record per costruire i metadati che descrivono il set in questione.</span><span class="sxs-lookup"><span data-stu-id="319ab-129">It marks the beginning of a result set and uses the record metadata to construct the metadata that describes the result set.</span></span> <span data-ttu-id="319ab-130">Non invia il valore del record con `SendResultsStart`.</span><span class="sxs-lookup"><span data-stu-id="319ab-130">It does not send the value of the record with `SendResultsStart`.</span></span> <span data-ttu-id="319ab-131">Tutte le righe successive, inviate mediante il metodo `SendResultsRow`, dovranno corrispondere alla specifica definizione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="319ab-131">All the subsequent rows, sent using `SendResultsRow`, must match that metadata definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="319ab-132">Dopo la chiamata al metodo `SendResultsStart`, è possibile chiamare solo `SendResultsRow` e `SendResultsEnd`.</span><span class="sxs-lookup"><span data-stu-id="319ab-132">After calling the `SendResultsStart` method only `SendResultsRow` and `SendResultsEnd` can be called.</span></span> <span data-ttu-id="319ab-133">La chiamata di qualsiasi altro metodo nella stessa istanza di `SqlPipe` provoca una `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="319ab-133">Calling any other method in the same instance of `SqlPipe` causes an `InvalidOperationException`.</span></span> <span data-ttu-id="319ab-134">`SendResultsEnd` imposta `SqlPipe` di nuovo nello stato iniziale nel quale possono essere chiamati gli altri metodi.</span><span class="sxs-lookup"><span data-stu-id="319ab-134">`SendResultsEnd` sets `SqlPipe` back to the initial state in which other methods can be called.</span></span>  
  
### <a name="example"></a><span data-ttu-id="319ab-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="319ab-135">Example</span></span>  
 <span data-ttu-id="319ab-136">La stored procedure `uspGetProductLine` restituisce il nome, il numero di prodotto, il colore e il prezzo di listino di tutti i prodotti di una linea dei prodotti specificata.</span><span class="sxs-lookup"><span data-stu-id="319ab-136">The `uspGetProductLine` stored procedure returns the name, product number, color, and list price of all products within a specified product line.</span></span> <span data-ttu-id="319ab-137">Questo stored procedure accetta corrispondenze esatte per *prodLine*.</span><span class="sxs-lookup"><span data-stu-id="319ab-137">This stored procedure accepts exact matches for *prodLine*.</span></span>  
  
 <span data-ttu-id="319ab-138">C#</span><span class="sxs-lookup"><span data-stu-id="319ab-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspGetProductLine(SqlString prodLine)  
{  
    // Connect through the context connection.  
    using (SqlConnection connection = new SqlConnection("context connection=true"))  
    {  
        connection.Open();  
  
        SqlCommand command = new SqlCommand(  
            "SELECT Name, ProductNumber, Color, ListPrice " +  
            "FROM Production.Product " +   
            "WHERE ProductLine = @prodLine;", connection);  
  
        command.Parameters.AddWithValue("@prodLine", prodLine);  
  
        try  
        {  
            // Execute the command and send the results to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command);  
        }  
        catch (System.Data.SqlClient.SqlException ex)  
        {  
            // An error occurred executing the SQL command.  
        }  
     }  
}  
};  
```  
  
 <span data-ttu-id="319ab-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="319ab-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub uspGetProductLine(ByVal prodLine As SqlString)  
    Dim command As SqlCommand  
  
    ' Connect through the context connection.  
    Using connection As New SqlConnection("context connection=true")  
        connection.Open()  
  
        command = New SqlCommand( _  
        "SELECT Name, ProductNumber, Color, ListPrice " & _  
        "FROM Production.Product " & _  
        "WHERE ProductLine = @prodLine;", connection)  
        command.Parameters.AddWithValue("@prodLine", prodLine)  
  
        Try  
            ' Execute the command and send the results   
            ' directly to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command)  
        Catch ex As System.Data.SqlClient.SqlException  
            ' An error occurred executing the SQL command.  
        End Try  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="319ab-140">Nell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente viene eseguita la procedura `uspGetProduct` che restituisce un elenco di biciclette da passeggio.</span><span class="sxs-lookup"><span data-stu-id="319ab-140">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement executes the `uspGetProduct` procedure, which returns a list of touring bike products.</span></span>  
  
```  
EXEC uspGetProductLineVB 'T';  
```  
  
## <a name="see-also"></a><span data-ttu-id="319ab-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="319ab-141">See Also</span></span>  
 <span data-ttu-id="319ab-142">[Oggetto SqlDataRecord](sqldatarecord-object.md) </span><span class="sxs-lookup"><span data-stu-id="319ab-142">[SqlDataRecord Object](sqldatarecord-object.md) </span></span>  
 <span data-ttu-id="319ab-143">[Stored procedure CLR](../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="319ab-143">[CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="319ab-144">Estensioni specifiche in-process di SQL Server ad ADO.NET</span><span class="sxs-lookup"><span data-stu-id="319ab-144">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
