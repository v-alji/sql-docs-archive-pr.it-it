---
title: Eliminazione di un assembly | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- removing assemblies
- DROP ASSEMBLY statement
- assemblies [CLR integration], removing
- dropping assemblies
ms.assetid: 03481034-dc91-4488-ab24-ba44243e2690
author: rothja
ms.author: jroth
ms.openlocfilehash: 45d02cbb57459a4c1c11330446021c32dc897353
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720033"
---
# <a name="dropping-an-assembly"></a><span data-ttu-id="85894-102">Eliminazione di un assembly</span><span class="sxs-lookup"><span data-stu-id="85894-102">Dropping an Assembly</span></span>
  <span data-ttu-id="85894-103">Gli assembly registrati in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzando l'istruzione CREATE ASSEMBLY possono essere eliminati quando la funzionalità che forniscono non è più necessaria.</span><span class="sxs-lookup"><span data-stu-id="85894-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement can be deleted, or dropped, when the functionality they provide is no longer needed.</span></span> <span data-ttu-id="85894-104">L'eliminazione di un assembly ne comporta la rimozione insieme a tutti i file associati, ad esempio i file di debug, dal database.</span><span class="sxs-lookup"><span data-stu-id="85894-104">Dropping an assembly removes the assembly and all of its associated files, such as debug files, from the database.</span></span> <span data-ttu-id="85894-105">Per eliminare un assembly, utilizzare l'istruzione DROP ASSEMBLY con la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="85894-105">To drop an assembly, use the DROP ASSEMBLY statement with the following syntax:</span></span>  
  
```  
DROP ASSEMBLY MyDotNETAssembly  
```  
  
 <span data-ttu-id="85894-106">DROP ASSEMBLY non interferisce con il codice che fa riferimento all'assembly attualmente in esecuzione. Tuttavia, dopo l'esecuzione di DROP ASSEMBLY qualsiasi tentativo di richiamare il codice dell'assembly avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="85894-106">DROP ASSEMBLY does not interfere with any code referencing the assembly that is currently running, but after DROP ASSEMBLY executes, any attempts to invoke the assembly code fail.</span></span>  
  
 <span data-ttu-id="85894-107">DROP ASSEMBLY restituisce un errore se all'assembly viene fatto riferimento da un altro assembly esistente nel database oppure se viene utilizzato da funzioni CLR (Common Language Runtime), procedure, trigger, tipi definiti dall'utente o funzioni di aggregazione definite dall'utente nel database corrente.</span><span class="sxs-lookup"><span data-stu-id="85894-107">DROP ASSEMBLY returns an error if the assembly is referenced by another assembly that exists in the database, or if it is used by common language runtime (CLR) functions, procedures, triggers, user-defined types (UDTs), or user-defined aggregates (UDAs) in the current database.</span></span> <span data-ttu-id="85894-108">Utilizzare innanzitutto le istruzioni DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER e DROP TYPE per eliminare gli oggetti di database gestiti contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="85894-108">First use the DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER, and DROP TYPE statements to delete any managed database objects contained in the assembly.</span></span>  
  
## <a name="removing-a-udt-from-the-database"></a><span data-ttu-id="85894-109">Rimozione di un tipo definito dall'utente (UDT) dal database</span><span class="sxs-lookup"><span data-stu-id="85894-109">Removing a UDT from the Database</span></span>  
 <span data-ttu-id="85894-110">L'istruzione DROP TYPE rimuove un tipo definito dall'utente (UDT) dal database corrente.</span><span class="sxs-lookup"><span data-stu-id="85894-110">The DROP TYPE statement removes a UDT from the current database.</span></span> <span data-ttu-id="85894-111">Dopo avere eliminato un tipo definito dall'utente (UDT), è possibile utilizzare l'istruzione DROP ASSEMBLY per eliminare l'assembly dal database.</span><span class="sxs-lookup"><span data-stu-id="85894-111">Once a UDT is dropped, you can use the DROP ASSEMBLY statement to drop the assembly from the database.</span></span>  
  
 <span data-ttu-id="85894-112">L'istruzione DROP TYPE non riesce se gli oggetti dipendono dal tipo definito dall'utente, come nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85894-112">The DROP TYPE statement fails if objects depend on the UDT, as in the following situations:</span></span>  
  
-   <span data-ttu-id="85894-113">Tabelle del database che contengono colonne definite mediante il tipo definito dall'utente (UDT).</span><span class="sxs-lookup"><span data-stu-id="85894-113">Tables in the database that contain columns defined using the UDT.</span></span>  
  
-   <span data-ttu-id="85894-114">Funzioni, stored procedure o trigger che utilizzano variabili o parametri del tipo definito dall'utente (UDT), creati nel database con la clausola WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="85894-114">Functions, stored procedures, or triggers that use variables or parameters of the UDT, created in the database with the WITH SCHEMABINDING clause.</span></span>  
  
### <a name="finding-udt-dependencies"></a><span data-ttu-id="85894-115">Ricerca di dipendenze di tipi definiti dall'utente (UDT)</span><span class="sxs-lookup"><span data-stu-id="85894-115">Finding UDT Dependencies</span></span>  
 <span data-ttu-id="85894-116">È necessario innanzitutto eliminare tutti gli oggetti dipendenti, quindi eseguire l'istruzione DROP TYPE.</span><span class="sxs-lookup"><span data-stu-id="85894-116">You must first drop all dependent objects, and then execute the DROP TYPE statement.</span></span> <span data-ttu-id="85894-117">Nella query seguente vengono [!INCLUDE[tsql](../../../includes/tsql-md.md)] individuate tutte le colonne e i parametri che utilizzano un tipo definito dall'utente nel database **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="85894-117">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] query locates all of the columns and parameters that use a UDT in the **AdventureWorks** database.</span></span>  
  
```  
USE Adventureworks;  
SELECT o.name AS major_name, o.type_desc AS major_type_desc  
     , c.name AS minor_name, c.type_desc AS minor_type_desc  
     , at.assembly_class  
  FROM (  
        SELECT object_id, name, user_type_id, 'SQL_COLUMN' AS type_desc  
          FROM sys.columns  
     UNION ALL  
        SELECT object_id, name, user_type_id, 'SQL_PROCEDURE_PARAMETER'  
          FROM sys.parameters  
     ) AS c  
  JOIN sys.objects AS o  
    ON o.object_id = c.object_id  
  JOIN sys.assembly_types AS at  
    ON at.user_type_id = c.user_type_id;   
```  
  
## <a name="see-also"></a><span data-ttu-id="85894-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85894-118">See Also</span></span>  
 <span data-ttu-id="85894-119">[Gestione degli assembly di integrazione CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="85894-119">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="85894-120">[Modifica di un assembly](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="85894-120">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="85894-121">[Creazione di un assembly](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="85894-121">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="85894-122">[DROP AGGREGAte &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85894-122">[DROP AGGREGATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span></span>  
 <span data-ttu-id="85894-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85894-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span></span>  
 <span data-ttu-id="85894-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85894-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="85894-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85894-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="85894-126">DROP TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="85894-126">DROP TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-type-transact-sql)  
  
  
