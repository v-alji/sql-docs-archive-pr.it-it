---
title: Creare trigger DML per gestire più righe di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- multiple row DML triggers
- UPDATE statement [SQL Server], DML triggers
- DELETE statement [SQL Server], DML triggers
- multirow DML triggers [SQL Server]
- INSERT statement [SQL Server], DML triggers
- DML triggers, multirow
ms.assetid: d476c124-596b-4b27-a883-812b6b50a735
author: rothja
ms.author: jroth
ms.openlocfilehash: 11ea7aa457a5cdfcafd4a8c4e0ac170ae0e3b9c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637152"
---
# <a name="create-dml-triggers-to-handle-multiple-rows-of-data"></a><span data-ttu-id="95ccd-102">Creazione di trigger DML per gestire più righe di dati</span><span class="sxs-lookup"><span data-stu-id="95ccd-102">Create DML Triggers to Handle Multiple Rows of Data</span></span>
  <span data-ttu-id="95ccd-103">Quando si scrive il codice di un trigger DML, è importante considerare che l'istruzione che attiva il trigger può essere singola e interessare più righe di dati, anziché una sola riga.</span><span class="sxs-lookup"><span data-stu-id="95ccd-103">When you write the code for a DML trigger, consider that the statement that causes the trigger to fire can be a single statement that affects multiple rows of data, instead of a single row.</span></span> <span data-ttu-id="95ccd-104">Questo funzionamento è comune per i trigger UPDATE e DELETE perché queste istruzioni in genere interessano più righe,</span><span class="sxs-lookup"><span data-stu-id="95ccd-104">This behavior is common for UPDATE and DELETE triggers because these statements frequently affect multiple rows.</span></span> <span data-ttu-id="95ccd-105">mentre è meno comune per i trigger INSERT perché l'istruzione INSERT di base aggiunge soltanto una riga singola.</span><span class="sxs-lookup"><span data-stu-id="95ccd-105">The behavior is less common for INSERT triggers because the basic INSERT statement adds only a single row.</span></span> <span data-ttu-id="95ccd-106">Dato però che un trigger INSERT può essere attivato da un'istruzione INSERT INTO (*table_name*) SELECT, l'inserimento di molte righe può causare la chiamata a un unico trigger.</span><span class="sxs-lookup"><span data-stu-id="95ccd-106">However, because an INSERT trigger can be fired by an INSERT INTO (*table_name*) SELECT statement, the insertion of many rows may cause a single trigger invocation.</span></span>  
  
 <span data-ttu-id="95ccd-107">Queste considerazioni sono di particolare importanza quando la funzione di un trigger DML consiste nel ricalcolare automaticamente i valori di riepilogo di una tabella e archiviare i risultati in un'altra tabella per i conteggi.</span><span class="sxs-lookup"><span data-stu-id="95ccd-107">Multirow considerations are especially important when the function of a DML trigger is to automatically recalculate summary values from one table and store the results in another for ongoing tallies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95ccd-108">Non è consigliabile utilizzare cursori nei trigger dato che possono potenzialmente ridurre le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="95ccd-108">We do not recommend using cursors in triggers because they could potentially reduce performance.</span></span> <span data-ttu-id="95ccd-109">Per progettare un trigger che interessa più righe, utilizzare una logica basata su set di righe invece che su cursori.</span><span class="sxs-lookup"><span data-stu-id="95ccd-109">To design a trigger that affects multiple rows, use rowset-based logic instead of cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="95ccd-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="95ccd-110">Examples</span></span>  
 <span data-ttu-id="95ccd-111">I trigger DML negli esempi seguenti sono progettati per archiviare il totale parziale di una colonna in un'altra tabella del database di esempio di [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95ccd-111">The DML triggers in the following examples are designed to store a running total of a column in another table of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
