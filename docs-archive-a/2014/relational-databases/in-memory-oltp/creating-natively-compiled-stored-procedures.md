---
title: Creazione di stored procedure compilate in modo nativo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: e6b34010-cf62-4f65-bbdf-117f291cde7b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3e8e8139427c7f2ad92eea856be8da542f65e344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626094"
---
# <a name="creating-natively-compiled-stored-procedures"></a><span data-ttu-id="8aa1f-102">Creazione di stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="8aa1f-102">Creating Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="8aa1f-103">Le stored procedure compilate in modo nativo non implementano la programmabilità completa di [!INCLUDE[tsql](../../includes/tsql-md.md)] e la superficie di attacco delle query.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-103">Natively compiled stored procedures do not implement the full [!INCLUDE[tsql](../../includes/tsql-md.md)] programmability and query surface area.</span></span> <span data-ttu-id="8aa1f-104">Alcuni costrutti [!INCLUDE[tsql](../../includes/tsql-md.md)] non possono essere utilizzati all'interno delle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-104">There are certain [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs that cannot be used inside natively compiled stored procedures.</span></span> <span data-ttu-id="8aa1f-105">Per ulteriori informazioni, vedere [costrutti supportati nelle stored procedure compilate in modo nativo](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span><span class="sxs-lookup"><span data-stu-id="8aa1f-105">For more information, see [Supported Constructs in Natively Compiled Stored Procedures](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span></span>  
  
 <span data-ttu-id="8aa1f-106">Esistono, tuttavia, alcune funzionalità di [!INCLUDE[tsql](../../includes/tsql-md.md)] che sono supportate solo per le stored procedure compilate in modo nativo:</span><span class="sxs-lookup"><span data-stu-id="8aa1f-106">There are, however, several [!INCLUDE[tsql](../../includes/tsql-md.md)] features that are only supported for natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="8aa1f-107">Blocchi atomici.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-107">Atomic blocks.</span></span> <span data-ttu-id="8aa1f-108">Per altre informazioni, vedere [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8aa1f-108">For more information, see [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span></span>  
  
-   <span data-ttu-id="8aa1f-109">Vincoli `NOT NULL` su parametri e variabili nelle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-109">`NOT NULL` constraints on parameters of and variables in natively compiled stored procedures.</span></span> <span data-ttu-id="8aa1f-110">Non è possibile assegnare valori `NULL` ai parametri o alle variabili dichiarate come `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-110">You cannot assign `NULL` values to parameters or variables declared as `NOT NULL`.</span></span> <span data-ttu-id="8aa1f-111">Per altre informazioni, vedere [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8aa1f-111">For more information, see [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span></span>  
  
-   <span data-ttu-id="8aa1f-112">Associazione allo schema delle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-112">Schema binding of natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="8aa1f-113">Le stored procedure compilate in modo nativo vengono create usando [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8aa1f-113">Natively compiled stored procedures are created using [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span> <span data-ttu-id="8aa1f-114">Nell'esempio seguente vengono illustrate una tabella ottimizzata per la memoria e una stored procedure compilata in modo nativo per inserire righe nella tabella.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-114">The following example shows a memory-optimized table and a natively compiled stored procedure used for inserting rows into the table.</span></span>  
  
```sql  
create table dbo.Ord  
(OrdNo integer not null primary key nonclustered,   
 OrdDate datetime not null,   
 CustCode nvarchar(5) not null)   
 with (memory_optimized=on)  
go  
  
create procedure dbo.OrderInsert(@OrdNo integer, @CustCode nvarchar(5))  
with native_compilation, schemabinding, execute as owner  
as   
begin atomic with  
(transaction isolation level = snapshot,  
language = N'English')  
  
  declare @OrdDate datetime = getdate();  
  insert into dbo.Ord (OrdNo, CustCode, OrdDate) values (@OrdNo, @CustCode, @OrdDate);  
end  
go  
```  
  
 <span data-ttu-id="8aa1f-115">Nell'esempio di codice `NATIVE_COMPILATION` indica che questa stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] è una stored procedure compilata in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-115">In the code sample, `NATIVE_COMPILATION` indicates that this [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure is a natively compiled stored procedure.</span></span> <span data-ttu-id="8aa1f-116">Sono necessarie le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8aa1f-116">The following options are required:</span></span>  
  
|<span data-ttu-id="8aa1f-117">Opzione</span><span class="sxs-lookup"><span data-stu-id="8aa1f-117">Option</span></span>|<span data-ttu-id="8aa1f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aa1f-118">Description</span></span>|  
|------------|-----------------|  
|`SCHEMABINDING`|<span data-ttu-id="8aa1f-119">Le stored procedure compilate in modo nativo devono essere associate allo schema degli oggetti a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-119">Natively compiled stored procedures must be bound to the schema of the objects it references.</span></span> <span data-ttu-id="8aa1f-120">Ciò significa che i riferimenti alla tabella della procedura non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-120">This means that table references by the procedure cannot be dropped.</span></span> <span data-ttu-id="8aa1f-121">Le tabelle a cui viene fatto riferimento nella procedura devono includere il nome dello schema e i caratteri jolly ( \* ) non sono consentiti nelle query.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-121">Tables referenced in the procedure must include their schema name, and wildcards (\*) are not allowed in queries.</span></span> <span data-ttu-id="8aa1f-122">`SCHEMABINDING` è supportato unicamente per le stored procedure compilate in modo nativo in questa versione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aa1f-122">`SCHEMABINDING` is only supported for natively compiled stored procedures in this version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>|  
|`EXECUTE AS`|<span data-ttu-id="8aa1f-123">Le stored procedure compilate in modo nativo non supportano `EXECUTE AS CALLER`, ovvero il contesto di esecuzione predefinito.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-123">Natively compiled stored procedures do not support `EXECUTE AS CALLER`, which is the default execution context.</span></span> <span data-ttu-id="8aa1f-124">Di conseguenza, è necessario specificare il contesto di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-124">Therefore, specifying the execution context is required.</span></span> <span data-ttu-id="8aa1f-125">`EXECUTE AS OWNER`Sono supportate le opzioni, `EXECUTE AS` *User*e `EXECUTE AS SELF` .</span><span class="sxs-lookup"><span data-stu-id="8aa1f-125">The options `EXECUTE AS OWNER`, `EXECUTE AS`*user*, and `EXECUTE AS SELF` are supported.</span></span>|  
|`BEGIN ATOMIC`|<span data-ttu-id="8aa1f-126">Il corpo di una stored procedure compilata in modo nativo deve essere costituito esattamente da un blocco atomico.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-126">The natively compiled stored procedure body must consist of exactly one atomic block.</span></span> <span data-ttu-id="8aa1f-127">I blocchi atomici garantiscono l'esecuzione atomica della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-127">Atomic blocks guarantee atomic execution of the stored procedure.</span></span> <span data-ttu-id="8aa1f-128">Se la stored procedure viene richiamata all'esterno del contesto di una transazione attiva, verrà avviata una nuova transazione il cui commit avverrà alla fine del blocco atomico.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-128">If the procedure is invoked outside the context of an active transaction, it will start a new transaction, which commits at the end of the atomic block.</span></span> <span data-ttu-id="8aa1f-129">I blocchi atomici nelle stored procedure compilate in modo nativo presentano due opzioni obbligatorie:</span><span class="sxs-lookup"><span data-stu-id="8aa1f-129">Atomic blocks in natively compiled stored procedures have two required options:</span></span><br /><br /> <span data-ttu-id="8aa1f-130">`TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-130">`TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="8aa1f-131">Vedere [livelli di isolamento delle transazioni](../../database-engine/transaction-isolation-levels.md) per i livelli di isolamento supportati.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-131">See [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md) for supported isolation levels.</span></span><br /><br /> <span data-ttu-id="8aa1f-132">`LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-132">`LANGUAGE`.</span></span> <span data-ttu-id="8aa1f-133">Il linguaggio della stored procedure deve essere impostato su uno dei linguaggi o alias disponibili.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-133">The language for the stored procedure must be set to one of the available languages or language aliases.</span></span>|  
  
 <span data-ttu-id="8aa1f-134">In relazione a `EXECUTE AS` e agli account di accesso di Windows, può verificarsi un errore a causa della rappresentazione eseguita tramite `EXECUTE AS`.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-134">Regarding `EXECUTE AS` and Windows logins, an error can occur because of the impersonation done through `EXECUTE AS`.</span></span> <span data-ttu-id="8aa1f-135">Se un account utente utilizza l'autenticazione di Windows, è necessario che vi sia attendibilità totale tra l'account del servizio utilizzato per l'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e il dominio dell'account di accesso di Windows.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-135">If a user account uses Windows Authentication, there must be full trust between the service account used for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance and the domain of the Windows login.</span></span> <span data-ttu-id="8aa1f-136">Se non è presente alcuna attendibilità totale, quando si crea una stored procedure compilata in modo nativo viene restituito il messaggio di errore seguente: messaggio 15404, non è stato possibile ottenere informazioni relative al gruppo/utente di Windows NT ' username ', codice di errore 0x5.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-136">If there is not full trust, the following error message is returned when creating a natively compiled stored procedure: Msg 15404, Could not obtain information about Windows NT group/user 'username', error code 0x5.</span></span>  
  
 <span data-ttu-id="8aa1f-137">Per risolvere l'errore, utilizzare una delle soluzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8aa1f-137">To resolve this error, use one of the following:</span></span>  
  
-   <span data-ttu-id="8aa1f-138">Utilizzare un account dello stesso dominio dell'utente di Windows per il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aa1f-138">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="8aa1f-139">Se [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizza un account computer, ad esempio Servizio di rete o Sistema locale, il computer deve essere considerato attendibile dal dominio che contiene l'utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-139">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows user.</span></span>  
  
-   <span data-ttu-id="8aa1f-140">Utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aa1f-140">Use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="8aa1f-141">Durante la creazione di una stored procedure compilata in modo nativo, potrebbe essere visualizzato l'errore 15517.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-141">You may also see error 15517 when creating a natively compiled stored procedure.</span></span> <span data-ttu-id="8aa1f-142">Per ulteriori informazioni, vedere [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="8aa1f-142">For more information, see [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span></span>  
  
## <a name="updating-a-natively-compiled-stored-procedure"></a><span data-ttu-id="8aa1f-143">Aggiornamento di una stored procedure compilata in modo nativo</span><span class="sxs-lookup"><span data-stu-id="8aa1f-143">Updating a Natively Compiled Stored Procedure</span></span>  
 <span data-ttu-id="8aa1f-144">L'esecuzione di operazioni di modifica nelle stored procedure compilate in modo nativo non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-144">Performing alter operations on natively compiled stored procedures is not supported.</span></span> <span data-ttu-id="8aa1f-145">Per modificare una stored procedure compilata in modo nativo è possibile eliminare e ricreare la stored procedure:</span><span class="sxs-lookup"><span data-stu-id="8aa1f-145">One way to modify a natively compiled stored procedure is to drop and recreate the stored procedure:</span></span>  
  
1.  <span data-ttu-id="8aa1f-146">Generare lo script per le autorizzazioni della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-146">Generate script for the permissions on the stored procedure.</span></span>  
  
2.  <span data-ttu-id="8aa1f-147">Facoltativamente, generare lo script per la stored procedure e il salvataggio come backup.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-147">Optional, generate script for the stored procedure and save as a backup.</span></span>  
  
3.  <span data-ttu-id="8aa1f-148">Eliminare la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-148">Drop the stored procedure.</span></span>  
  
4.  <span data-ttu-id="8aa1f-149">Creare la stored procedure modificata.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-149">Create the altered stored procedure.</span></span>  
  
5.  <span data-ttu-id="8aa1f-150">Riapplicare le autorizzazioni dello script alla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-150">Re-apply the scripted permissions to the stored procedure.</span></span>  
  
 <span data-ttu-id="8aa1f-151">Lo svantaggio di questa procedura consiste nel fatto che l'applicazione sarà offline dall'inizio del passaggio 3 alla fine del passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-151">The disadvantage to this procedure is the application will be offline from the start of step 3 through the completion of step 5.</span></span> <span data-ttu-id="8aa1f-152">È possibile che siano necessari alcuni secondi e che il client che utilizza l'applicazione riceva messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-152">This may take a few seconds and the client using the application may see error messages.</span></span>  
  
 <span data-ttu-id="8aa1f-153">Un'altra soluzione efficace per modificare una stored procedure compilata in modo nativo consiste nel creare innanzitutto una nuova versione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-153">Another way to (effectively) modify a natively compiled stored procedure is to first create a new version of the stored procedure.</span></span> <span data-ttu-id="8aa1f-154">In questo caso, la stored procedure compilata in modo nativo ha un numero di versione associato.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-154">Here, the natively compiled stored procedure has an associated version number.</span></span> <span data-ttu-id="8aa1f-155">La versione precedente si chiama SP_Vold e la nuova versione SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-155">We will call the old version SP_Vold and the new version SP_Vnew.</span></span>  
  
1.  <span data-ttu-id="8aa1f-156">Generare lo script per le autorizzazioni di SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-156">Generate script for the permissions on SP_Vold.</span></span>  
  
2.  <span data-ttu-id="8aa1f-157">Creare SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-157">Create SP_Vnew.</span></span>  
  
3.  <span data-ttu-id="8aa1f-158">Applicare le autorizzazioni di SP_Vold a SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-158">Apply the permissions of SP_Vold to SP_Vnew.</span></span>  
  
4.  <span data-ttu-id="8aa1f-159">Aggiornare i riferimenti a SP_Vold in modo che puntino a SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-159">Update references to SP_Vold to point to SP_Vnew.</span></span> <span data-ttu-id="8aa1f-160">Questa operazione può essere eseguita in diversi modi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8aa1f-160">This can be accomplished in different of ways, for example:</span></span>  
  
     <span data-ttu-id="8aa1f-161">Utilizzare una stored procedure (basata su disco) wrapper e modificare tale procedura in modo che punti a SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-161">Use a wrapper (disk-based) stored procedure, and alter that procedure to point to SP_Vnew.</span></span> <span data-ttu-id="8aa1f-162">Lo svantaggio di questo approccio sta nell'impatto del riferimento indiretto sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-162">The disadvantage of this approach is the performance impact of the indirection.</span></span>  
  
    ```sql  
    ALTER PROCEDURE dbo.SP p1,...,pn  
    AS  
      EXEC dbo.SP_Vnew p1,...,pn  
    GO  
    ```  
  
5.  <span data-ttu-id="8aa1f-163">Facoltativamente, eliminare SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-163">Optional, drop SP_Vold.</span></span>  
  
 <span data-ttu-id="8aa1f-164">Il vantaggio di questo approccio consiste nel fatto che l'applicazione non risulta offline.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-164">The advantage of this approach is that the application does not go offline.</span></span> <span data-ttu-id="8aa1f-165">Tuttavia, è necessario più impegno per mantenere i riferimenti e verificare che puntino sempre alla versione più recente della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8aa1f-165">However, more work is required to maintain the references and make sure they always point to the latest version of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa1f-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aa1f-166">See Also</span></span>  
 [<span data-ttu-id="8aa1f-167">Stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="8aa1f-167">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
