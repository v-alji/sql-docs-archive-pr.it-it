---
title: Rimuovere le istruzioni che modificano le autorizzazioni a livello di colonna per gli oggetti di sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- column-level permissions [SQL Server]
- removed statement permissions [SQL Server]
ms.assetid: 7f4fbbef-2696-4911-903b-63f6d9e4484a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e55af3dca0c55c2babd09bc6cfc48ed0ddf3ad7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635361"
---
# <a name="remove-statements-that-modify-column-level-permissions-on-system-objects"></a><span data-ttu-id="dbf0c-102">Rimuovere le istruzioni che modificano le autorizzazioni a livello di colonna per gli oggetti di sistema</span><span class="sxs-lookup"><span data-stu-id="dbf0c-102">Remove statements that modify column-level permissions on system objects</span></span>
  <span data-ttu-id="dbf0c-103">Sono state rilevate autorizzazioni non standard a livello di colonna per alcuni oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="dbf0c-103">The Upgrade Advisor detected nonstandard column-level permissions on system objects.</span></span> <span data-ttu-id="dbf0c-104">Tali modifiche alle autorizzazioni non verranno mantenute durante l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="dbf0c-104">These permission changes will not be maintained when you upgrade.</span></span> <span data-ttu-id="dbf0c-105">Le autorizzazioni a livello di colonna per gli oggetti di sistema non sono inoltre più supportate.</span><span class="sxs-lookup"><span data-stu-id="dbf0c-105">Additionally, column-level permissions on system objects are no longer supported.</span></span> <span data-ttu-id="dbf0c-106">Rimuovere dalle applicazioni tutte le istruzioni che impostano autorizzazioni a livello di colonna per oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="dbf0c-106">Remove statements from your applications that set column-level permissions on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="dbf0c-107">Componente</span><span class="sxs-lookup"><span data-stu-id="dbf0c-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="dbf0c-108">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="dbf0c-108">Corrective Action</span></span>  
 <span data-ttu-id="dbf0c-109">Rimuovere dalle applicazioni le istruzioni che concedono, negano o revocano autorizzazioni a livello di colonna per oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="dbf0c-109">Remove statements from your application that grant, deny, or revoke column-level permissions on system objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf0c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbf0c-110">See Also</span></span>  
 <span data-ttu-id="dbf0c-111">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="dbf0c-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="dbf0c-112">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="dbf0c-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
