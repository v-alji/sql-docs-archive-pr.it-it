---
title: Numeri di sequenza | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sequence number object, overview
- sequence [Database Engine]
- autonumbers, sequences
- sequence numbers [SQL Server]
- sequence number object
ms.assetid: c900e30d-2fd3-4d5f-98ee-7832f37e79d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6c65b4df915a85cf0ec7c7c0c8c0ff9f6607ad96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725367"
---
# <a name="sequence-numbers"></a><span data-ttu-id="560a3-102">Numeri di sequenza</span><span class="sxs-lookup"><span data-stu-id="560a3-102">Sequence Numbers</span></span>
  <span data-ttu-id="560a3-103">Una sequenza è un oggetto associato a schema definito dall'utente che genera una sequenza di valori numerici in base alla specifica con la quale è stata creata la sequenza.</span><span class="sxs-lookup"><span data-stu-id="560a3-103">A sequence is a user-defined schema-bound object that generates a sequence of numeric values according to the specification with which the sequence was created.</span></span> <span data-ttu-id="560a3-104">La sequenza di valori numerici viene generata in ordine crescente o decrescente a un intervallo definito e può essere ripetuta (ciclicamente) in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="560a3-104">The sequence of numeric values is generated in an ascending or descending order at a defined interval and may cycle (repeat) as requested.</span></span> <span data-ttu-id="560a3-105">Le sequenze, a differenza delle colonne di identità, non sono associate a tabelle.</span><span class="sxs-lookup"><span data-stu-id="560a3-105">Sequences, unlike identity columns, are not associated with tables.</span></span> <span data-ttu-id="560a3-106">In un'applicazione viene fatto riferimento a un oggetto sequenza per recuperare il relativo valore successivo.</span><span class="sxs-lookup"><span data-stu-id="560a3-106">An application refers to a sequence object to receive its next value.</span></span> <span data-ttu-id="560a3-107">La relazione tra sequenze e tabelle è controllata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="560a3-107">The relationship between sequences and tables is controlled by the application.</span></span> <span data-ttu-id="560a3-108">È possibile che nelle applicazioni utente si faccia riferimento a un oggetto sequenza e vengano coordinate le chiavi dei valori di più righe e tabelle.</span><span class="sxs-lookup"><span data-stu-id="560a3-108">User applications can reference a sequence object and coordinate the values keys across multiple rows and tables.</span></span>  
  
 <span data-ttu-id="560a3-109">Una sequenza viene creata indipendentemente delle tabelle usando l'istruzione **CREATE SEQUENCE** .</span><span class="sxs-lookup"><span data-stu-id="560a3-109">A sequence is created independently of the tables by using the **CREATE SEQUENCE** statement.</span></span> <span data-ttu-id="560a3-110">Le opzioni consentono di controllare i valori di incremento, massimo e minimo, il punto iniziale, la funzionalità di riavvio automatico e la memorizzazione nella cache per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="560a3-110">Options enable you to control the increment, maximum and minimum values, starting point, automatic restarting capability, and caching to improve performance.</span></span> <span data-ttu-id="560a3-111">Per informazioni sulle opzioni, vedere [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="560a3-111">For information about the options, see [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span></span>  
  
 <span data-ttu-id="560a3-112">A differenza dei valori delle colonne di identità, che vengono generati quando si inseriscono righe, un'applicazione può ottenere il numero di sequenza successivo prima di inserire la riga chiamando la funzione [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="560a3-112">Unlike identity column values, which are generated when rows are inserted, an application can obtain the next sequence number before inserting the row by calling the [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) function.</span></span> <span data-ttu-id="560a3-113">Il numero di sequenza viene allocato quando viene chiamata tale funzione, anche se il numero non viene mai inserito in una tabella.</span><span class="sxs-lookup"><span data-stu-id="560a3-113">The sequence number is allocated when NEXT VALUE FOR is called even if the number is never inserted into a table.</span></span> <span data-ttu-id="560a3-114">La funzione NEXT VALUE FOR può essere utilizzata come valore predefinito per una colonna in una definizione della tabella.</span><span class="sxs-lookup"><span data-stu-id="560a3-114">The NEXT VALUE FOR function can be used as the default value for a column in a table definition.</span></span> <span data-ttu-id="560a3-115">Usare [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) per ottenere un intervallo di numeri di sequenza.</span><span class="sxs-lookup"><span data-stu-id="560a3-115">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) to get a range of multiple sequence numbers at once.</span></span>  
  
 <span data-ttu-id="560a3-116">Una sequenza può essere definita come qualsiasi tipo di dati integer.</span><span class="sxs-lookup"><span data-stu-id="560a3-116">A sequence can be defined as any integer data type.</span></span> <span data-ttu-id="560a3-117">Se il tipo di dati non viene specificato, viene utilizzata per impostazione predefinita la sequenza `bigint`.</span><span class="sxs-lookup"><span data-stu-id="560a3-117">If the data type is not specified, a sequence defaults to `bigint`.</span></span>  
  
