---
title: Gerarchia delle autorizzazioni (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.server.permissions.f1--May use common.permissions
helpviewer_keywords:
- security [SQL Server], denying access
- hierarchies [SQL Server], permissions
- securables [SQL Server]
- security [SQL Server], permissions
- permissions [SQL Server], hierarchy
- security [SQL Server], granting access
ms.assetid: f6d20a55-ef03-4e14-85f9-009902889866
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9a04e5595e509de63b362b31b240e113e635581d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714055"
---
# <a name="permissions-hierarchy-database-engine"></a><span data-ttu-id="d82d3-102">Gerarchia delle autorizzazioni (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="d82d3-102">Permissions Hierarchy (Database Engine)</span></span>
  <span data-ttu-id="d82d3-103">[!INCLUDE[ssDE](../../../includes/ssde-md.md)] gestisce una raccolta gerarchica di entità che possono essere protette attraverso l'uso di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d82d3-103">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] manages a hierarchical collection of entities that can be secured with permissions.</span></span> <span data-ttu-id="d82d3-104">Queste entità sono denominate *entità a sicurezza diretta*.</span><span class="sxs-lookup"><span data-stu-id="d82d3-104">These entities are known as *securables*.</span></span> <span data-ttu-id="d82d3-105">Le entità a protezione diretta più significative sono server e database, ma è possibile impostare autorizzazione distinte a un livello più specifico.</span><span class="sxs-lookup"><span data-stu-id="d82d3-105">The most prominent securables are servers and databases, but discrete permissions can be set at a much finer level.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d82d3-106">regola le azioni delle entità sulle entità a protezione diretta verificando che siano state concesse le autorizzazioni corrette.</span><span class="sxs-lookup"><span data-stu-id="d82d3-106">regulates the actions of principals on securables by verifying that they have been granted appropriate permissions.</span></span>

 <span data-ttu-id="d82d3-107">Nella figura seguente vengono illustrate le relazioni esistenti tra le gerarchie di autorizzazioni di [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d82d3-107">The following illustration shows the relationships among the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions hierarchies.</span></span>

 <span data-ttu-id="d82d3-108">![Diagramma delle gerarchie di autorizzazioni del motore di database](../../database-engine/media/wj-security-layers.gif "Diagramma delle gerarchie di autorizzazioni del motore di database")</span><span class="sxs-lookup"><span data-stu-id="d82d3-108">![Diagram of Database Engine permissions hierarchies](../../database-engine/media/wj-security-layers.gif "Diagram of Database Engine permissions hierarchies")</span></span>

## <a name="chart-of-sql-server-permissions"></a><span data-ttu-id="d82d3-109">Grafico delle autorizzazioni di SQL Server</span><span class="sxs-lookup"><span data-stu-id="d82d3-109">Chart of SQL Server Permissions</span></span>
 <span data-ttu-id="d82d3-110">Per un'anteprima di grandi dimensioni di tutte le autorizzazioni del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] in formato pdf, vedere [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span><span class="sxs-lookup"><span data-stu-id="d82d3-110">For a poster sized chart of all [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions in pdf format, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>

## <a name="working-with-permissions"></a><span data-ttu-id="d82d3-111">Utilizzo delle autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d82d3-111">Working with Permissions</span></span>
 <span data-ttu-id="d82d3-112">Le autorizzazioni possono essere manipolate attraverso le ben note query GRANT, DENY e REVOKE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d82d3-112">Permissions can be manipulated with the familiar [!INCLUDE[tsql](../../includes/tsql-md.md)] queries GRANT, DENY, and REVOKE.</span></span> <span data-ttu-id="d82d3-113">Le informazioni sulle autorizzazioni sono visualizzate nelle viste di catalogo [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) e [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d82d3-113">Information about permissions is visible in the [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) and [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) catalog views.</span></span> <span data-ttu-id="d82d3-114">Le funzioni predefinite offrono inoltre supporto per query sulle informazioni relative alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d82d3-114">There is also support for querying permissions information by using built-in functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="d82d3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d82d3-115">See Also</span></span>
 <span data-ttu-id="d82d3-116">[Protezione](securing-sql-server.md) [delle autorizzazioni SQL Server &#40;motore di database](permissions-database-engine.md) entità a [protezione diretta](securables.md)&#41;[entità &#40;](authentication-access/principals-database-engine.md) motore di database&#41;&#40;Transact-SQL&#41;&#40;Transact [-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) Transact [-SQL &#40;](/sql/t-sql/statements/revoke-transact-sql) [Deny](/sql/t-sql/statements/deny-transact-sql)&#41;Transact- [SQL HAS_PERMS_BY_NAME &#40;](/sql/t-sql/functions/has-perms-by-name-transact-sql)&#41;Transact-SQL [fn_builtin_permissions sys.](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) [&#40;&#41;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) Transact-SQL server_permissions sys. &#40;[&#41;Transact-](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) SQL database_permissions</span><span class="sxs-lookup"><span data-stu-id="d82d3-116">[Securing SQL Server](securing-sql-server.md) [Permissions &#40;Database Engine&#41;](permissions-database-engine.md) [Securables](securables.md) [Principals &#40;Database Engine&#41;](authentication-access/principals-database-engine.md) [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) [HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/has-perms-by-name-transact-sql) [sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) [sys.server_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) [sys.database_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql)</span></span>


