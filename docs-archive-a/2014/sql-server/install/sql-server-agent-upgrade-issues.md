---
title: Problemi di aggiornamento SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server Agent
- SQL Server Agent, upgrades
ms.assetid: 77e303ff-febd-4103-ae5d-6e5b85bc8009
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ac234a757510af5ebfac261ea6d3e7e57d2f426f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715968"
---
# <a name="sql-server-agent-upgrade-issues"></a><span data-ttu-id="e4c4c-102">Problemi di aggiornamento di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e4c4c-102">SQL Server Agent Upgrade Issues</span></span>
  <span data-ttu-id="e4c4c-103">Negli argomenti seguenti vengono descritti i problemi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che possono influire su un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e4c4c-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent issues that might affect an upgrade.</span></span> <span data-ttu-id="e4c4c-104">Vengono illustrate le azioni che è possibile eseguire per tentare di ridurre gli effetti di queste modifiche nell'ambiente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4c4c-104">The topics describe actions that you can take to help reduce the effect of these changes on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4c4c-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e4c4c-105">In This Section</span></span>  
  
-   [<span data-ttu-id="e4c4c-106">Piani di manutenzione del database sostituiti</span><span class="sxs-lookup"><span data-stu-id="e4c4c-106">Database maintenance plans superseded</span></span>](../../../2014/sql-server/install/database-maintenance-plans-superseded.md)  
  
-   [<span data-ttu-id="e4c4c-107">Solo gli utenti sysadmin possono scrivere file di log dei passaggi del processo nel file system</span><span class="sxs-lookup"><span data-stu-id="e4c4c-107">Only sysadmin users can write job step log files to the file system</span></span>](../../../2014/sql-server/install/only-sysadmin-users-can-write-job-step-log-files-to-the-file-system.md)  
  
-   [<span data-ttu-id="e4c4c-108">Al posto della stored procedure estesa xp_sqlagent_proxy_account usare le nuove stored procedure</span><span class="sxs-lookup"><span data-stu-id="e4c4c-108">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>](../../../2014/sql-server/install/replace-xp-sqlagent-proxy-account-extended-sp-with-new-stored-procedures.md)  
  
-   [<span data-ttu-id="e4c4c-109">La categoria di processi per il log shipping di SQL Server Agent impedisce il completamento dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e4c4c-109">SQL Server Agent log shipping job category causes upgrade to fail</span></span>](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md)  
  
-   [<span data-ttu-id="e4c4c-110">Il servizio SQL Server Agent non può usare l'autenticazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4c4c-110">SQL Server Agent Service cannot use SQL Server Authentication</span></span>](../../../2014/sql-server/install/sql-server-agent-service-cannot-use-sql-server-authentication.md)  
  
-   [<span data-ttu-id="e4c4c-111">Aggiornare la sintassi del token nei passaggi del processo di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e4c4c-111">Update token syntax in SQL Server Agent job steps</span></span>](../../../2014/sql-server/install/update-token-syntax-in-sql-server-agent-job-steps.md)  
  
-   [<span data-ttu-id="e4c4c-112">Aggiornare tutti i server di destinazione prima di aggiornare il server master</span><span class="sxs-lookup"><span data-stu-id="e4c4c-112">Upgrade all target servers before upgrading the master server</span></span>](../../../2014/sql-server/install/upgrade-all-target-servers-before-upgrading-the-master-server.md)  
  
-   [<span data-ttu-id="e4c4c-113">In seguito all'aggiornamento l'account proxy utente per SQL Server Agent verrà sostituito dall'account temporaneo UpgradedProxyAccount</span><span class="sxs-lookup"><span data-stu-id="e4c4c-113">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md)  
  
## <a name="see-also"></a><span data-ttu-id="e4c4c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4c4c-114">See Also</span></span>  
 <span data-ttu-id="e4c4c-115">[SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="e4c4c-115">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="e4c4c-116">Risoluzione dei problemi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e4c4c-116">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