## <a name="using-sequences"></a><span data-ttu-id="560a3-118">Utilizzo di sequenze</span><span class="sxs-lookup"><span data-stu-id="560a3-118">Using Sequences</span></span>  
 <span data-ttu-id="560a3-119">Utilizzare sequenze anziché colonne di identità negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="560a3-119">Use sequences instead of identity columns in the following scenarios:</span></span>  
  
-   <span data-ttu-id="560a3-120">Nell'applicazione è richiesto un numero prima che venga effettuato l'inserimento nella tabella.</span><span class="sxs-lookup"><span data-stu-id="560a3-120">The application requires a number before the insert into the table is made.</span></span>  
  
-   <span data-ttu-id="560a3-121">Nell'applicazione è richiesta la condivisione di una singola serie di numeri tra più tabelle o più colonne all'interno di una tabella.</span><span class="sxs-lookup"><span data-stu-id="560a3-121">The application requires sharing a single series of numbers between multiple tables or multiple columns within a table.</span></span>  
  
-   <span data-ttu-id="560a3-122">Nell'applicazione deve essere riavviata la serie di numeri quando viene raggiunto un numero specificato.</span><span class="sxs-lookup"><span data-stu-id="560a3-122">The application must restart the number series when a specified number is reached.</span></span> <span data-ttu-id="560a3-123">Dopo che sono stati assegnati valori da 1 a 10, ad esempio, viene iniziata di nuovo l'assegnazione di valori da 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="560a3-123">For example, after assigning values 1 through 10, the application starts assigning values 1 through 10 again.</span></span>  
  
-   <span data-ttu-id="560a3-124">Nell'applicazione è richiesto l'ordinamento dei valori di sequenza in base a un altro campo.</span><span class="sxs-lookup"><span data-stu-id="560a3-124">The application requires sequence values to be sorted by another field.</span></span> <span data-ttu-id="560a3-125">Dalla funzione NEXT VALUE FOR può essere applicata la clausola OVER alla chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="560a3-125">The NEXT VALUE FOR function can apply the OVER clause to the function call.</span></span> <span data-ttu-id="560a3-126">La clausola OVER garantisce che i valori restituiti vengano generati in base all'ordine della clausola ORDER BY della clausola OVER.</span><span class="sxs-lookup"><span data-stu-id="560a3-126">The OVER clause guarantees that the values returned are generated in the order of the OVER clause's ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="560a3-127">In un'applicazione è richiesta l'assegnazione contemporanea di più numeri.</span><span class="sxs-lookup"><span data-stu-id="560a3-127">An application requires multiple numbers to be assigned at the same time.</span></span> <span data-ttu-id="560a3-128">Devono essere riservati, ad esempio, cinque numeri sequenziali.</span><span class="sxs-lookup"><span data-stu-id="560a3-128">For example, an application needs to reserve five sequential numbers.</span></span> <span data-ttu-id="560a3-129">La richiesta di valori di identità potrebbe comportare gap nella serie se sono stati emessi contemporaneamente numeri per altri processi.</span><span class="sxs-lookup"><span data-stu-id="560a3-129">Requesting identity values could result in gaps in the series if other processes were simultaneously issued numbers.</span></span> <span data-ttu-id="560a3-130">Una chiamata a sp_sequence_get_range consente di recuperare contemporaneamente diversi numeri della sequenza.</span><span class="sxs-lookup"><span data-stu-id="560a3-130">Calling sp_sequence_get_range can retrieve several numbers in the sequence at once.</span></span>  
  
