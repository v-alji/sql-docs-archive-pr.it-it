---
title: Verificare che tutti i filegroup siano scrivibili durante il processo di aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filegroups [SQL Server], writeable
- writeable filegroups [SQL Server]
ms.assetid: 2985efc1-4b14-46c3-abbd-a656b159f23c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8146efb876bf97c36c549a2b58d104592df611e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726428"
---
# <a name="verify-all-filegroups-are-writeable-during-the-upgrade-process"></a><span data-ttu-id="7a1dd-102">Verificare che durante il processo di aggiornamento tutti i filegroup siano scrivibili</span><span class="sxs-lookup"><span data-stu-id="7a1dd-102">Verify all filegroups are writeable during the upgrade process</span></span>
  <span data-ttu-id="7a1dd-103">È stato rilevato un database con uno o più filegroup di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="7a1dd-103">Upgrade Advisor detected a database that has one or more read-only filegroups.</span></span> <span data-ttu-id="7a1dd-104">Prima dell'aggiornamento, è necessario che i filegroup di tutti i database nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] siano impostati su READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="7a1dd-104">All databases in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must have filegroups set to READ_WRITE before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="7a1dd-105">Componente</span><span class="sxs-lookup"><span data-stu-id="7a1dd-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="7a1dd-106">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="7a1dd-106">Corrective Action</span></span>  
 <span data-ttu-id="7a1dd-107">Utilizzare ALTER DATABASE per impostare il filegroup su READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="7a1dd-107">Use ALTER DATABASE to set the filegroup to READ_WRITE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a1dd-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a1dd-108">See Also</span></span>  
 <span data-ttu-id="7a1dd-109">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="7a1dd-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="7a1dd-110">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="7a1dd-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
