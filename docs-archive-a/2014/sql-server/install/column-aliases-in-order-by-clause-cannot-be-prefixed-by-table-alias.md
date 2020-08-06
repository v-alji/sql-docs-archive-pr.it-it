---
title: Gli alias di colonna nella clausola ORDER BY non possono essere preceduti dall'alias di tabella | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], columns
ms.assetid: fee7328f-6e8d-4005-930b-56fb6f17e0b2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 44333d778753a2f8761d32d181681b798e3bc409
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628199"
---
# <a name="column-aliases-in-order-by-clause-cannot-be-prefixed-by-table-alias"></a><span data-ttu-id="73dc0-102">Gli alias di colonna utilizzati nella clausola ORDER BY non possono essere preceduti dall'alias della tabella</span><span class="sxs-lookup"><span data-stu-id="73dc0-102">Column aliases in ORDER BY clause cannot be prefixed by table alias</span></span>
  <span data-ttu-id="73dc0-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o versioni successiva gli alias di colonna utilizzati nella clausola ORDER BY non possono essere preceduti dall'alias della tabella.</span><span class="sxs-lookup"><span data-stu-id="73dc0-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, column aliases in the ORDER BY clause cannot be prefixed by the table alias.</span></span>  
  
## <a name="component"></a><span data-ttu-id="73dc0-104">Componente</span><span class="sxs-lookup"><span data-stu-id="73dc0-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="73dc0-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73dc0-105">Description</span></span>  
 <span data-ttu-id="73dc0-106">Ad esempio, la query seguente viene eseguita in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], ma restituisce un errore in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="73dc0-106">For example, the following query executes in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but returns an error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.l  
```  
  
 <span data-ttu-id="73dc0-107">Il [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] non associa `p.l` nella clausola `ORDER BY` a una colonna valida nella tabella.</span><span class="sxs-lookup"><span data-stu-id="73dc0-107">The [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] does not match `p.l` in the `ORDER BY` clause to a valid column in the table.</span></span>  
  
### <a name="exception"></a><span data-ttu-id="73dc0-108">Eccezione</span><span class="sxs-lookup"><span data-stu-id="73dc0-108">Exception</span></span>  
 <span data-ttu-id="73dc0-109">Se l'alias di colonna con prefisso specificato nella clausola ORDER BY è un nome di colonna valido nella tabella specificata, la query viene eseguita senza errori. In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] la semantica dell'istruzione potrebbe essere diversa.</span><span class="sxs-lookup"><span data-stu-id="73dc0-109">If the prefixed column alias that is specified in the ORDER BY clause is a valid column name in the specified table, the query executes without error; in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the semantics of the statement might be different.</span></span> <span data-ttu-id="73dc0-110">Ad esempio, l'alias di colonna (`id`) specificato nell'istruzione seguente è un nome di colonna valido nella tabella `sysobjects`.</span><span class="sxs-lookup"><span data-stu-id="73dc0-110">For example, the column alias (`id`) specified in the following statement is a valid column name in the `sysobjects` table.</span></span> <span data-ttu-id="73dc0-111">Quando l'istruzione viene eseguita in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], l'operazione `CAST` viene eseguita dopo l'ordinamento del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="73dc0-111">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], when the statement executes, the `CAST` operation is performed after the result set is sorted.</span></span> <span data-ttu-id="73dc0-112">Questo significa che nell'operazione di ordinamento viene utilizzata la colonna `name`.</span><span class="sxs-lookup"><span data-stu-id="73dc0-112">This means the `name` column is used in the sort operation.</span></span> <span data-ttu-id="73dc0-113">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] l'operazione `CAST` viene eseguita prima dell'operazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="73dc0-113">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the `CAST` operation occurs before the sort operation.</span></span> <span data-ttu-id="73dc0-114">Questo significa che nell'operazione di ordinamento viene utilizzata la colonna `id` nelle tabelle e il set di risultati viene restituito in un ordine imprevisto.</span><span class="sxs-lookup"><span data-stu-id="73dc0-114">This means the `id` column in the table is used in the sort operation and returns the result set in an unexpected order.</span></span>  
  
```  
SELECT CAST (o.name AS char(128)) AS id  
FROM sysobjects AS o  
ORDER BY o.id;  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="73dc0-115">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="73dc0-115">Corrective Action</span></span>  
 <span data-ttu-id="73dc0-116">Modificare le query che utilizzano alias di colonna preceduti da alias di tabella nella clausola ORDER BY in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="73dc0-116">Modify queries that use column aliases prefixed by table aliases in the ORDER BY clause in either of the following ways:</span></span>  
  
-   <span data-ttu-id="73dc0-117">Se possibile, evitare di aggiungere un prefisso all'alias di colonna nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="73dc0-117">Do not prefix the column alias in the ORDER BY clause, if possible.</span></span>  
  
-   <span data-ttu-id="73dc0-118">Sostituire l'alias di colonna con il nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="73dc0-118">Replace the column alias with the column name.</span></span>  
  
 <span data-ttu-id="73dc0-119">Ad esempio, le due query seguenti vengono eseguite senza errori in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="73dc0-119">For example, both of the following queries execute without error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY l  
  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.LastName  
```  
  
## <a name="see-also"></a><span data-ttu-id="73dc0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73dc0-120">See Also</span></span>  
 <span data-ttu-id="73dc0-121">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="73dc0-121">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="73dc0-122">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="73dc0-122">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
