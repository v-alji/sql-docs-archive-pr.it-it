---
title: Costrutti supportati su stored procedure compilate in modo nativo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 6b21f47e-bceb-4054-8b3c-9d39bb9583c0
author: rothja
ms.author: jroth
ms.openlocfilehash: f3bc7e28fa2a868ac39c6adbb2dea3cc5c3ace73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627258"
---
# <a name="supported-constructs-on-natively-compiled-stored-procedures"></a><span data-ttu-id="5954f-102">Costrutti supportati su stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="5954f-102">Supported Constructs on Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="5954f-103">In questo argomento vengono illustrati i costrutti supportati nelle stored procedure compilate in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="5954f-103">This topic lists the supported constructs on natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="5954f-104">Per altre informazioni su costrutti non supportati, vedere [Costrutti Transact-SQL non supportati da OLTP in memoria](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="5954f-104">For information about unsupported constructs, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="procedure-ddl"></a><span data-ttu-id="5954f-105">DLL di procedura</span><span class="sxs-lookup"><span data-stu-id="5954f-105">Procedure DDL</span></span>  
 <span data-ttu-id="5954f-106">Sono supportati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5954f-106">The following are supported:</span></span>  
  
-   <span data-ttu-id="5954f-107">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="5954f-107">CREATE PROCEDURE</span></span>  
  
-   <span data-ttu-id="5954f-108">DROP PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="5954f-108">DROP PROCEDURE</span></span>  
  
-   <span data-ttu-id="5954f-109">SCHEMABINDING (obbligatorio per le stored procedure compilate in modo nativo)</span><span class="sxs-lookup"><span data-stu-id="5954f-109">SCHEMABINDING (required for natively compiled stored procedures)</span></span>  
  
-   <span data-ttu-id="5954f-110">NATIVE_COMPILATION</span><span class="sxs-lookup"><span data-stu-id="5954f-110">NATIVE_COMPILATION</span></span>  
  
-   <span data-ttu-id="5954f-111">I parametri possono essere dichiarati come NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="5954f-111">Parameters can be declared as NOT NULL.</span></span>  
  
-   <span data-ttu-id="5954f-112">Parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="5954f-112">Table-valued parameters.</span></span>  
  
## <a name="security"></a><span data-ttu-id="5954f-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5954f-113">Security</span></span>  
 <span data-ttu-id="5954f-114">Sono supportati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5954f-114">The following are supported:</span></span>  
  
-   <span data-ttu-id="5954f-115">Per le procedure: EXECUTE AS OWNER, SELF e utente.</span><span class="sxs-lookup"><span data-stu-id="5954f-115">For procedures: EXECUTE AS OWNER, SELF, and user.</span></span>  
  
-   <span data-ttu-id="5954f-116">Autorizzazioni GRANT e DENY per tabelle e procedure.</span><span class="sxs-lookup"><span data-stu-id="5954f-116">GRANT and DENY permissions on tables and procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5954f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5954f-117">See Also</span></span>  
 [<span data-ttu-id="5954f-118">Stored procedure compilate in modo nativo</span><span class="sxs-lookup"><span data-stu-id="5954f-118">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