-   <span data-ttu-id="560a3-131">È necessario modificare la specifica della sequenza, ad esempio il valore di incremento.</span><span class="sxs-lookup"><span data-stu-id="560a3-131">You need to change the specification of the sequence, such as the increment value.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="560a3-132">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="560a3-132">Limitations</span></span>  
 <span data-ttu-id="560a3-133">A differenza delle colonne di identità, i cui valori non possono essere modificati, i valori di sequenza non sono protetti automaticamente dopo l'inserimento nella tabella.</span><span class="sxs-lookup"><span data-stu-id="560a3-133">Unlike identity columns, whose values cannot be changed, sequence values are not automatically protected after insertion into the table.</span></span> <span data-ttu-id="560a3-134">Per evitare la modifica dei valori di sequenza, utilizzare un trigger di aggiornamento sulla tabella per eseguire il rollback delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="560a3-134">To prevent sequence values from being changed, use an update trigger on the table to roll back changes.</span></span>  
  
 <span data-ttu-id="560a3-135">L'univocità non viene applicata automaticamente per i valori di sequenza.</span><span class="sxs-lookup"><span data-stu-id="560a3-135">Uniqueness is not automatically enforced for sequence values.</span></span> <span data-ttu-id="560a3-136">Da progettazione, i valori di sequenza possono essere riutilizzati.</span><span class="sxs-lookup"><span data-stu-id="560a3-136">The ability to reuse sequence values is by design.</span></span> <span data-ttu-id="560a3-137">Se è necessario che i valori di sequenza in una tabella siano univoci, creare un indice univoco nella colonna.</span><span class="sxs-lookup"><span data-stu-id="560a3-137">If sequence values in a table are required to be unique, create a unique index on the column.</span></span> <span data-ttu-id="560a3-138">Se è necessario che i valori di sequenza in una tabella siano univoci per un gruppo di tabelle, creare trigger per impedire duplicati a causa di istruzioni di aggiornamento o ripetizione di numeri di sequenza.</span><span class="sxs-lookup"><span data-stu-id="560a3-138">If sequence values in a table are required to be unique throughout a group of tables, create triggers to prevent duplicates caused by update statements or sequence number cycling.</span></span>  
  
 <span data-ttu-id="560a3-139">L'oggetto sequenza genera numeri in base alla definizione, ma non controlla come vengono utilizzati i numeri.</span><span class="sxs-lookup"><span data-stu-id="560a3-139">The sequence object generates numbers according to its definition, but the sequence object does not control how the numbers are used.</span></span> <span data-ttu-id="560a3-140">Nei numeri di sequenza inseriti in una tabella possono essere presenti gap quando viene eseguito il rollback di una transazione, quando un oggetto sequenza è condiviso da più tabelle o quando i numeri di sequenza vengono allocati senza essere utilizzati nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="560a3-140">Sequence numbers inserted into a table can have gaps when a transaction is rolled back, when a sequence object is shared by multiple tables, or when sequence numbers are allocated without using them in tables.</span></span> <span data-ttu-id="560a3-141">In caso di creazione con l'opzione CACHE, un arresto imprevisto quale un'interruzione dell'alimentazione, può provocare la perdita dei numeri di sequenza nella cache.</span><span class="sxs-lookup"><span data-stu-id="560a3-141">When created with the CACHE option, an unexpected shutdown, such as a power failure, can lose the sequence numbers in the cache.</span></span>  
  
 <span data-ttu-id="560a3-142">Se sono presenti più istanze della funzione `NEXT VALUE FOR` tramite cui viene specificato lo stesso generatore di sequenze in un'unica istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)], mediante tutte le istanze viene restituito lo stesso valore per una determinata riga elaborata da questa istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="560a3-142">If there are multiple instances of the `NEXT VALUE FOR` function specifying the same sequence generator within a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, all those instances return the same value for a given row processed by that [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="560a3-143">Questo comportamento è coerente con lo standard ANSI.</span><span class="sxs-lookup"><span data-stu-id="560a3-143">This behavior is consistent with the ANSI standard.</span></span>  
  
## <a name="typical-use"></a><span data-ttu-id="560a3-144">Utilizzo tipico</span><span class="sxs-lookup"><span data-stu-id="560a3-144">Typical Use</span></span>  
 <span data-ttu-id="560a3-145">Per creare un numero di sequenza intero che viene incrementato di 1 da -2.147.483.648 a 2.147.483.647, utilizzare l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="560a3-145">To create an integer sequence number that increments by 1 from -2,147,483,648 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    INCREMENT BY 1 ;  
