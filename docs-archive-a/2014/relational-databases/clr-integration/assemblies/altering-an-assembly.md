---
title: Modifica di un assembly | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], modifying
- permissions [CLR integration]
- altering assemblies
- ALTER ASSEMBLY statement
ms.assetid: 9e765fbd-f339-473c-8537-22f478e79696
author: rothja
ms.author: jroth
ms.openlocfilehash: c22ca979675d3b7f263e3bc6de0c41c134a1abcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720046"
---
# <a name="altering-an-assembly"></a><span data-ttu-id="adddb-102">Modifica di un assembly</span><span class="sxs-lookup"><span data-stu-id="adddb-102">Altering an Assembly</span></span>
  <span data-ttu-id="adddb-103">Gli assembly registrati in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] possono essere aggiornati da una versione più recente utilizzando l'istruzione ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="adddb-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can be updated from a more recent version using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="adddb-104">Per aggiornare un assembly, utilizzare l'istruzione ALTER ASSEMBLY con la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="adddb-104">To update an assembly, use the ALTER ASSEMBLY statement with the following syntax:</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
```  
  
 <span data-ttu-id="adddb-105">ALTER ASSEMBLY non interrompe i processi in esecuzione che utilizzano l'assembly. L'esecuzione di tali processi continua con l'assembly non modificato.</span><span class="sxs-lookup"><span data-stu-id="adddb-105">ALTER ASSEMBLY does not disrupt currently running processes that are using the assembly; the processes continue executing with the unaltered assembly.</span></span> <span data-ttu-id="adddb-106">Non è possibile utilizzare ALTER ASSEMBLY per modificare le firme di funzioni, funzioni di aggregazione, stored procedure e trigger di CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="adddb-106">ALTER ASSEMBLY cannot be used to change the signatures of common language runtime (CLR) functions, aggregate functions, stored procedures, and triggers.</span></span> <span data-ttu-id="adddb-107">Nuovi metodi pubblici possono essere aggiunti all'assembly, i metodi privati possono essere modificati nel modo desiderato e i metodi pubblici possono essere modificati a condizione di non modificare le firme o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="adddb-107">New public methods can be added to the assembly, private methods can be modified in any way, and public methods can be modified as long as signatures or attributes are not changed.</span></span> <span data-ttu-id="adddb-108">Non è possibile modificare tramite ALTER ASSEMBLY i campi contenuti in un tipo definito dall'utente con serializzazione nativa, inclusi i membri dei dati o le classi base.</span><span class="sxs-lookup"><span data-stu-id="adddb-108">Fields that are contained within a native-serialized user-defined type, including data members or base classes, cannot be changed by using ALTER ASSEMBLY.</span></span> <span data-ttu-id="adddb-109">Tutte le altre modifiche non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="adddb-109">All other changes are unsupported.</span></span> <span data-ttu-id="adddb-110">Per ulteriori informazioni, vedere [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="adddb-110">For more information, see [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
## <a name="changing-the-permission-set-of-an-assembly"></a><span data-ttu-id="adddb-111">Modifica del set di autorizzazioni di un assembly</span><span class="sxs-lookup"><span data-stu-id="adddb-111">Changing the Permission Set of an Assembly</span></span>  
 <span data-ttu-id="adddb-112">Il set di autorizzazioni di un assembly può essere anch'esso modificato utilizzando l'istruzione ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="adddb-112">The permission set of an assembly can also be changed using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="adddb-113">Nell'istruzione seguente il set di autorizzazioni dell'assembly SQLCLRTest viene modificato in `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="adddb-113">The following statement changes the permission set of the SQLCLRTest assembly to `EXTERNAL_ACCESS`.</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
WITH PERMISSION_SET = EXTERNAL_ACCESS   
```  
  
 <span data-ttu-id="adddb-114">Se il set di autorizzazioni di un assembly viene modificato da `SAFE` a `EXTERNAL_ACCESS` o `UNSAFE`, è innanzitutto necessario creare una chiave asimmetrica e un account di accesso corrispondente con autorizzazione `EXTERNAL ACCESS ASSEMBLY` o `UNSAFE ASSEMBLY` per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="adddb-114">If the permission set of an assembly is being changed from `SAFE` to `EXTERNAL_ACCESS` or `UNSAFE`, an asymmetric key and corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission or `UNSAFE ASSEMBLY` permission for the assembly must first be created.</span></span> <span data-ttu-id="adddb-115">Per altre informazioni, vedere [Creating an Assembly](creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="adddb-115">For more information, see [Creating an Assembly](creating-an-assembly.md).</span></span>  
  
## <a name="adding-the-source-code-of-an-assembly"></a><span data-ttu-id="adddb-116">Aggiunta del codice sorgente di un assembly.</span><span class="sxs-lookup"><span data-stu-id="adddb-116">Adding the Source Code of an Assembly</span></span>  
 <span data-ttu-id="adddb-117">La clausola ADD FILE nella sintassi ALTER ASSEMBLY non è presente in CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="adddb-117">The ADD FILE clause in the ALTER ASSEMBLY syntax is not present in CREATE ASSEMBLY.</span></span> <span data-ttu-id="adddb-118">È possibile utilizzarla per aggiungere codice sorgente o altri file associati a un assembly.</span><span class="sxs-lookup"><span data-stu-id="adddb-118">You can use it to add source code or any other files associated with an assembly.</span></span> <span data-ttu-id="adddb-119">I file vengono copiati dai percorsi originali e vengono archiviati nelle tabelle di sistema del database.</span><span class="sxs-lookup"><span data-stu-id="adddb-119">The files are copied from their original locations and stored in system tables in the database.</span></span> <span data-ttu-id="adddb-120">In questo modo il codice sorgente o gli altri file saranno sempre disponibili nel caso in cui sia necessario ricreare o documentare la versione corrente del tipo definito dall'utente (UDT).</span><span class="sxs-lookup"><span data-stu-id="adddb-120">This ensures that you always have source code or other files on hand should you ever need to re-create or document the current version of the UDT.</span></span>  
  
 <span data-ttu-id="adddb-121">L'istruzione seguente aggiunge il codice sorgente della classe Point.cs per il tipo definito dall'utente Point.</span><span class="sxs-lookup"><span data-stu-id="adddb-121">The following statement adds the Point.cs class source code for the Point UDT.</span></span> <span data-ttu-id="adddb-122">Il testo contenuto nel file Point.cs viene copiato e archiviato nel database con il nome "PointSource".</span><span class="sxs-lookup"><span data-stu-id="adddb-122">This copies the text contained in the Point.cs file and stores it in the database under the name "PointSource".</span></span>  
  
 `ALTER ASSEMBLY Point`  
  
 `ADD FILE FROM 'C:\Projects\Point\Point.cs' AS PointSource`  
  
## <a name="see-also"></a><span data-ttu-id="adddb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adddb-123">See Also</span></span>  
 <span data-ttu-id="adddb-124">[Gestione degli assembly di integrazione CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="adddb-124">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="adddb-125">[Creazione di un assembly](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="adddb-125">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="adddb-126">[Eliminazione di un assembly](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="adddb-126">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 [<span data-ttu-id="adddb-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="adddb-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
  
