---
title: Le query FOR XML AUTO restituiscono riferimenti a tabelle derivate in modalità di compatibilità 90 o successive | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FOR XML AUTO [SQL Server]
ms.assetid: 10c32f06-f7e1-40e0-8f79-6d921f2bef1d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 702cb2ca1d437dff03cee09c98d72082500709d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638257"
---
# <a name="for-xml-auto-queries-return-derived-table-references-in-90-or-later-compatibility-modes"></a><span data-ttu-id="845f2-102">In modalità di compatibilità 90 o successiva le query FOR XML AUTO restituiscono riferimenti a tabelle derivate</span><span class="sxs-lookup"><span data-stu-id="845f2-102">FOR XML AUTO queries return derived table references in 90 or later compatibility modes</span></span>
  <span data-ttu-id="845f2-103">Quando il livello di compatibilità del database è impostato su 90 o successivo, le query FOR XML eseguite in modalità AUTO restituiscono riferimenti ad alias di tabelle derivate.</span><span class="sxs-lookup"><span data-stu-id="845f2-103">When the database compatibility level is set to 90 or later, FOR XML queries that execute in AUTO mode return references to derived table aliases.</span></span> <span data-ttu-id="845f2-104">Quando il livello di compatibilità è impostato su 80, le query FOR XML AUTO restituiscono riferimenti alle tabelle di base che definiscono una tabella derivata.</span><span class="sxs-lookup"><span data-stu-id="845f2-104">When the compatibility level is set to 80, FOR XML AUTO queries return references to the base tables that define a derived table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="845f2-105">Componente</span><span class="sxs-lookup"><span data-stu-id="845f2-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="845f2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="845f2-106">Description</span></span>  
 <span data-ttu-id="845f2-107">Si consideri ad esempio la tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="845f2-107">For example, consider the following table:</span></span>  
  
```  
CREATE TABLE Test(id int);  
INSERT INTO Test VALUES(1);  
INSERT INTO Test VALUES(2);  
```  
  
 <span data-ttu-id="845f2-108">La query seguente, che include una tabella derivata, produce risultati diversi con i livelli di compatibilità 80, 90 o successivo:</span><span class="sxs-lookup"><span data-stu-id="845f2-108">The following query, which includes a derived table, produces different results under compatibility levels 80, 90, or later:</span></span>  
  
```  
SELECT * FROM   
   (SELECT a.id AS a, b.id AS b   
    FROM Test a JOIN Test b ON a.id=b.id)  
AS DerivedTest   
FOR XML AUTO;  
```  
  
 <span data-ttu-id="845f2-109">Con il livello di compatibilità 80, la query restituisce i risultati seguenti.</span><span class="sxs-lookup"><span data-stu-id="845f2-109">Under compatibility level 80, the query returns the following results.</span></span> <span data-ttu-id="845f2-110">I risultati fanno riferimento agli alias delle tabelle di base `a` e `b` della tabella derivata anziché all'alias della tabella derivata.</span><span class="sxs-lookup"><span data-stu-id="845f2-110">The results reference the base table aliases `a` and `b` of the derived table instead of the derived table alias.</span></span>  
  
```  
<a a="1"><b b="1"/></a><a a="2"><b b="2"/></a>  
```  
  
 <span data-ttu-id="845f2-111">Con il livello di compatibilità 90 o successivo, la query restituisce i riferimenti all'alias della tabella derivata `DerivedTest` anziché alle tabelle di base della tabella derivata.</span><span class="sxs-lookup"><span data-stu-id="845f2-111">Under compatibility level 90 or later, the query returns references to the derived table alias `DerivedTest` instead of to the derived table's base tables.</span></span>  
  
```  
<DerivedTest a="1" b="1"/><DerivedTest a="2" b="2"/>  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="845f2-112">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="845f2-112">Corrective Action</span></span>  
 <span data-ttu-id="845f2-113">Apportare le modifiche necessarie all'applicazione in base alle modifiche dei risultati delle query FOR XML AUTO che includono tabelle derivate e che vengono eseguite con il livello di compatibilità 90 o successivo.</span><span class="sxs-lookup"><span data-stu-id="845f2-113">Modify your application as required to account for the changes in results of FOR XML AUTO queries that include derived tables and that run under compatibility level 90 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="845f2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="845f2-114">See Also</span></span>  
 <span data-ttu-id="845f2-115">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="845f2-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="845f2-116">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="845f2-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
