---
title: Utilizzo di System. Transactions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TransactionScope class
- Dispose method
- System.Transactions namespace
ms.assetid: 79656ce5-ce46-4c5e-9540-cf9869bd774b
author: rothja
ms.author: jroth
ms.openlocfilehash: 277edd75ea0437dc532ed5672e3c7b8a0569af8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725964"
---
# <a name="using-systemtransactions"></a><span data-ttu-id="a3a93-102">Utilizzo di System.Transactions</span><span class="sxs-lookup"><span data-stu-id="a3a93-102">Using System.Transactions</span></span>
  <span data-ttu-id="a3a93-103">Tramite lo spazio dei nomi `System.Transactions` vengono forniti un framework di transazioni pienamente integrato con ADO.NET e l'integrazione con CRL di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3a93-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="a3a93-104">La classe `System.Transactions.TransactionScope` rende transazionale un blocco di codice attraverso un'integrazione implicita delle connessioni in una transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="a3a93-104">The `System.Transactions.TransactionScope` class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="a3a93-105">È necessario chiamare il metodo `Complete` alla fine del blocco di codice contrassegnato da `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-105">You must call the `Complete` method at the end of the code block marked by the `TransactionScope`.</span></span> <span data-ttu-id="a3a93-106">Il metodo `Dispose` viene richiamato quando l'esecuzione del programma lascia un blocco di codice. Se il metodo `Complete` non viene chiamato, la transazione non viene più utilizzata.</span><span class="sxs-lookup"><span data-stu-id="a3a93-106">The `Dispose` method is invoked when program execution leaves a code block, causing the transaction to be discontinued if the `Complete` method is not called.</span></span> <span data-ttu-id="a3a93-107">Se è stata generata un'eccezione che determina l'uscita del codice dall'ambito, la transazione non viene più utilizzata.</span><span class="sxs-lookup"><span data-stu-id="a3a93-107">If an exception has been thrown that causes the code to leave scope, the transaction is considered to be discontinued.</span></span>  
  
 <span data-ttu-id="a3a93-108">È consigliabile utilizzare un blocco `using` per far sì che il metodo `Dispose` venga chiamato sull'oggetto `TransactionScope` al termine del blocco `using`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-108">We recommend that you employ a `using` block to ensure that the `Dispose` method is called on the `TransactionScope` object when the `using` block is exited.</span></span> <span data-ttu-id="a3a93-109">L'impossibilità di eseguire il commit o il rollback delle transazioni in sospeso può compromettere notevolmente le prestazioni in quanto il timeout predefinito per `TransactionScope` è pari a un minuto.</span><span class="sxs-lookup"><span data-stu-id="a3a93-109">Failure to commit or roll back pending transactions can seriously degrade performance because the default time-out for the `TransactionScope` is one minute.</span></span> <span data-ttu-id="a3a93-110">Se non si utilizza un'istruzione `using`, è necessario eseguire tutto il lavoro in un blocco `Try` e chiamare in modo esplicito il metodo `Dispose` all'interno del blocco `Finally`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-110">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the `Dispose` method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="a3a93-111">Se si verifica un'eccezione all'interno di `TransactionScope`, la transazione viene contrassegnata come incoerente e quindi abbandonata.</span><span class="sxs-lookup"><span data-stu-id="a3a93-111">If an exception occurs within the `TransactionScope`, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="a3a93-112">Ne viene eseguito il rollback all'eliminazione di `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-112">It is rolled back when the `TransactionScope` is disposed.</span></span> <span data-ttu-id="a3a93-113">Se non si verifica alcuna eccezione, viene eseguito il commit delle transazioni partecipanti.</span><span class="sxs-lookup"><span data-stu-id="a3a93-113">If no exception occurs, participating transactions commit.</span></span>  
  
 <span data-ttu-id="a3a93-114">È opportuno utilizzare `TransactionScope` solo quando si accede a origini dati locali e remote o a gestori di risorse esterni in quanto</span><span class="sxs-lookup"><span data-stu-id="a3a93-114">`TransactionScope` should be used only when local and remote data sources or external resource managers are being accessed.</span></span> <span data-ttu-id="a3a93-115">Questo perché `TransactionScope` causa sempre l'innalzamento di livello delle transazioni, anche se viene utilizzato solo all'interno di una connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="a3a93-115">This is because `TransactionScope` always causes transactions to promote, even if it is being used only within a context connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3a93-116">Per impostazione predefinita, la classe `TransactionScope` crea una transazione con un `System.Transactions.Transaction.IsolationLevel` di `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-116">The `TransactionScope` class creates a transaction with a `System.Transactions.Transaction.IsolationLevel` of `Serializable` by default.</span></span> <span data-ttu-id="a3a93-117">A seconda dell'applicazione, è possibile abbassare il livello di isolamento per evitare che si verifichi un numero elevato di contese.</span><span class="sxs-lookup"><span data-stu-id="a3a93-117">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3a93-118">È consigliabile eseguire solo aggiornamenti, inserimenti ed eliminazioni all'interno di transazioni distribuite sui server remoti in quanto tali operazioni comportano un notevole consumo di risorse del database.</span><span class="sxs-lookup"><span data-stu-id="a3a93-118">We recommend that you perform only updates, inserts, and deletes within distributed transactions against remote servers because they consume significant database resources.</span></span> <span data-ttu-id="a3a93-119">Se l'operazione viene effettuata sul server locale, non è necessario eseguire una transazione distribuita ed è sufficiente una transazione locale.</span><span class="sxs-lookup"><span data-stu-id="a3a93-119">If the operation is going to be performed on the local server, a distributed transaction is not necessary and a local transaction will suffice.</span></span> <span data-ttu-id="a3a93-120">Le istruzioni SELECT potrebbero bloccare inutilmente risorse del database e in alcuni scenari può essere necessario utilizzare le transazioni per le operazioni di selezione.</span><span class="sxs-lookup"><span data-stu-id="a3a93-120">SELECT statements may lock database resources unnecessarily, and in some scenarios it may be necessary to use transactions for selects.</span></span> <span data-ttu-id="a3a93-121">Tutto il lavoro che non riguarda il database deve essere svolto all'esterno dell'ambito della transazione, a meno che non coinvolga altri gestori di risorse inclusi nella transazione.</span><span class="sxs-lookup"><span data-stu-id="a3a93-121">Any non-database work should be done outside of the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="a3a93-122">Sebbene un'eccezione all'interno dell'ambito della transazione impedisca il commit di quest'ultima, la classe `TransactionScope` non consente di eseguire il rollback delle modifiche apportate al codice all'esterno dell'ambito della transazione stessa.</span><span class="sxs-lookup"><span data-stu-id="a3a93-122">Although an exception within the scope of the transaction prevents the transaction from committing, the `TransactionScope` class has no provision for rolling back any changes your code has made outside of the scope of the transaction itself.</span></span> <span data-ttu-id="a3a93-123">Per intraprendere qualche azione durante il rollback della transazione, è necessario scrivere un'implementazione personalizzata dell'interfaccia `System.Transactions.IEnlistmentNotification` ed integrarla esplicitamente nella transazione.</span><span class="sxs-lookup"><span data-stu-id="a3a93-123">If you need to take some action when the transaction is rolled back, you must write your own implementation of the `System.Transactions.IEnlistmentNotification` interface, and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3a93-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3a93-124">Example</span></span>  
 <span data-ttu-id="a3a93-125">Per utilizzare `System.Transactions`, è necessario disporre di un riferimento al file System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="a3a93-125">To work with `System.Transactions`, you must have a reference to the System.Transactions.dll file.</span></span>  
  
 <span data-ttu-id="a3a93-126">Nel codice seguente viene illustrato come creare una transazione che può essere promossa su due istanze diverse di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3a93-126">The following code demonstrates how to create a transaction that can be promoted against two different instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a3a93-127">Queste istanze vengono rappresentate da due oggetti `System.Data.SqlClient.SqlConnection` diversi, di cui viene eseguito il wrapping in un blocco `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-127">These instances are represented by two different `System.Data.SqlClient.SqlConnection` objects, which are wrapped in a `TransactionScope` block.</span></span> <span data-ttu-id="a3a93-128">Il codice crea il blocco `TransactionScope` con un'istruzione `using` e apre la prima connessione, che comporta un'integrazione automatica in `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-128">The code creates the `TransactionScope` block with a `using` statement, and opens the first connection, which automatically enlists it in the `TransactionScope`.</span></span> <span data-ttu-id="a3a93-129">La transazione viene integrata inizialmente come transazione lightweight, non come transazione completamente distribuita.</span><span class="sxs-lookup"><span data-stu-id="a3a93-129">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="a3a93-130">Il codice presuppone l'esistenza della logica condizionale, omessa per brevità.</span><span class="sxs-lookup"><span data-stu-id="a3a93-130">The code assumes the existence of conditional logic (which has been omitted for brevity).</span></span> <span data-ttu-id="a3a93-131">Apre la seconda connessione solo se necessario, integrandola in `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-131">It opens the second connection only if it is needed, enlisting it in the `TransactionScope`.</span></span> <span data-ttu-id="a3a93-132">Quando la connessione è aperta, la transazione viene promossa automaticamente a una transazione completamente distribuita.</span><span class="sxs-lookup"><span data-stu-id="a3a93-132">When the connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="a3a93-133">Il codice quindi richiama `TransactionScope.Complete`, che esegue il commit della transazione,</span><span class="sxs-lookup"><span data-stu-id="a3a93-133">The code then invokes `TransactionScope.Complete`, which commits the transaction.</span></span> <span data-ttu-id="a3a93-134">ed elimina le due connessioni al termine delle istruzioni `using` per le connessioni.</span><span class="sxs-lookup"><span data-stu-id="a3a93-134">The code disposes of the two connections when exiting the `using` statements for the connections.</span></span> <span data-ttu-id="a3a93-135">Il metodo `TransactionScope.Dispose` per `TransactionScope` viene chiamato automaticamente al termine del blocco `using` per `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-135">The `TransactionScope.Dispose` method for the `TransactionScope` is automatically called at the termination of the `using` block for the `TransactionScope`.</span></span> <span data-ttu-id="a3a93-136">Se in un punto qualsiasi del blocco `TransactionScope` è stata generata un'eccezione, `Complete` non viene chiamato e viene eseguito il rollback della transazione distribuita al momento dell'eliminazione di `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="a3a93-136">If an exception has been thrown at any point in the `TransactionScope` block, `Complete` does not get called, and the distributed transaction will roll back when the `TransactionScope` is disposed.</span></span>  
  
 <span data-ttu-id="a3a93-137">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3a93-137">Visual Basic</span></span>  
  