```  
  
 <span data-ttu-id="560a3-146">Per creare un numero di sequenza intero simile a una colonna di identità che viene incrementato di 1 da 1 a 2.147.483.647, utilizzare l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="560a3-146">To create an integer sequence number similar to an identity column that increments by 1 from 1 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
  
```  
  
## <a name="managing-sequences"></a><span data-ttu-id="560a3-147">Gestione di sequenze</span><span class="sxs-lookup"><span data-stu-id="560a3-147">Managing Sequences</span></span>  
 <span data-ttu-id="560a3-148">Per informazioni sulle sequenze, eseguire una query su [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="560a3-148">For information about sequences, query [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="560a3-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="560a3-149">Examples</span></span>  
 <span data-ttu-id="560a3-150">Altri esempi sono disponibili negli argomenti [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql) e [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="560a3-150">There are additional examples in the topics [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql), and [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span></span>  
  
### <a name="a-using-a-sequence-number-in-a-single-table"></a><span data-ttu-id="560a3-151">R.</span><span class="sxs-lookup"><span data-stu-id="560a3-151">A.</span></span> <span data-ttu-id="560a3-152">Utilizzo di un numero di sequenza in una singola tabella</span><span class="sxs-lookup"><span data-stu-id="560a3-152">Using a sequence number in a single table</span></span>  
 <span data-ttu-id="560a3-153">Nell'esempio seguente viene creato uno schema denominato Test, una tabella denominata Orders e una sequenza denominata CountBy1, quindi vengono inserite righe nella tabella usando la funzione NEXT VALUE FOR.</span><span class="sxs-lookup"><span data-stu-id="560a3-153">The following example creates a schema named Test, a table named Orders, and a sequence named CountBy1, and then inserts rows into the table using the NEXT VALUE FOR function.</span></span>  
  
```  
--Create the Test schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Orders  
    (OrderID int PRIMARY KEY,  
    Name varchar(20) NOT NULL,  
    Qty int NOT NULL);  
GO  
  
-- Create a sequence  
CREATE SEQUENCE Test.CountBy1  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
-- Insert three records  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Tire', 2) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Seat', 1) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Brake', 1) ;  
GO  
  
-- View the table  
SELECT * FROM Test.Orders ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `OrderID  Name    Qty`  
  
 `1        Tire    2`  
  
 `2        Seat    1`  
  
 `3        Brake   1`  
  
### <a name="b-calling-next-value-for-before-inserting-a-row"></a><span data-ttu-id="560a3-154">B.</span><span class="sxs-lookup"><span data-stu-id="560a3-154">B.</span></span> <span data-ttu-id="560a3-155">Chiamata a NEXT VALUE FOR prima di inserire una riga</span><span class="sxs-lookup"><span data-stu-id="560a3-155">Calling NEXT VALUE FOR before inserting a row</span></span>  
 <span data-ttu-id="560a3-156">Utilizzando la tabella `Orders` creata nell'esempio A, nell'esempio seguente viene dichiarata una variabile denominata `@nextID`, quindi viene utilizzata la funzione NEXT VALUE FOR per impostare la variabile sul successivo numero di sequenza disponibile.</span><span class="sxs-lookup"><span data-stu-id="560a3-156">Using the `Orders` table created in example A, the following example declares a variable named `@nextID`, and then uses the NEXT VALUE FOR function to set the variable to the next available sequence number.</span></span> <span data-ttu-id="560a3-157">Si presuppone che nell'applicazione vengano eseguite alcune operazioni di elaborazione dell'ordine, ad esempio fornire al cliente il numero di `OrderID` dell'ordine potenziale, quindi convalidare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="560a3-157">The application is presumed to do some processing of the order, such as providing the customer with the `OrderID` number of their potential order, and then validates the order.</span></span> <span data-ttu-id="560a3-158">Indipendentemente dalla durata di tale elaborazione o dal numero di ordini aggiunti durante il processo, viene mantenuto il numero originale per l'utilizzo da parte di questa connessione.</span><span class="sxs-lookup"><span data-stu-id="560a3-158">No matter how long this processing might take, or how many other orders are added during the process, the original number is preserved for use by this connection.</span></span> <span data-ttu-id="560a3-159">Infine, viene aggiunto l'ordine alla tabella `INSERT` tramite l'istruzione `Orders` .</span><span class="sxs-lookup"><span data-stu-id="560a3-159">Finally, the `INSERT` statement adds the order to the `Orders` table.</span></span>  
  
```  
DECLARE @NextID int ;  
SET @NextID = NEXT VALUE FOR Test.CountBy1;  
-- Some work happens  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (@NextID, 'Rim', 2) ;  
GO  
  
```  
  
### <a name="c-using-a-sequence-number-in-multiple-tables"></a><span data-ttu-id="560a3-160">C.</span><span class="sxs-lookup"><span data-stu-id="560a3-160">C.</span></span> <span data-ttu-id="560a3-161">Utilizzo di un numero di sequenza in più tabelle</span><span class="sxs-lookup"><span data-stu-id="560a3-161">Using a sequence number in multiple tables</span></span>  
 <span data-ttu-id="560a3-162">In questo esempio si presuppone che un processo di controllo di una linea di produzione riceva notifica di eventi che si verificano in tutta l'officina.</span><span class="sxs-lookup"><span data-stu-id="560a3-162">This example assumes that a production-line monitoring process receives notification of events that occur throughout the workshop.</span></span> <span data-ttu-id="560a3-163">Ogni evento riceve un numero `EventID` univoco e a incremento progressivo costante.</span><span class="sxs-lookup"><span data-stu-id="560a3-163">Each event receives a unique and monotonically increasing `EventID` number.</span></span> <span data-ttu-id="560a3-164">Per tutti gli eventi viene utilizzato lo stesso numero di sequenza `EventID` , in modo che nei report in cui vengono combinati tutti gli eventi sia possibile identificare in modo univoco ogni evento.</span><span class="sxs-lookup"><span data-stu-id="560a3-164">All events use the same `EventID` sequence number so that reports that combine all events can uniquely identify each event.</span></span> <span data-ttu-id="560a3-165">I dati degli eventi vengono tuttavia archiviati in tre tabelle diverse, a seconda del tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="560a3-165">However the event data is stored in three different tables, depending on the type of event.</span></span> <span data-ttu-id="560a3-166">L'esempio di codice illustra come creare uno schema denominato `Audit`, una sequenza denominata `EventCounter`e tre tabelle, ciascuna delle quali usa la sequenza `EventCounter` come valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="560a3-166">The code example creates a schema named `Audit`, a sequence named `EventCounter`, and three tables which each use the `EventCounter` sequence as a default value.</span></span> <span data-ttu-id="560a3-167">Nell'esempio vengono quindi aggiunte righe alle tre tabelle e vengono eseguite query sui risultati.</span><span class="sxs-lookup"><span data-stu-id="560a3-167">Then the example adds rows to the three tables and queries the results.</span></span>  
  
```  
CREATE SCHEMA Audit ;  
GO  
CREATE SEQUENCE Audit.EventCounter  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
CREATE TABLE Audit.ProcessEvents  
(  
    EventID int PRIMARY KEY CLUSTERED   
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EventCode nvarchar(5) NOT NULL,  
    Description nvarchar(300) NULL  
) ;  
GO  
  
CREATE TABLE Audit.ErrorEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NULL,  
    ErrorNumber int NOT NULL,  
    EventDesc nvarchar(256) NULL  
) ;  
GO  
  
CREATE TABLE Audit.StartStopEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NOT NULL,  
    StartOrStop bit NOT NULL  
) ;  
GO  
  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 0) ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (72, 0) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (2735,   
    'Clean room temperature 18 degrees C.') ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (18, 'Spin rate threashold exceeded.') ;  
INSERT Audit.ErrorEvents (EquipmentID, ErrorNumber, EventDesc)   
    VALUES (248, 82, 'Feeder jam') ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 1) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (1841, 'Central feed in bypass mode.') ;  
