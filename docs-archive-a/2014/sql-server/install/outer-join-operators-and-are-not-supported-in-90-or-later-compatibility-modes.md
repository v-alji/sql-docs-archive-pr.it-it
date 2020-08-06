---
title: Gli operatori outer join *= e =* non sono supportati in modalità di compatibilità 90 o successive | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- =* join
- '*= join'
- joins [SQL Server]
ms.assetid: ca4aa11f-1048-411f-9c6c-3d0a8e319f2f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 357c729e6d53cc17f2e4c169dd66613b6cfd2f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720867"
---
# <a name="outer-join-operators--and--are-not-supported-in-90-or-later-compatibility-modes"></a><span data-ttu-id="95254-102">Gli operatori di outer join \*= e =\* non sono supportati in modalità di compatibilità 90 o successiva</span><span class="sxs-lookup"><span data-stu-id="95254-102">Outer join operators \*= and =\* are not supported in 90 or later compatibility modes</span></span>
  <span data-ttu-id="95254-103">È stato rilevato l'utilizzo di outer join Operators \* = e = \* .</span><span class="sxs-lookup"><span data-stu-id="95254-103">Upgrade Advisor detected the use of outer join operators \*= and =\*.</span></span> <span data-ttu-id="95254-104">Tali operatori non sono supportati nella modalità di compatibilità 90 o successiva</span><span class="sxs-lookup"><span data-stu-id="95254-104">These operators are not supported in 90 or later compatibility modes.</span></span> <span data-ttu-id="95254-105">Quando si esegue l'aggiornamento, la modalità di compatibilità dei database utente non cambia.</span><span class="sxs-lookup"><span data-stu-id="95254-105">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="95254-106">Le istruzioni in cui sono utilizzati questi operatori non riusciranno.</span><span class="sxs-lookup"><span data-stu-id="95254-106">Statements that use these operators will fail.</span></span>  
  
## <a name="component"></a><span data-ttu-id="95254-107">Componente</span><span class="sxs-lookup"><span data-stu-id="95254-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="95254-108">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="95254-108">Corrective Action</span></span>  
 <span data-ttu-id="95254-109">Prima di modificare la modalità di compatibilità del database con 90 o versioni successive, modificare le istruzioni che usano gli operatori outer join \* = e = \* per usare parole chiave outer join equivalenti.</span><span class="sxs-lookup"><span data-stu-id="95254-109">Before you change the database compatibility mode to 90 or later, modify statements that use the outer join operators \*= and =\* to use equivalent OUTER JOIN keywords.</span></span> <span data-ttu-id="95254-110">Nell'esempio seguente vengono illustrate una query che utilizza l'operatore `\*=` e una query equivalente che utilizza le parole chiave `LEFT OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="95254-110">The following example shows a query that uses the `\*=` operator and an equivalent query that uses the `LEFT OUTER JOIN` keywords.</span></span>  
  
```  
-- This query uses an old-style outer join operator.  
USE pubs  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee, jobs   
WHERE employee.job_id *= jobs.job_id  
ORDER BY employee.job_id  
  
-- This query uses the ANSI standard keywords LEFT OUTER JOIN.  
USE pubs;  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
ORDER BY employee.job_id  
```  
  
 <span data-ttu-id="95254-111">Per ulteriori informazioni sugli outer join, vedere "Utilizzo di outer join" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95254-111">For more information about outer joins, see "Using Outer Joins" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95254-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95254-112">See Also</span></span>  
 <span data-ttu-id="95254-113">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="95254-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="95254-114">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="95254-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