```  
Using transScope As New TransactionScope()  
    Using connection1 As New SqlConnection(connectString1)  
        ' Opening connection1 automatically enlists it in the   
        ' TransactionScope as a lightweight transaction.  
        connection1.Open()  
  
        ' Do work in the first connection.  
  
        ' Assumes conditional logic in place where the second  
        ' connection will only be opened as needed.  
        Using connection2 As New SqlConnection(connectString2)  
            ' Open the second connection, which enlists the   
            ' second connection and promotes the transaction to  
            ' a full distributed transaction.  
            connection2.Open()  
  
            ' Do work in the second connection.  
  
        End Using  
    End Using  
  
    ' Commit the transaction.  
    transScope.Complete()  
End Using  
```  
  
 <span data-ttu-id="a3a93-138">C#</span><span class="sxs-lookup"><span data-stu-id="a3a93-138">C#</span></span>  
  
```  
using (TransactionScope transScope = new TransactionScope())  
{  
    using (SqlConnection connection1 = new   
       SqlConnection(connectString1))  
    {  
        // Opening connection1 automatically enlists it in the   
        // TransactionScope as a lightweight transaction.  
        connection1.Open();  
  
        // Do work in the first connection.  
  
        // Assumes conditional logic in place where the second  
        // connection will only be opened as needed.  
        using (SqlConnection connection2 = new   
            SqlConnection(connectString2))  
        {  
            // Open the second connection, which enlists the   
            // second connection and promotes the transaction to  
            // a full distributed transaction.   
            connection2.Open();  
  
            // Do work in the second connection.  
        }  
    }  
    //  The Complete method commits the transaction.  
    transScope.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3a93-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3a93-139">See Also</span></span>  
 [<span data-ttu-id="a3a93-140">Integrazione con CLR e transazioni</span><span class="sxs-lookup"><span data-stu-id="a3a93-140">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