-- The following statement combines all events, though not all fields.  
SELECT EventID, EventTime, Description FROM Audit.ProcessEvents   
UNION SELECT EventID, EventTime, EventDesc FROM Audit.ErrorEvents   
UNION SELECT EventID, EventTime,   
CASE StartOrStop   
    WHEN 0 THEN 'Start'   
    ELSE 'Stop'  
END   
FROM Audit.StartStopEvents  
ORDER BY EventID ;  
GO  
  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `EventID  EventTime                Description`  
  
 `1        2009-11-02 15:00:51.157  Start`  
  
 `2        2009-11-02 15:00:51.160  Start`  
  
 `3        2009-11-02 15:00:51.167  Clean room temperature 18 degrees C.`  
  
 `4        2009-11-02 15:00:51.167  Spin rate threshold exceeded.`  
  
 `5        2009-11-02 15:00:51.173  Feeder jam`  
  
 `6        2009-11-02 15:00:51.177  Stop`  
  
 `7        2009-11-02 15:00:51.180  Central feed in bypass mode.`  
  
### <a name="d-generating-repeating-sequence-numbers-in-a-result-set"></a><span data-ttu-id="560a3-168">D.</span><span class="sxs-lookup"><span data-stu-id="560a3-168">D.</span></span> <span data-ttu-id="560a3-169">Generazione di numeri di sequenza ripetuti in un set di risultati</span><span class="sxs-lookup"><span data-stu-id="560a3-169">Generating repeating sequence numbers in a result set</span></span>  
 <span data-ttu-id="560a3-170">Nell'esempio seguente vengono illustrate due caratteristiche dei numeri di sequenza: ripetizione e utilizzo di `NEXT VALUE FOR` in un'istruzione Select.</span><span class="sxs-lookup"><span data-stu-id="560a3-170">The following example demonstrates two features of sequence numbers: cycling, and using `NEXT VALUE FOR` in a select statement.</span></span>  
  
