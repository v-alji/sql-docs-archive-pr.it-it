---
title: Non è possibile aggiornare gli account di accesso SQL Server 6,5 inattivi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- passwords [SQL Server], dormant logins
- dormant logins
- logins [SQL Server], upgrading dormant logins
- identifying dormant logins
- password hashes [SQL Server]
ms.assetid: ebe18a74-0375-4df4-b894-239f8fdabb64
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f78bca9bf2b99b2ab6f530613b64bc0e46c4001c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628185"
---
# <a name="dormant-sql-server-65-logins-cannot-be-upgraded"></a><span data-ttu-id="00031-102">Impossibile aggiornare gli account di accesso di SQL Server 6.5 inattivi</span><span class="sxs-lookup"><span data-stu-id="00031-102">Dormant SQL Server 6.5 logins cannot be upgraded</span></span>
  <span data-ttu-id="00031-103">Preparazione aggiornamento ha rilevato un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la cui password non può essere direttamente aggiornata a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00031-103">Upgrade Advisor detected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login whose password cannot be directly upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="00031-104">Per attivare questo account di accesso, è necessario reimpostarne la password.</span><span class="sxs-lookup"><span data-stu-id="00031-104">To enable this login, you must reset its password.</span></span> <span data-ttu-id="00031-105">Utilizzare ALTER LOGIN per reimpostare la password.</span><span class="sxs-lookup"><span data-stu-id="00031-105">You can reset the password by using ALTER LOGIN.</span></span>  
  
```  
ALTER LOGIN <login name> WITH PASSWORD = '<new password>' MUST_CHANGE  
```  
  
 <span data-ttu-id="00031-106">La nuova password verrà convalidata in base ai criteri di complessità delle password del sistema, a meno che il controllo dei criteri non sia disabilitato.</span><span class="sxs-lookup"><span data-stu-id="00031-106">The new password will be validated against your system's password complexity policy, unless policy checking is disabled.</span></span> <span data-ttu-id="00031-107">È consigliabile utilizzare password complesse e non disabilitare il controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="00031-107">We recommend that you use complex passwords and not disable policy checking.</span></span> <span data-ttu-id="00031-108">L'opzione MUST_CHANGE impone all'utente la selezione di una nuova password.</span><span class="sxs-lookup"><span data-stu-id="00031-108">The MUST_CHANGE option forces the user to select a new password.</span></span> <span data-ttu-id="00031-109">Tale procedura non è necessaria ma è consigliabile.</span><span class="sxs-lookup"><span data-stu-id="00031-109">This is not required, but it is recommended.</span></span>  
  
 <span data-ttu-id="00031-110">Per identificare gli account di accesso inattivi utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="00031-110">You can identify dormant logins by using the following query:</span></span>  
  
```  
SELECT * FROM sysxlogins WHERE (xstatus & 2048) = 2048;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="00031-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00031-111">See Also</span></span>  
 <span data-ttu-id="00031-112">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="00031-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="00031-113">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="00031-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
