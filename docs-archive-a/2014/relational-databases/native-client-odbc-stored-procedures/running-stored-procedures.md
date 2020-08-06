---
title: Esecuzione di stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- stored procedures [ODBC], running
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], executing
ms.assetid: 866b6dd3-2acd-4dfb-aeca-a0352b2d4c6a
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e5de6a9a13c95b417657a1d108403fa27abe34b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725627"
---
# <a name="running-stored-procedures"></a><span data-ttu-id="7692a-102">Esecuzione delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="7692a-102">Running Stored Procedures</span></span>
  <span data-ttu-id="7692a-103">Una stored procedure è un oggetto eseguibile archiviato in un database.</span><span class="sxs-lookup"><span data-stu-id="7692a-103">A stored procedure is an executable object stored in a database.</span></span> <span data-ttu-id="7692a-104">Supporti [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7692a-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports:</span></span>  
  
-   <span data-ttu-id="7692a-105">Stored procedure:</span><span class="sxs-lookup"><span data-stu-id="7692a-105">Stored procedures:</span></span>  
  
     <span data-ttu-id="7692a-106">Una o più istruzioni SQL precompilate in una sola stored procedure eseguibile.</span><span class="sxs-lookup"><span data-stu-id="7692a-106">One or more SQL statements precompiled into a single executable procedure.</span></span>  
  
-   <span data-ttu-id="7692a-107">Stored procedure estese:</span><span class="sxs-lookup"><span data-stu-id="7692a-107">Extended stored procedures:</span></span>  
  
     <span data-ttu-id="7692a-108">DLL C o C++ scritte nell'API ODS di SQL Server per le stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="7692a-108">C or C++ dynamic-link libraries (DLL) written to the SQL Server Open Data Services API for extended stored procedures.</span></span> <span data-ttu-id="7692a-109">L'API ODS amplia le funzionalità delle stored procedure per includere il codice C o C++.</span><span class="sxs-lookup"><span data-stu-id="7692a-109">The Open Data Services API extends the capabilities of stored procedures to include C or C++ code.</span></span>  
  
 <span data-ttu-id="7692a-110">Durante l'esecuzione delle istruzioni, la chiamata a una stored procedure sull'origine dati, in alternativa all'esecuzione o alla preparazione diretta di un'istruzione nell'applicazione client, può offrire:</span><span class="sxs-lookup"><span data-stu-id="7692a-110">When executing statements, calling a stored procedure on the data source (instead of directly executing or preparing a statement in the client application) can provide:</span></span>  
  
-   <span data-ttu-id="7692a-111">Prestazioni più elevate</span><span class="sxs-lookup"><span data-stu-id="7692a-111">Higher performance</span></span>  
  
     <span data-ttu-id="7692a-112">Le istruzioni SQL vengono analizzate e compilate durante la creazione delle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7692a-112">SQL statements are parsed and compiled when procedures are created.</span></span> <span data-ttu-id="7692a-113">Questo overhead viene quindi salvato durante l'esecuzione delle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7692a-113">This overhead is then saved when the procedures are executed.</span></span>  
  
-   <span data-ttu-id="7692a-114">Overhead di rete ridotto</span><span class="sxs-lookup"><span data-stu-id="7692a-114">Reduced network overhead</span></span>  
  
     <span data-ttu-id="7692a-115">L'esecuzione di una stored procedure in alternativa all'invio di query complesse in rete può ridurre il traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="7692a-115">Executing a procedure instead of sending complex queries across the network can reduce network traffic.</span></span> <span data-ttu-id="7692a-116">Se un'applicazione ODBC utilizza la sintassi ODBC {CALL} per eseguire una stored procedure, il driver ODBC esegue ulteriori ottimizzazioni che eliminano la necessità di convertire i dati dei parametri.</span><span class="sxs-lookup"><span data-stu-id="7692a-116">If an ODBC application uses the ODBC { CALL } syntax to execute a stored procedure, the ODBC driver makes additional optimizations that eliminate the need to convert parameter data.</span></span>  
  
-   <span data-ttu-id="7692a-117">Maggiore coerenza</span><span class="sxs-lookup"><span data-stu-id="7692a-117">Greater consistency</span></span>  
  
     <span data-ttu-id="7692a-118">Se le regole di un'organizzazione vengono implementate in una risorsa centrale, ad esempio una stored procedure, possono essere codificate, testate e sottoposte a debug una volta.</span><span class="sxs-lookup"><span data-stu-id="7692a-118">If an organization's rules are implemented in a central resource, such as a stored procedure, they can be coded, tested, and debugged once.</span></span> <span data-ttu-id="7692a-119">I singoli programmatori possono quindi utilizzare le stored procedure testate anziché sviluppare implementazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7692a-119">Individual programmers can then use the tested stored procedures instead of developing their own implementations.</span></span>  
  
-   <span data-ttu-id="7692a-120">Maggiore precisione</span><span class="sxs-lookup"><span data-stu-id="7692a-120">Greater accuracy</span></span>  
  
     <span data-ttu-id="7692a-121">Poiché le stored procedure vengono in genere sviluppate da programmatori esperti, sono più efficienti e contengono un numero di errori inferiore rispetto al codice sviluppato più volte da programmatori meno competenti.</span><span class="sxs-lookup"><span data-stu-id="7692a-121">Because stored procedures are usually developed by experienced programmers, they tend to be more efficient and have fewer errors than code developed multiple times by programmers of varying skill levels.</span></span>  
  
-   <span data-ttu-id="7692a-122">Maggior numero di funzionalità</span><span class="sxs-lookup"><span data-stu-id="7692a-122">Added functionality</span></span>  
  
     <span data-ttu-id="7692a-123">Le stored procedure estese possono utilizzare le caratteristiche C e C++ non disponibili nelle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7692a-123">Extended stored procedures can use C and C++ features not available in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="7692a-124">Per un esempio di come chiamare una stored procedure, vedere [elaborare i codici restituiti e i parametri di Output &#40;&#41;ODBC ](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7692a-124">For an example of how to call a stored procedure, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7692a-125">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7692a-125">In This Section</span></span>  
  
-   [<span data-ttu-id="7692a-126">Chiamata di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="7692a-126">Calling a Stored Procedure</span></span>](calling-a-stored-procedure.md)  
  
-   [<span data-ttu-id="7692a-127">Invio in batch di chiamate a stored procedure</span><span class="sxs-lookup"><span data-stu-id="7692a-127">Batching Stored Procedure Calls</span></span>](batching-stored-procedure-calls.md)  
  
-   [<span data-ttu-id="7692a-128">Risultati dell'elaborazione delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="7692a-128">Processing Stored Procedure Results</span></span>](processing-stored-procedure-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="7692a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7692a-129">See Also</span></span>  
 <span data-ttu-id="7692a-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="7692a-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="7692a-131">Procedure per l'esecuzione di stored procedure &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="7692a-131">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
  
