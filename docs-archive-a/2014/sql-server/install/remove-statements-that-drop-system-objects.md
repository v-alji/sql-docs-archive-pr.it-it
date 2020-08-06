---
title: Rimuovere le istruzioni che eliminano oggetti di sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- drop system objects [SQL Server]
ms.assetid: cdfc3c50-c801-4039-a4bf-b35f876f1c61
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d9e8fbfd4a436e87cee413d95468ccf5dd36b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623746"
---
# <a name="remove-statements-that-drop-system-objects"></a><span data-ttu-id="0f677-102">Rimuovere le istruzioni che eliminano oggetti di sistema</span><span class="sxs-lookup"><span data-stu-id="0f677-102">Remove statements that drop system objects</span></span>
  <span data-ttu-id="0f677-103">Sono state rilevate istruzioni che eliminano oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="0f677-103">Upgrade Advisor detected statements that drop system objects.</span></span> <span data-ttu-id="0f677-104">Gli oggetti di sistema, incluse le stored procedure estese, vengono distribuiti nel database **Resource** di sola lettura (mssqlsystemresource) e non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="0f677-104">System objects, including extended stored procedures, are deployed in the read-only **resource** database (mssqlsystemresource) and cannot be dropped.</span></span> <span data-ttu-id="0f677-105">Modificare le applicazioni in modo da revocare o negare l'autorizzazione EXECUTE sugli oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="0f677-105">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="0f677-106">Componente</span><span class="sxs-lookup"><span data-stu-id="0f677-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="0f677-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f677-107">Description</span></span>  
 <span data-ttu-id="0f677-108">Non è possibile utilizzare istruzioni quali DROP TABLE, DROP PROCEDURE e **sp_dropextendedproc** per rimuovere gli oggetti di sistema, poiché tali oggetti vengono distribuiti nel database **Resource** di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0f677-108">Statements such as DROP TABLE, DROP PROCEDURE, and **sp_dropextendedproc** cannot be used to remove system objects, because these objects are deployed in the read-only **resource** database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="0f677-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="0f677-109">Corrective Action</span></span>  
 <span data-ttu-id="0f677-110">Rimuovere dalle applicazioni tutte le istruzioni che tentano di eliminare oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="0f677-110">Remove all statements that try to drop system objects from your applications.</span></span> <span data-ttu-id="0f677-111">Modificare le applicazioni in modo da revocare o negare l'autorizzazione EXECUTE sugli oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="0f677-111">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span> <span data-ttu-id="0f677-112">In alternativa è possibile utilizzare uno degli strumenti Configurazione superficie di attacco per disabilitare alcuni di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="0f677-112">Alternatively, you can use the Surface Area Configuration (SAC) tool to disable some of these objects.</span></span> <span data-ttu-id="0f677-113">Ad esempio, il **xp_cmdshell** stored procedure esteso può essere disabilitato o abilitato mediante lo strumento SAC.</span><span class="sxs-lookup"><span data-stu-id="0f677-113">For example, the **xp_cmdshell** extended stored procedure can be disabled or enabled using the SAC tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f677-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f677-114">See Also</span></span>  
 <span data-ttu-id="0f677-115">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="0f677-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="0f677-116">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="0f677-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
