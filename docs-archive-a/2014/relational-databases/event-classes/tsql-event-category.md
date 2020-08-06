---
title: Categoria di eventi TSQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, TSQL event category
- TSQL event category [SQL Server]
- event classes [SQL Server], TSQL event category
ms.assetid: 215f8747-64b5-4bf3-9845-d476b10cda3a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 763d5f31fd3562f54b274a74324ed4715b623a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711963"
---
# <a name="tsql-event-category"></a><span data-ttu-id="f5bcd-102">Categoria di eventi TSQL</span><span class="sxs-lookup"><span data-stu-id="f5bcd-102">TSQL Event Category</span></span>
  <span data-ttu-id="f5bcd-103">La categoria di eventi **TSQL** include eventi TSQL generali.</span><span class="sxs-lookup"><span data-stu-id="f5bcd-103">The **TSQL** event category contains general TSQL events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5bcd-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f5bcd-104">In This Section</span></span>  
  
|<span data-ttu-id="f5bcd-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="f5bcd-105">Topic</span></span>|<span data-ttu-id="f5bcd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5bcd-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f5bcd-107">Classe di evento Exec Prepared SQL</span><span class="sxs-lookup"><span data-stu-id="f5bcd-107">Exec Prepared SQL Event Class</span></span>](exec-prepared-sql-event-class.md)|<span data-ttu-id="f5bcd-108">Indica che SqlClient, ODBC, OLE DB o DB-Library ha eseguito una o più istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] preparate.</span><span class="sxs-lookup"><span data-stu-id="f5bcd-108">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has executed a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="f5bcd-109">Classe di evento Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="f5bcd-109">Prepare SQL Event Class</span></span>](prepare-sql-event-class.md)|<span data-ttu-id="f5bcd-110">Indica che SqlClient, ODBC, OLE DB o DB-Library ha preparato una o più istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f5bcd-110">Indicates that SqlClient, ODBC, OLE DB, or DB-Library has prepared a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements for use.</span></span>|  
|[<span data-ttu-id="f5bcd-111">Classe di evento SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="f5bcd-111">SQL:BatchCompleted Event Class</span></span>](sql-batchcompleted-event-class.md)|<span data-ttu-id="f5bcd-112">Indica il completamento del batch [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5bcd-112">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch has completed.</span></span>|  
|[<span data-ttu-id="f5bcd-113">Classe di evento SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="f5bcd-113">SQL:BatchStarting Event Class</span></span>](sql-batchstarting-event-class.md)|<span data-ttu-id="f5bcd-114">Indica l'avvio del batch [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5bcd-114">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch is starting.</span></span>|  
|[<span data-ttu-id="f5bcd-115">Classe di evento SQL:StmtCompleted</span><span class="sxs-lookup"><span data-stu-id="f5bcd-115">SQL:StmtCompleted Event Class</span></span>](sql-stmtcompleted-event-class.md)|<span data-ttu-id="f5bcd-116">Indica il completamento di un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5bcd-116">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement has completed.</span></span>|  
|[<span data-ttu-id="f5bcd-117">Classe di evento SQL:StmtRecompile</span><span class="sxs-lookup"><span data-stu-id="f5bcd-117">SQL:StmtRecompile Event Class</span></span>](sql-stmtrecompile-event-class.md)|<span data-ttu-id="f5bcd-118">Indica ricompilazioni a livello di istruzioni, provocate da tutti i tipi di batch, ovvero stored procedure, trigger, batch ad hoc e query.</span><span class="sxs-lookup"><span data-stu-id="f5bcd-118">Indicates statement-level recompilations caused by all types of batches: stored procedures, triggers, ad hoc batches, and queries.</span></span>|  
|[<span data-ttu-id="f5bcd-119">Classe di evento SQL:StmtStarting</span><span class="sxs-lookup"><span data-stu-id="f5bcd-119">SQL:StmtStarting Event Class</span></span>](sql-stmtstarting-event-class.md)|<span data-ttu-id="f5bcd-120">Indica l'avvio di un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5bcd-120">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is starting.</span></span>|  
|[<span data-ttu-id="f5bcd-121">Classe di evento Unprepare SQL</span><span class="sxs-lookup"><span data-stu-id="f5bcd-121">Unprepare SQL Event Class</span></span>](unprepare-sql-event-class.md)|<span data-ttu-id="f5bcd-122">Indica che SqlClient, ODBC, OLE DB o DB-Library ha eliminato una o più istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] preparate.</span><span class="sxs-lookup"><span data-stu-id="f5bcd-122">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has deleted a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="f5bcd-123">Classe di evento XQuery Static Type</span><span class="sxs-lookup"><span data-stu-id="f5bcd-123">XQuery Static Type Event Class</span></span>](xquery-static-type-event-class.md)|<span data-ttu-id="f5bcd-124">Viene generato quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue un'espressione XQuery.</span><span class="sxs-lookup"><span data-stu-id="f5bcd-124">Occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes an XQuery expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5bcd-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5bcd-125">See Also</span></span>  
 [<span data-ttu-id="f5bcd-126">Guida di riferimento a Transact-SQL &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="f5bcd-126">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