### <a name="a-storing-a-running-total-for-a-single-row-insert"></a><span data-ttu-id="95ccd-112">R.</span><span class="sxs-lookup"><span data-stu-id="95ccd-112">A.</span></span> <span data-ttu-id="95ccd-113">Archiviazione di un totale parziale per l'inserimento di una riga singola</span><span class="sxs-lookup"><span data-stu-id="95ccd-113">Storing a running total for a single-row insert</span></span>  
 <span data-ttu-id="95ccd-114">La prima versione del trigger DML funziona correttamente per l'inserimento di una singola riga, quando una riga di dati viene caricata nella tabella `PurchaseOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="95ccd-114">The first version of the DML trigger works well for a single-row insert when a row of data is loaded into the `PurchaseOrderDetail` table.</span></span> <span data-ttu-id="95ccd-115">Il trigger DML viene attivato da un'istruzione INSERT e la nuova riga viene caricata nella tabella **inserted** per la durata dell'esecuzione del trigger.</span><span class="sxs-lookup"><span data-stu-id="95ccd-115">An INSERT statement fires the DML trigger, and the new row is loaded into the **inserted** table for the duration of the trigger execution.</span></span> <span data-ttu-id="95ccd-116">L'istruzione `UPDATE` legge il valore della colonna `LineTotal` per la riga e lo aggiunge al valore esistente nella colonna `SubTotal` della tabella `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="95ccd-116">The `UPDATE` statement reads the `LineTotal` column value for the row and adds that value to the existing value in the `SubTotal` column in the `PurchaseOrderHeader` table.</span></span> <span data-ttu-id="95ccd-117">La clausola `WHERE` verifica che la riga aggiornata nella tabella `PurchaseOrderDetail` corrisponda al valore di `PurchaseOrderID` della riga nella tabella **inserted** .</span><span class="sxs-lookup"><span data-stu-id="95ccd-117">The `WHERE` clause makes sure that the updated row in the `PurchaseOrderDetail` table matches the `PurchaseOrderID` of the row in the **inserted** table.</span></span>  
  
```  
-- Trigger is valid for single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID ;  
```  
  
### <a name="b-storing-a-running-total-for-a-multirow-or-single-row-insert"></a><span data-ttu-id="95ccd-118">B.</span><span class="sxs-lookup"><span data-stu-id="95ccd-118">B.</span></span> <span data-ttu-id="95ccd-119">Archiviazione di un totale parziale per l'inserimento di una riga singola o di più righe</span><span class="sxs-lookup"><span data-stu-id="95ccd-119">Storing a running total for a multirow or single-row insert</span></span>  
 <span data-ttu-id="95ccd-120">Nel caso di un'istruzione che interessa più righe, il trigger DML dell'esempio A potrebbe non funzionare correttamente. Nell'espressione a destra di un'espressione di assegnazione in un'istruzione UPDATE (`SubTotal` + `LineTotal`) è possibile includere un valore singolo, non un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="95ccd-120">For a multirow insert, the DML trigger in example A might not operate correctly; the expression to the right of an assignment expression in an UPDATE statement (`SubTotal` + `LineTotal`) can be only a single value, not a list of values.</span></span> <span data-ttu-id="95ccd-121">L'effetto del trigger è quindi quello di recuperare un valore dalle righe singole della tabella **inserted** e aggiungerlo al valore esistente `SubTotal` nella tabella `PurchaseOrderHeader` per un determinato valore di `PurchaseOrderID` .</span><span class="sxs-lookup"><span data-stu-id="95ccd-121">Therefore, the effect of the trigger is to retrieve a value from any single row in the **inserted** table and add that value to the existing `SubTotal` value in the `PurchaseOrderHeader` table for a specific `PurchaseOrderID` value.</span></span> <span data-ttu-id="95ccd-122">L'effetto dell'operazione potrebbe non essere quello atteso se un singolo valore di `PurchaseOrderID` compare più volte nella tabella **inserted** .</span><span class="sxs-lookup"><span data-stu-id="95ccd-122">This operation might not have the expected effect if a single `PurchaseOrderID` value occurred more than one time in the **inserted** table.</span></span>  
  
 <span data-ttu-id="95ccd-123">Per aggiornare la tabella `PurchaseOrderHeader` correttamente, il trigger deve tener conto della possibile presenza di più righe nella tabella **inserted** .</span><span class="sxs-lookup"><span data-stu-id="95ccd-123">To correctly update the `PurchaseOrderHeader` table, the trigger must allow for the chance of multiple rows in the **inserted** table.</span></span> <span data-ttu-id="95ccd-124">Ciò può essere ottenuto utilizzando la funzione `SUM` per calcolare il valore `LineTotal` totale relativo a un gruppo di righe nella tabella **inserted** per ogni `PurchaseOrderID`.</span><span class="sxs-lookup"><span data-stu-id="95ccd-124">You can do this by using the `SUM` function that calculates the total `LineTotal` for a group of rows in the **inserted** table for each `PurchaseOrderID`.</span></span> <span data-ttu-id="95ccd-125">La funzione `SUM` viene inclusa in una sottoquery correlata (l'istruzione `SELECT` in parentesi).</span><span class="sxs-lookup"><span data-stu-id="95ccd-125">The `SUM` function is included in a correlated subquery (the `SELECT` statement in parentheses).</span></span> <span data-ttu-id="95ccd-126">Questa sottoquery restituisce un singolo valore per ogni `PurchaseOrderID` nella tabella **inserted** che corrisponde o è correlato a un valore `PurchaseOrderID` nella tabella `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="95ccd-126">This subquery returns a single value for each `PurchaseOrderID` in the **inserted** table that matches or is correlated with a `PurchaseOrderID` in the `PurchaseOrderHeader` table.</span></span>  
  
