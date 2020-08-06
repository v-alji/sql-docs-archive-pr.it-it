---
title: La nuova colonna nell'output di sp_helptrigger può influisca sulle applicazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sp_helptrigger
ms.assetid: b7c42a8f-f2e0-4fa3-b046-3cf39c854c47
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b1f5e936843ed84a5c6b88e2f3685e7a4272bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637024"
---
# <a name="new-column-in-output-of-sp_helptrigger-may-impact-applications"></a><span data-ttu-id="82682-102">La nuova colonna nell'output di sp_helptrigger potrebbe influire sulle applicazioni</span><span class="sxs-lookup"><span data-stu-id="82682-102">New column in output of sp_helptrigger may impact applications</span></span>
  <span data-ttu-id="82682-103">trigger_schemaias l'ultima colonna del set di risultati restituito dalla stored procedure di sistema di sp_helptrigger.</span><span class="sxs-lookup"><span data-stu-id="82682-103">trigger_schemaias the last column in the result set returned by the sp_helptrigger system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="82682-104">Per ottenere informazioni sui trigger definiti in una specifica tabella, eseguire una query sulla vista del catalogo sys.triggers.</span><span class="sxs-lookup"><span data-stu-id="82682-104">To obtain information about triggers defined on a particular table, query the sys.triggers catalog view.</span></span>  
  
## <a name="component"></a><span data-ttu-id="82682-105">Componente</span><span class="sxs-lookup"><span data-stu-id="82682-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="82682-106">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="82682-106">Corrective Action</span></span>  
 <span data-ttu-id="82682-107">Esaminare l'utilizzo di sp_helptrigger nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="82682-107">Review the use of sp_helptrigger in applications.</span></span> <span data-ttu-id="82682-108">Può essere necessario modificare le applicazioni in modo da gestire la colonna aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="82682-108">You may need to modify your applications to accommodate the additional column.</span></span> <span data-ttu-id="82682-109">In alternativa, è possibile utilizzare la vista del catalogo sys. Triggers.</span><span class="sxs-lookup"><span data-stu-id="82682-109">Alternatively, you can use the sys.triggers catalog view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82682-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82682-110">See Also</span></span>  
 <span data-ttu-id="82682-111">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="82682-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="82682-112">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="82682-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
