---
title: Accesso alla transazione corrente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- current transaction access
- Current property
- Transaction class
ms.assetid: 1a4e2ce5-f627-4c81-8960-6a9968cefda2
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b7e67d30cb9d89a02eb918fcd03651b2915955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725983"
---
# <a name="accessing-the-current-transaction"></a><span data-ttu-id="94383-102">Accesso alla transazione corrente</span><span class="sxs-lookup"><span data-stu-id="94383-102">Accessing the Current Transaction</span></span>
  <span data-ttu-id="94383-103">Se una transazione è attiva quando viene immesso il codice CLT (Common Language Runtime) in esecuzione su [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la transazione viene esposta mediante la classe `System.Transactions.Transaction`.</span><span class="sxs-lookup"><span data-stu-id="94383-103">If a transaction is active at the point at which common language runtime (CLR) code running on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is entered, the transaction is exposed through the `System.Transactions.Transaction` class.</span></span> <span data-ttu-id="94383-104">Per accedere alla transazione corrente viene utilizzata la proprietà `Transaction.Current`.</span><span class="sxs-lookup"><span data-stu-id="94383-104">The `Transaction.Current` property is used to access the current transaction.</span></span> <span data-ttu-id="94383-105">Nella maggior parte dei casi non è necessario accedere in modo esplicito alla transazione.</span><span class="sxs-lookup"><span data-stu-id="94383-105">In most cases it is not necessary to access the transaction explicitly.</span></span> <span data-ttu-id="94383-106">Per le connessioni al database, ADO.NET controlla `Transaction.Current` automaticamente quando viene chiamato il metodo `Connection.Open` e integra in modo trasparente la connessione in tale transazione, a meno che la parola chiave `Enlist` non venga impostata su false nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="94383-106">For database connections, ADO.NET checks `Transaction.Current` automatically when the `Connection.Open` method is called, and transparently enlists the connection in that transaction (unless the `Enlist` keyword is set to false in the connection string).</span></span>  
  
 <span data-ttu-id="94383-107">Può essere necessario utilizzare direttamente l'oggetto `Transaction` negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="94383-107">You might want to use the `Transaction` object directly in the following scenarios:</span></span>  
  
-   <span data-ttu-id="94383-108">Se si desidera integrare una risorsa che non esegue l'integrazione automatica o che per qualche motivo non è stata integrata durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="94383-108">If you want to enlist a resource that does not do automatic enlistment, or that for some reason was not enlisted during initialization.</span></span>  
  
-   <span data-ttu-id="94383-109">Se si desidera integrare in modo esplicito una risorsa nella transazione.</span><span class="sxs-lookup"><span data-stu-id="94383-109">If you want to explicitly enlist a resource in the transaction.</span></span>  
  
-   <span data-ttu-id="94383-110">Se si desidera terminare la transazione esterna dalla stored procedure o dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="94383-110">If you want to terminate the external transaction from within your stored procedure or function.</span></span> <span data-ttu-id="94383-111">In questo caso, utilizzare <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="94383-111">In this case, you use <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="94383-112">Nel codice seguente, ad esempio, viene eseguito il rollback della transazione corrente:</span><span class="sxs-lookup"><span data-stu-id="94383-112">For example, the following code will rollback the current transaction:</span></span>  
  
    ```  
    using(TransactionScope transactionScope = new TransactionScope(TransactionScopeOptions.Required)) { }  
    ```  
  
 <span data-ttu-id="94383-113">Nella parte restante di questo argomento vengono descritte altre modalità di annullamento di una transazione esterna.</span><span class="sxs-lookup"><span data-stu-id="94383-113">The rest of this topic describes other ways to cancel an external transaction.</span></span>  
  
## <a name="canceling-an-external-transaction"></a><span data-ttu-id="94383-114">Annullamento di una transazione esterna</span><span class="sxs-lookup"><span data-stu-id="94383-114">Canceling an External Transaction</span></span>  
 <span data-ttu-id="94383-115">È possibile annullare le transazioni esterne da una funzione o procedura gestita nelle modalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="94383-115">You can cancel external transactions from a managed procedure or function in the following ways:</span></span>  
  
-   <span data-ttu-id="94383-116">La funzione o procedura gestita può restituire un valore utilizzando un parametro di output.</span><span class="sxs-lookup"><span data-stu-id="94383-116">The managed procedure or function can return a value by using an output parameter.</span></span> <span data-ttu-id="94383-117">La procedura [!INCLUDE[tsql](../../includes/tsql-md.md)] chiamante può controllare il valore restituito e, se necessario, eseguire `ROLLBACK TRANSACTION`.</span><span class="sxs-lookup"><span data-stu-id="94383-117">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can check the returned value and, if appropriate, execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="94383-118">La funzione o procedura gestita può generare un'eccezione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="94383-118">The managed procedure or function can throw a custom exception.</span></span> <span data-ttu-id="94383-119">La [!INCLUDE[tsql](../../includes/tsql-md.md)] procedura chiamante può intercettare l'eccezione generata dalla procedura o dalla funzione gestita in un blocco try/catch ed eseguire `ROLLBACK TRANSACTION` .</span><span class="sxs-lookup"><span data-stu-id="94383-119">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can catch the exception thrown by the managed procedure or function in a try/catch block and execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="94383-120">La funzione o procedura gestita può annullare la transazione corrente chiamando il metodo `Transaction.Rollback` se viene soddisfatta una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="94383-120">The managed procedure or function can cancel the current transaction by calling the `Transaction.Rollback` method if a certain condition is met.</span></span>  
  
 <span data-ttu-id="94383-121">Quando viene chiamato all'interno di una funzione o procedura gestita, il metodo `Transaction.Rollback` genera un'eccezione con un messaggio di errore ambiguo e può essere incluso in un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="94383-121">When it is called within a managed procedure or function, the `Transaction.Rollback` method throws an exception with an ambiguous error message and can be wrapped in a try/catch block.</span></span> <span data-ttu-id="94383-122">Il messaggio di errore è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="94383-122">The error message thresembles similar to the following:</span></span>  
  
```  
Msg 3994, Level 16, State 1, Procedure uspRollbackFromProc, Line 0  
Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting.  
```  
  
 <span data-ttu-id="94383-123">Questa eccezione è prevista e il blocco try/catch è necessario per continuare a eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="94383-123">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="94383-124">Senza il blocco try/catch, l'eccezione verrà generata immediatamente per la procedura [!INCLUDE[tsql](../../includes/tsql-md.md)] chiamante e l'esecuzione del codice gestito verrà terminata.</span><span class="sxs-lookup"><span data-stu-id="94383-124">Without the try/catch block, the exception will be immediately thrown to the calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure and managed code execution will finish.</span></span> <span data-ttu-id="94383-125">Al termine dell'esecuzione del codice gestito, viene generata un'altra eccezione:</span><span class="sxs-lookup"><span data-stu-id="94383-125">When the managed code finishes execution, another exception is raised:</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure uspRollbackFromProc, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate " uspRollbackFromProc " has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting. The statement has been terminated.  
```  
  
 <span data-ttu-id="94383-126">Anche questa eccezione è prevista e, per continuare l'esecuzione è necessario un blocco try/catch intorno all'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] che esegue l'azione che attiva il trigger.</span><span class="sxs-lookup"><span data-stu-id="94383-126">This exception is also expected, and for execution to continue, you must have a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger.</span></span> <span data-ttu-id="94383-127">Nonostante le due eccezioni generate, viene eseguito il rollback della transazione e le modifiche non vengono sottoposte a commit.</span><span class="sxs-lookup"><span data-stu-id="94383-127">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed.</span></span>  
  
### <a name="example"></a><span data-ttu-id="94383-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="94383-128">Example</span></span>  
 <span data-ttu-id="94383-129">Di seguito è riportato un esempio di transazione sottoposta a rollback da una procedura gestita mediante il metodo `Transaction.Rollback`.</span><span class="sxs-lookup"><span data-stu-id="94383-129">The following is an example of a transaction being rolled back from a managed procedure by using the `Transaction.Rollback` method.</span></span> <span data-ttu-id="94383-130">Si noti il blocco try/catch intorno al metodo `Transaction.Rollback` nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="94383-130">Notice the try/catch block around the `Transaction.Rollback` method in the managed code.</span></span> <span data-ttu-id="94383-131">Lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] crea un assembly e una stored procedure gestita.</span><span class="sxs-lookup"><span data-stu-id="94383-131">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates an assembly and managed stored procedure.</span></span> <span data-ttu-id="94383-132">Tenere presente che l' `EXEC uspRollbackFromProc` istruzione viene sottoposta a incapsulamento in un blocco try/catch, in modo che venga rilevata l'eccezione generata al termine dell'esecuzione della procedura gestita.</span><span class="sxs-lookup"><span data-stu-id="94383-132">Be aware that the `EXEC uspRollbackFromProc` statement is wrapped in a try/catch block, so that the exception thrown when the managed procedure completes execution is caught.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspRollbackFromProc()  
{  
   using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
   {  
      // Open the connection.  
      connection.Open();  
  
      bool successCondition = true;  
  
      // Success condition is met.  
      if (successCondition)  
      {  
         SqlContext.Pipe.Send("Success condition met in procedure.");   
         // Perform other actions here.  
      }  
  
      //  Success condition is not met, the transaction will be rolled back.  
      else  
      {  
         SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...");  
         try  
         {  
               // Get the current transaction and roll it back.  
               Transaction trans = Transaction.Current;  
               trans.Rollback();  
         }  
         catch (SqlException ex)  
         {  
            // Catch the expected exception.   
            // This allows the connection to close correctly.                      
         }    
      }  
  
      // Close the connection.  
      connection.Close();  
   }  
}  
};  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  uspRollbackFromProc ()  
   Using connection As New SqlConnection("context connection=true")  
  
   ' Open the connection.  
   connection.Open()  
  
   Dim successCondition As Boolean  
   successCondition = False  
  
   ' Success condition is met.  
   If successCondition Then  
  
      SqlContext.Pipe.Send("Success condition met in procedure.")  
  
      ' Success condition is not met, the transaction will be rolled back.  
  
   Else  
      SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...")  
      Try  
         ' Get the current transaction and roll it back.  
         Dim trans As Transaction  
         trans = Transaction.Current  
         trans.Rollback()  
  
      Catch ex As SqlException  
         ' Catch the exception instead of throwing it.    
         ' This allows the connection to close correctly.                      
      End Try  
  
   End If  
  
   ' Close the connection.  
   connection.Close()  
  
End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="94383-133">**Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="94383-133">**Transact-SQL**</span></span>  
  
```  
--Register assembly.  
CREATE ASSEMBLY TestProcs FROM 'C:\Programming\TestProcs.dll'   
Go  
CREATE PROCEDURE uspRollbackFromProc AS EXTERNAL NAME TestProcs.StoredProcedures.uspRollbackFromProc  
Go  
  
-- Execute procedure.  
BEGIN TRY  
BEGIN TRANSACTION   
-- Perform other actions.  
Exec uspRollbackFromProc  
-- Perform other actions.  
PRINT N'Commiting transaction...'  
COMMIT TRANSACTION  
END TRY  
  
BEGIN CATCH  
SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
PRINT N'Exception thrown, rolling back transaction.'  
ROLLBACK TRANSACTION  
PRINT N'Transaction rolled back.'   
END CATCH  
Go  
  
-- Clean up.  
DROP Procedure uspRollbackFromProc;  
Go  
DROP ASSEMBLY TestProcs;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="94383-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94383-134">See Also</span></span>  
 [<span data-ttu-id="94383-135">Integrazione con CLR e transazioni</span><span class="sxs-lookup"><span data-stu-id="94383-135">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
