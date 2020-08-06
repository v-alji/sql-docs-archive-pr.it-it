---
title: Implementazione di IDENTITY in una tabella con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c0a704a3-3a31-4c2c-b967-addacda62ef8
author: rothja
ms.author: jroth
ms.openlocfilehash: 955f9f1a905a9d0c71304320f60abe300e430e4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627266"
---
# <a name="implementing-identity-in-a-memory-optimized-table"></a><span data-ttu-id="b10ce-102">Implementazione di IDENTITY in una tabella con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="b10ce-102">Implementing IDENTITY in a Memory-Optimized Table</span></span>
  <span data-ttu-id="b10ce-103">IDENTITY(1, 1) è supportato in una tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b10ce-103">IDENTITY(1, 1) is supported on a memory-optimized table.</span></span> <span data-ttu-id="b10ce-104">Tuttavia, le colonne Identity con la definizione di IDENTITY(x, y) dove x != 1 o y != 1 non sono supportate nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b10ce-104">However, identity columns with definition of IDENTITY(x, y) where x != 1 or y != 1 are not supported on memory-optimized tables.</span></span> <span data-ttu-id="b10ce-105">La soluzione alternativa per i valori IDENTITY usa l'oggetto sequenza ([numeri di sequenza](../sequence-numbers/sequence-numbers.md)).</span><span class="sxs-lookup"><span data-stu-id="b10ce-105">The workaround for IDENTITY values uses the SEQUENCE object ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span></span>  
  
 <span data-ttu-id="b10ce-106">Rimuovere innanzitutto la proprietà IDENTITY della tabella che si converte in OLTP in memoria.</span><span class="sxs-lookup"><span data-stu-id="b10ce-106">First remove the IDENTITY property from the table you are converting to In-Memory OLTP.</span></span> <span data-ttu-id="b10ce-107">Quindi, definire un nuovo oggetto SEQUENCE per la colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="b10ce-107">Then, define a new SEQUENCE object for the column in the table.</span></span> <span data-ttu-id="b10ce-108">Gli oggetti SEQUENCE come le colonne IDENTITY possono creare valori DEFAULT per le colonne che utilizzano la sintassi NEXT VALUE FOR per ottenere un nuovo valore IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="b10ce-108">SEQUENCE objects as identity columns rely on the ability to create DEFAULT values for columns that use the NEXT VALUE FOR syntax to get a new identity value.</span></span> <span data-ttu-id="b10ce-109">Poiché i valori DEFAULT non sono supportati in OLTP in memoria, è necessario passare il valore SEQUENCE appena generato all'istruzione INSERT o a una stored procedure compilata in modo nativo che esegue l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="b10ce-109">Since DEFAULTs are not supported in In-Memory OLTP, you need to pass the newly-generated SEQUENCE value either to the INSERT statement or to a natively compiled stored procedure that does the insert.</span></span> <span data-ttu-id="b10ce-110">Nell'esempio seguente viene illustrato questo modello.</span><span class="sxs-lookup"><span data-stu-id="b10ce-110">The following example demonstrates this pattern.</span></span>  
  
```sql  
-- Create a new In-Memory OLTP table to simulate IDENTITY insert  
-- Here the column C1 was the identity column in the original table  
--  
create table T1  
(  
  
[c1] integer not null primary key T1_c1 nonclustered,  
[c2] varchar(32) not null,  
[c3] datetime not null  
  
) with (memory_optimized = on)  
go  
  
-- This is a sequence provider that will give us values for column [c1]  
--  
create sequence usq_SequenceForT1 as integer start with 2 increment by 1  
go  
  
--   insert a sample row using the sequence  
--   note that a new value needs to be retrieved form   
--   the sequence object for every insert  
--  
declare @c1 integer = next value for [dbo].[usq_SequenceForT1]  
insert into T1 values (@c1, 'test', getdate())  
```  
  
 <span data-ttu-id="b10ce-111">Dopo aver eseguito l'inserimento più volte, nella colonna [c1] vengono visualizzati valori validi a incremento progressivo costante.</span><span class="sxs-lookup"><span data-stu-id="b10ce-111">After performing the insert several times, you see valid monotonically increasing values in column [c1].</span></span> <span data-ttu-id="b10ce-112">Questo set di risultati viene generato utilizzando la scansione della tabella e l'indice hash senza `ORDER BY` e quindi le righe non vengono ordinate.</span><span class="sxs-lookup"><span data-stu-id="b10ce-112">This result set is generated using table scan and hash index without `ORDER BY` so the rows are not ordered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b10ce-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b10ce-113">See Also</span></span>  
 [<span data-ttu-id="b10ce-114">Migrazione a OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="b10ce-114">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
