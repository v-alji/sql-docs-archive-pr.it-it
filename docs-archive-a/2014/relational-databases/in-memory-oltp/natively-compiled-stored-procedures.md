---
title: Stored procedure compilate in modo nativo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- natively compiled stored procedures
ms.assetid: d5ed432c-10c5-4e4f-883c-ef4d1fa32366
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b8fb7a379c0c08ca357baa1042ebcf51c512c9ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722815"
---
# <a name="natively-compiled-stored-procedures"></a><span data-ttu-id="96636-102">stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="96636-102">Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="96636-103">Le stored procedure compilate in modo nativo sono stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] compilate nel codice nativo che accedono a tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="96636-103">Natively compiled stored procedures are [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures compiled to native code that access memory-optimized tables.</span></span> <span data-ttu-id="96636-104">Le stored procedure compilate in modo nativo consentono un'esecuzione efficiente delle query e della logica di business nella stored procedure.</span><span class="sxs-lookup"><span data-stu-id="96636-104">Natively compiled stored procedures allow for efficient execution of queries and business logic in the stored procedure.</span></span> <span data-ttu-id="96636-105">Per altri dettagli sul processo di compilazione nativa, vedere [Compilazione nativa di tabelle e stored procedure](native-compilation-of-tables-and-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="96636-105">For more details about the native compilation process, see [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span></span> <span data-ttu-id="96636-106">Per altre informazioni sulla migrazione delle stored procedure basate su disco alle stored procedure compilate in modo nativo, vedere [Problemi di migrazione relativi alle stored procedure compilate in modo nativo](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="96636-106">For more information about migrating disk-based stored procedures to natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96636-107">Una differenza tra le stored procedure interpretate (basate su disco) e le stored procedure compilate in modo nativo consiste nel fatto che una stored procedure interpretata viene compilata alla prima esecuzione mentre una stored procedure compilata in modo nativo viene compilata alla creazione.</span><span class="sxs-lookup"><span data-stu-id="96636-107">One difference between interpreted (disk-based) stored procedures and natively compiled stored procedures is that an interpreted stored procedure is compiled at first execution whereas a natively compiled stored procedure is compiled when it is created.</span></span> <span data-ttu-id="96636-108">Con le stored procedure compilate in modo nativo, molte condizioni di errore (overflow aritmetico, conversione dei tipi e alcune condizioni di divisione per zero) possono essere rilevate al momento della creazione e causano l'esito negativo della creazione della stored procedure compilata in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="96636-108">With natively compiled stored procedures, many error conditions (arithmetic overflow, type conversion, and some divide-by-zero conditions) can be detected at create time and will cause creation of the natively compiled stored procedure to fail.</span></span> <span data-ttu-id="96636-109">Con le stored procedure interpretate, queste condizioni di errore in genere non causano errori alla creazione della stored procedure, ma tutte le esecuzioni avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="96636-109">With interpreted stored procedures, these error conditions will typically not cause a failure when the stored procedure is created, but all executions will fail.</span></span>  
  
 <span data-ttu-id="96636-110">Contenuto della sezione:</span><span class="sxs-lookup"><span data-stu-id="96636-110">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="96636-111">Creazione di stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="96636-111">Creating Natively Compiled Stored Procedures</span></span>](creating-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="96636-112">Blocchi atomici</span><span class="sxs-lookup"><span data-stu-id="96636-112">Atomic Blocks</span></span>](atomic-blocks-in-native-procedures.md)  
  
-   [<span data-ttu-id="96636-113">Costrutti supportati in stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="96636-113">Supported Constructs in Natively Compiled Stored Procedures</span></span>](supported-features-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="96636-114">Utilizzo di try...catch in stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="96636-114">Using Try..Catch in Natively Compiled Stored Procedures</span></span>](../../database-engine/using-try-catch-in-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="96636-115">Costrutti supportati su stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="96636-115">Supported Constructs on Natively Compiled Stored Procedures</span></span>](supported-ddl-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="96636-116">Stored procedure compilate in modo nativo e opzioni SET di esecuzione</span><span class="sxs-lookup"><span data-stu-id="96636-116">Natively Compiled Stored Procedures and Execution Set Options</span></span>](natively-compiled-stored-procedures-and-execution-set-options.md)  
  
-   [<span data-ttu-id="96636-117">Procedure consigliate per chiamare stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="96636-117">Best Practices for Calling Natively Compiled Stored Procedures</span></span>](best-practices-for-calling-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="96636-118">Monitoraggio delle prestazioni di stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="96636-118">Monitoring Performance of Natively Compiled Stored Procedures</span></span>](monitoring-performance-of-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="96636-119">Chiamata di stored procedure compilate in modo nativo da applicazioni di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="96636-119">Calling Natively Compiled Stored Procedures from Data Access Applications</span></span>](calling-natively-compiled-stored-procedures-from-data-access-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="96636-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96636-120">See Also</span></span>  
 [<span data-ttu-id="96636-121">Tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="96636-121">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