```  
-- Trigger is valid for multirow and single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail2  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted);  
```  
  
 <span data-ttu-id="95ccd-127">Questo trigger funziona inoltre correttamente per l'inserimento di una riga singola. La somma dei valori della colonna `LineTotal` corrisponde alla somma di una riga singola.</span><span class="sxs-lookup"><span data-stu-id="95ccd-127">This trigger also works correctly in a single-row insert; the sum of the `LineTotal` value column is the sum of a single row.</span></span> <span data-ttu-id="95ccd-128">Con questo trigger, tuttavia, la sottoquery correlata e l'operatore `IN` utilizzato nella clausola `WHERE` comportano un'ulteriore elaborazione in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="95ccd-128">However, with this trigger the correlated subquery and the `IN` operator that is used in the `WHERE` clause require additional processing from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="95ccd-129">non necessaria per l'inserimento di una riga singola.</span><span class="sxs-lookup"><span data-stu-id="95ccd-129">This is unnecessary for a single-row insert.</span></span>  
  
### <a name="c-storing-a-running-total-based-on-the-type-of-insert"></a><span data-ttu-id="95ccd-130">C.</span><span class="sxs-lookup"><span data-stu-id="95ccd-130">C.</span></span> <span data-ttu-id="95ccd-131">Archiviazione di un totale parziale sulla base del tipo di inserimento</span><span class="sxs-lookup"><span data-stu-id="95ccd-131">Storing a running total based on the type of insert</span></span>  
 <span data-ttu-id="95ccd-132">È possibile modificare il trigger per utilizzare il metodo ottimale in base al numero di righe.</span><span class="sxs-lookup"><span data-stu-id="95ccd-132">You can change the trigger to use the method optimal for the number of rows.</span></span> <span data-ttu-id="95ccd-133">È ad esempio possibile utilizzare la funzione `@@ROWCOUNT` nella logica del trigger per distinguere tra l'inserimento di una riga singola e di più righe.</span><span class="sxs-lookup"><span data-stu-id="95ccd-133">For example, the `@@ROWCOUNT` function can be used in the logic of the trigger to distinguish between a single and a multirow insert.</span></span>  
  
```  
-- Trigger valid for multirow and single row inserts  
-- and optimal for single row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail3  
ON Purchasing.PurchaseOrderDetail  
FOR INSERT AS  
IF @@ROWCOUNT = 1  
BEGIN  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
END  
ELSE  
BEGIN  
      UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted)  
END;  
```  
  
## <a name="see-also"></a><span data-ttu-id="95ccd-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95ccd-134">See Also</span></span>  
 [<span data-ttu-id="95ccd-135">Trigger DML</span><span class="sxs-lookup"><span data-stu-id="95ccd-135">DML Triggers</span></span>](dml-triggers.md)  
  
  