```  
CREATE SEQUENCE CountBy5  
   AS tinyint  
    START WITH 1  
    INCREMENT BY 1  
    MINVALUE 1  
    MAXVALUE 5  
    CYCLE ;  
GO  
  
SELECT NEXT VALUE FOR CountBy5 AS SurveyGroup, Name FROM sys.objects ;  
GO  
```  
  
### <a name="e-generating-sequence-numbers-for-a-result-set-by-using-the-over-clause"></a><span data-ttu-id="560a3-171">E.</span><span class="sxs-lookup"><span data-stu-id="560a3-171">E.</span></span> <span data-ttu-id="560a3-172">Generazione di numeri di sequenza per un set di risultati tramite la clausola OVER</span><span class="sxs-lookup"><span data-stu-id="560a3-172">Generating sequence numbers for a result set by using the OVER clause</span></span>  
 <span data-ttu-id="560a3-173">Nell'esempio seguente viene utilizzata la clausola `OVER` per ordinare il set di risultati in base a `Name` prima che venga aggiunta la colonna di numeri di sequenza.</span><span class="sxs-lookup"><span data-stu-id="560a3-173">The following example uses the `OVER` clause to sort the result set by `Name` before it adds the sequence number column.</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE SCHEMA Samples ;  
GO  
  
CREATE SEQUENCE Samples.IDLabel  
    AS tinyint  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="f-resetting-the-sequence-number"></a><span data-ttu-id="560a3-174">F.</span><span class="sxs-lookup"><span data-stu-id="560a3-174">F.</span></span> <span data-ttu-id="560a3-175">Reimpostazione del numero di sequenza</span><span class="sxs-lookup"><span data-stu-id="560a3-175">Resetting the sequence number</span></span>  
 <span data-ttu-id="560a3-176">Nell'esempio E sono stati utilizzati i primi 79 numeri di sequenza `Samples.IDLabel`.</span><span class="sxs-lookup"><span data-stu-id="560a3-176">Example E consumed the first 79 of the `Samples.IDLabel` sequence numbers.</span></span> <span data-ttu-id="560a3-177">È possibile che la versione in uso di `AdventureWorks2012` restituisca un numero di risultati diverso. Eseguire gli elementi seguenti per utilizzare i successivi 79 numeri di sequenza (da 80 a 158).</span><span class="sxs-lookup"><span data-stu-id="560a3-177">(Your version of `AdventureWorks2012` may return a different number of results.) Execute the following to consume the next 79 sequence numbers (80 though 158).</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
 <span data-ttu-id="560a3-178">Eseguire l'istruzione seguente per riavviare la sequenza `Samples.IDLabel`.</span><span class="sxs-lookup"><span data-stu-id="560a3-178">Execute the following statement to restart the `Samples.IDLabel` sequence.</span></span>  
  
