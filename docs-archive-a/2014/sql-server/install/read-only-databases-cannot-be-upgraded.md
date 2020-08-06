---
title: I database di sola lettura non possono essere aggiornati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- database cannot be upgraded
ms.assetid: 27964211-ea30-4390-b791-dcf225fb9ae7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ba48ed2bd80961a4949dc13f04fed0637ecc27ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635913"
---
# <a name="read-only-databases-cannot-be-upgraded"></a><span data-ttu-id="defb4-102">Non è possibile aggiornare database di sola lettura</span><span class="sxs-lookup"><span data-stu-id="defb4-102">Read-only databases cannot be upgraded</span></span>
  <span data-ttu-id="defb4-103">Alcuni database di questa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non possono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="defb4-103">Upgrade Advisor has determined that some databases on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be upgraded.</span></span>  
  
## <a name="component"></a><span data-ttu-id="defb4-104">Componente</span><span class="sxs-lookup"><span data-stu-id="defb4-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="defb4-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="defb4-105">Description</span></span>  
 <span data-ttu-id="defb4-106">È stato rilevato un database di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="defb4-106">A read-only database has been detected.</span></span> <span data-ttu-id="defb4-107">Per aggiornare il database, è necessario che sia accessibile in scrittura dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="defb4-107">To upgrade the database, Setup must be able to write to the database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="defb4-108">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="defb4-108">Corrective Action</span></span>  
 <span data-ttu-id="defb4-109">Quando nessuno utilizza il database, utilizzare l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istruzione di Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] o alter database per modificare il database in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="defb4-109">When no one is using the database, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or the ALTER DATABASE statement to change the database to read-write.</span></span> <span data-ttu-id="defb4-110">Per impostare il database in lettura/scrittura, utilizzare l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="defb4-110">The following statement changes the database to read-write.</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE <database name>  
SET READ_WRITE;  
GO  
```  
  
 <span data-ttu-id="defb4-111">Per ulteriori informazioni sull'istruzione ALTER DATABASE, vedere l'argomento "ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])" argomento nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="defb4-111">For more information about the ALTER DATABASE statement, see the "ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])" topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="defb4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="defb4-112">See Also</span></span>  
 <span data-ttu-id="defb4-113">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="defb4-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="defb4-114">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="defb4-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
