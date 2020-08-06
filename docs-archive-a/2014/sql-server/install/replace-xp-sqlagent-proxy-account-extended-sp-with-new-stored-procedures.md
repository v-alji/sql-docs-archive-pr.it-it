---
title: Sostituire l'utilizzo del xp_sqlagent_proxy_account stored procedure esteso con le nuove stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- xp_sqlagent_proxy_account
ms.assetid: 0e3cc931-6237-41dd-bf0d-0c03f4d8fff2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d124ab73f4b4315550134f28ffad232b4a1c0ec2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635348"
---
# <a name="replace-usage-of-the-xp_sqlagent_proxy_account-extended-stored-procedure-with-new-stored-procedures"></a><span data-ttu-id="1e02a-102">Al posto della stored procedure estesa xp_sqlagent_proxy_account utilizzare le nuove stored procedure</span><span class="sxs-lookup"><span data-stu-id="1e02a-102">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>
  <span data-ttu-id="1e02a-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent vengono supportati più proxy.</span><span class="sxs-lookup"><span data-stu-id="1e02a-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent supports multiple proxies.</span></span> <span data-ttu-id="1e02a-104">Per definire questi proxy, è necessario utilizzare un nuovo set di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="1e02a-104">You define these proxies by using a new set of stored procedures.</span></span> <span data-ttu-id="1e02a-105">Per ulteriori informazioni sulle nuove stored procedure di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, vedere gli argomenti seguenti nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1e02a-105">For more information about the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   <span data-ttu-id="1e02a-106">"sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-106">"sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-107">"sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-107">"sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-108">"sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-108">"sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-109">"sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-109">"sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-110">"sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-110">"sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-111">"sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-111">"sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-112">"sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-112">"sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-113">"sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-113">"sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-114">"sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-114">"sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-115">"sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-115">"sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="1e02a-116">"sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span><span class="sxs-lookup"><span data-stu-id="1e02a-116">"sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e02a-117">Dopo l'aggiornamento a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , le istruzioni che utilizzano il **xp_sqlagent_proxy_account** stored procedure esteso non funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="1e02a-117">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], any statements that use the **xp_sqlagent_proxy_account** extended stored procedure will not work.</span></span> <span data-ttu-id="1e02a-118">Utilizzare **sp_xp_cmdshell_proxy_account** anziché **xp_sqlagent_proxy_account** per impostare il proxy per **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="1e02a-118">Use **sp_xp_cmdshell_proxy_account** instead of **xp_sqlagent_proxy_account** to set the proxy for **xp_cmdshell**.</span></span>  
  
## <a name="component"></a><span data-ttu-id="1e02a-119">Componente</span><span class="sxs-lookup"><span data-stu-id="1e02a-119">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1e02a-120">Agent</span><span class="sxs-lookup"><span data-stu-id="1e02a-120">Agent</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e02a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e02a-121">See Also</span></span>  
 [<span data-ttu-id="1e02a-122">Problemi di aggiornamento di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="1e02a-122">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
