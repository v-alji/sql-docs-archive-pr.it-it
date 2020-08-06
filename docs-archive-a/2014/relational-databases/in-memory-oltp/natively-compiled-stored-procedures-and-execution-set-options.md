---
title: Stored procedure compilate in modo nativo e opzioni SET di esecuzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c1869cf7-9030-4d18-85d6-0e419a4e9af7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 264a2b3ab1e6f3f0bda97bfe89a4438aa641577d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725751"
---
# <a name="natively-compiled-stored-procedures-and-execution-set-options"></a><span data-ttu-id="ba100-102">Stored procedure compilate in modo nativo e opzioni SET di esecuzione</span><span class="sxs-lookup"><span data-stu-id="ba100-102">Natively Compiled Stored Procedures and Execution Set Options</span></span>
  <span data-ttu-id="ba100-103">Le opzioni di sessione sono fisse nei blocchi atomici.</span><span class="sxs-lookup"><span data-stu-id="ba100-103">Session options are fixed in atomic blocks.</span></span> <span data-ttu-id="ba100-104">L'esecuzione di una stored procedure non è interessata dalle opzioni SET di una sessione.</span><span class="sxs-lookup"><span data-stu-id="ba100-104">A stored procedure's execution is not affected by a session's SET options.</span></span> <span data-ttu-id="ba100-105">Tuttavia, alcune opzioni SET quali SET NOEXEC e SET SHOWPLAN_XML impediscono l'esecuzione delle stored procedure, incluse quelle compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="ba100-105">However, certain SET options, such as SET NOEXEC and SET SHOWPLAN_XML, cause stored procedures (including natively compiled stored procedures) to not execute.</span></span>  
  
 <span data-ttu-id="ba100-106">Quando una stored procedure compilata in modo nativo viene eseguita con una qualsiasi opzione STATISTICS attivata, le statistiche vengono raccolte per la stored procedure completa e non per istruzione.</span><span class="sxs-lookup"><span data-stu-id="ba100-106">When a natively compiled stored procedure is executed with any STATISTICS option turned on, statistics are gathered for the procedure as a whole and not per statement.</span></span> <span data-ttu-id="ba100-107">Per altre informazioni, vedere [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql) e [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba100-107">For more information, see [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql), and [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span></span> <span data-ttu-id="ba100-108">Per ottenere statistiche di esecuzione a livello di singola istruzione in stored procedure compilate in modo nativo, utilizzare una sessione Evento esteso in un evento sp_statement_completed, che viene attivato al completamento di ciascuna singola query nell'esecuzione di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="ba100-108">To obtain execution statistics on a per-statement level in natively compiled stored procedures, use an Extended Event session on the sp_statement_completed event, which starts when each individual query in a stored procedures execution completes.</span></span> <span data-ttu-id="ba100-109">Per altre informazioni sulla creazione di sessioni di evento estesi, vedere [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba100-109">For more information on creating Extended Event sessions, see [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span></span>  
  
 <span data-ttu-id="ba100-110">`SHOWPLAN_XML` è supportato per le stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="ba100-110">`SHOWPLAN_XML` is supported for natively compiled stored procedures.</span></span> <span data-ttu-id="ba100-111">Le opzioni `SHOWPLAN_ALL` e `SHOWPLAN_TEXT` non sono supportate con le stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="ba100-111">`SHOWPLAN_ALL` and `SHOWPLAN_TEXT` are not supported with natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="ba100-112">L'opzione `SET FMTONLY` non è supportata con le stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="ba100-112">`SET FMTONLY` in not supported with natively compiled stored procedures.</span></span> <span data-ttu-id="ba100-113">Usare invece [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba100-113">Use [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba100-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba100-114">See Also</span></span>  
 [<span data-ttu-id="ba100-115">Stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="ba100-115">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
