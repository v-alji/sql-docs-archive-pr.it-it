---
title: Oggetto SqlTriggerContext | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlTriggerContext object
- triggers [CLR integration]
- context [CLR integration]
ms.assetid: 472a2d0b-64ae-4877-8f11-a5620aa698b7
author: rothja
ms.author: jroth
ms.openlocfilehash: f7eae3d290a70bedee0ed9badf9e6d0503caa2bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725991"
---
# <a name="sqltriggercontext-object"></a><span data-ttu-id="99209-102">Oggetto SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="99209-102">SqlTriggerContext Object</span></span>
  <span data-ttu-id="99209-103">La classe `SqlTriggerContext` fornisce informazioni sul contesto per il trigger.</span><span class="sxs-lookup"><span data-stu-id="99209-103">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="99209-104">Tali informazioni includono il tipo di azione che ha provocato l'attivazione del trigger, le colonne modificate in un'operazione UPDATE e, nel caso di un trigger DDL, una struttura XML `EventData` che descrive l'operazione di attivazione del trigger.</span><span class="sxs-lookup"><span data-stu-id="99209-104">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a data definition language (DDL) trigger, an XML `EventData` structure that describes the triggering operation.</span></span> <span data-ttu-id="99209-105">Per altre informazioni ed esempi su come usare la `SqlTriggerContext` classe, vedere [trigger CLR](../../database-engine/dev-guide/clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="99209-105">For more information and examples of how to use the `SqlTriggerContext` class, see [CLR Triggers](../../database-engine/dev-guide/clr-triggers.md).</span></span>  
  
 <span data-ttu-id="99209-106">Per ulteriori informazioni, vedere la documentazione di riferimento sulla classe `Microsoft.SqlServer.Server.SqlTriggerContext` nella documentazione di .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="99209-106">For more information, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the .NET Framework SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99209-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99209-107">See Also</span></span>  
 <span data-ttu-id="99209-108">[Trigger CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="99209-108">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="99209-109">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="99209-109">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