```  
ALTER SEQUENCE Samples.IDLabel  
RESTART WITH 1 ;  
```  
  
 <span data-ttu-id="560a3-179">Eseguire di nuovo l'istruzione SELECT per verificare che la sequenza `Samples.IDLabel` sia ripartita dal numero 1.</span><span class="sxs-lookup"><span data-stu-id="560a3-179">Execute the select statement again to verify that the `Samples.IDLabel` sequence restarted with number 1.</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="g-changing-a-table-from-identity-to-sequence"></a><span data-ttu-id="560a3-180">G.</span><span class="sxs-lookup"><span data-stu-id="560a3-180">G.</span></span> <span data-ttu-id="560a3-181">Modifica di una tabella da identità a sequenza</span><span class="sxs-lookup"><span data-stu-id="560a3-181">Changing a table from identity to sequence</span></span>  
 <span data-ttu-id="560a3-182">Nell'esempio seguente vengono creati uno schema e una tabella contenente tre righe per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="560a3-182">The following example creates a schema and table containing three rows for the example.</span></span> <span data-ttu-id="560a3-183">Viene quindi aggiunta una nuova colonna e viene eliminata la colonna precedente.</span><span class="sxs-lookup"><span data-stu-id="560a3-183">Then the example adds a new column and drops the old column.</span></span>  
  
```  
-- Create a schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Department  
    (  
        DepartmentID smallint IDENTITY(1,1) NOT NULL,  
        Name nvarchar(100) NOT NULL,  
        GroupName nvarchar(100) NOT NULL  
    CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC)   
    ) ;  
GO  
  
-- Insert three rows into the table  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Engineering', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Tool Design', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Sales', 'Sales and Marketing');  
GO  
  
-- View the table that will be changed  
SELECT * FROM Test.Department ;  
GO  
  
-- End of portion creating a sample table  
--------------------------------------------------------  
-- Add the new column that does not have the IDENTITY property  
ALTER TABLE Test.Department   
    ADD DepartmentIDNew smallint NULL  
GO  
  
-- Copy values from the old column to the new column  
UPDATE Test.Department  
    SET DepartmentIDNew = DepartmentID ;  
GO  
  
-- Drop the primary key constraint on the old column  
ALTER TABLE Test.Department  
    DROP CONSTRAINT [PK_Department_DepartmentID];  
-- Drop the old column  
ALTER TABLE Test.Department  
    DROP COLUMN DepartmentID ;  
GO  
  
-- Rename the new column to the old columns name  
EXEC sp_rename 'Test.Department.DepartmentIDNew',   
    'DepartmentID', 'COLUMN';  
GO  
  
-- Change the new column to NOT NULL  
ALTER TABLE Test.Department  
    ALTER COLUMN DepartmentID smallint NOT NULL ;  
-- Add the unique primary key constraint  
ALTER TABLE Test.Department  
    ADD CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC) ;  
-- Get the highest current value from the DepartmentID column   
-- and create a sequence to use with the column. (Returns 3.)  
SELECT MAX(DepartmentID) FROM Test.Department ;  
-- Use the next desired value (4) as the START WITH VALUE;  
CREATE SEQUENCE Test.DeptSeq  
    AS smallint  
    START WITH 4  
    INCREMENT BY 1 ;  
GO  
  
-- Add a default value for the DepartmentID column  
ALTER TABLE Test.Department  
    ADD CONSTRAINT DefSequence DEFAULT (NEXT VALUE FOR Test.DeptSeq)   
        FOR DepartmentID;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;   
-- Test insert  
INSERT Test.Department (Name, GroupName)  
    VALUES ('Audit', 'Quality Assurance') ;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;  
GO  
  
```  
  
 <span data-ttu-id="560a3-184">Le istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] che utilizzano `SELECT *` riceveranno la nuova colonna come ultima colonna anziché come prima.</span><span class="sxs-lookup"><span data-stu-id="560a3-184">[!INCLUDE[tsql](../../../includes/tsql-md.md)] statements that use `SELECT *` will receive the new column as the last column instead of the first column.</span></span> <span data-ttu-id="560a3-185">Se ciò non è accettabile, sarà necessario creare una tabella completamente nuova, spostare i dati in tale tabella, quindi ricreare le autorizzazioni nella nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="560a3-185">If this is not acceptable, then you must create an entirely new table, move the data to it, and then recreate the permissions on the new table.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="560a3-186">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="560a3-186">Related Content</span></span>  
 [<span data-ttu-id="560a3-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="560a3-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-sequence-transact-sql)  
  
 [<span data-ttu-id="560a3-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="560a3-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-sequence-transact-sql)  
  
 [<span data-ttu-id="560a3-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="560a3-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-sequence-transact-sql)  
  
 [<span data-ttu-id="560a3-190">IDENTITY &#40;proprietà&#41; &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="560a3-190">IDENTITY &#40;Property&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql-identity-property)  
  
  
