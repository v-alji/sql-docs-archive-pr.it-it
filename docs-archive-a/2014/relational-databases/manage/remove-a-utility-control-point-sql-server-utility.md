---
title: Rimuovere un punto di controllo dell'utilità (Utilità SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c048a416-900e-4c77-8243-e0f0d8b94068
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fe4ebb9de3f7644b4cff5c7dbfb34e50be7e8993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637842"
---
# <a name="remove-a-utility-control-point-sql-server-utility"></a><span data-ttu-id="ad71b-102">Rimuovere un punto di controllo dell'utilità (Utilità SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ad71b-102">Remove a Utility Control Point (SQL Server Utility)</span></span>
  <span data-ttu-id="ad71b-103">In questo argomento viene illustrato come rimuovere un punto di controllo dell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dall'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad71b-103">This topic describes how to remove a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utility control point (UCP) from the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ad71b-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ad71b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad71b-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ad71b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ad71b-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="ad71b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ad71b-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ad71b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ad71b-108">**Per rimuovere un punto di controllo dell'utilità utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="ad71b-108">**To remove a Utility Control Point, using:**</span></span>  
  
     [<span data-ttu-id="ad71b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad71b-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ad71b-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ad71b-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ad71b-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="ad71b-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ad71b-112">Prima di utilizzare questa procedura per rimuovere il punto di controllo dell'utilità da Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , tenere presente i requisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="ad71b-112">Before you use this procedure to remove the UCP from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, note the following requirements.</span></span> <span data-ttu-id="ad71b-113">La stored procedure eseguirà i controlli necessari come parte dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="ad71b-113">The stored procedure will run prerequisite checks as part of the operation.</span></span>  
  
-   <span data-ttu-id="ad71b-114">Prima di eseguire questa procedura, è necessario che tutte le istanze gestite di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengano rimosse dal punto di controllo dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="ad71b-114">Before you run this procedure, all managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed from the UCP.</span></span> <span data-ttu-id="ad71b-115">Si noti che il punto di controllo dell'utilità è un'istanza gestita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad71b-115">Note that the UCP is a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ad71b-116">Per altre informazioni, vedere [Rimuovere un'istanza di SQL Server da Utilità SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ad71b-116">From more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
-   <span data-ttu-id="ad71b-117">È necessario eseguire la procedura in un computer configurato come punto di controllo dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="ad71b-117">This procedure must be run on a computer that is a UCP.</span></span>  
  
-   <span data-ttu-id="ad71b-118">Se l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da cui è stato rimosso il punto di controllo dell'utilità dispone di un set di raccolta dati non appartenente all'utilità, il database UMDW (sysutility_mdw) non verrà eliminato dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="ad71b-118">If the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the UCP was removed has a non-Utility data collection set, the UMDW database (sysutility_mdw) will not be dropped by the procedure.</span></span> <span data-ttu-id="ad71b-119">In tal caso, è necessario eliminare manualmente il database UMDW (sysutility_mdw) prima di creare nuovamente il punto di controllo dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="ad71b-119">If this is the case, the UMDW database (sysutility_mdw) must be dropped manually before the UCP can be created again.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ad71b-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ad71b-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ad71b-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ad71b-121">Permissions</span></span>  
 <span data-ttu-id="ad71b-122">La procedura deve essere eseguita da un utente che disponga di autorizzazioni `sysadmin`, le stesse necessarie per la creazione di un punto di controllo dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="ad71b-122">This procedure must be run by a user with `sysadmin` permissions; the same permissions required to create a UCP.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ad71b-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad71b-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-utility-control-point"></a><span data-ttu-id="ad71b-124">Per rimuovere un punto di controllo dell'utilità</span><span class="sxs-lookup"><span data-stu-id="ad71b-124">To remove a Utility Control Point</span></span>  
  
1.  <span data-ttu-id="ad71b-125">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad71b-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ad71b-126">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ad71b-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ad71b-127">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ad71b-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```  
EXEC msdb.dbo.sp_sysutility_ucp_remove;  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad71b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad71b-128">See Also</span></span>  
 <span data-ttu-id="ad71b-129">[Attività e funzionalità di Utilità SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="ad71b-129">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="ad71b-130">[Utilizzo di Esplora utilità per gestire Utilità SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ad71b-130">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="ad71b-131">Attività e funzionalità di Utilità SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad71b-131">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
