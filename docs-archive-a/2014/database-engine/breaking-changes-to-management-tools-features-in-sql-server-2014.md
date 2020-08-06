---
title: Modifiche di rilievo apportate alle funzionalità degli strumenti di gestione in SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 11/27/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 3ff3fad8-b569-4516-bd58-5a3efeb537e2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0487b6ab0958e0b83d4e8e34be507b5b3211ac87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630085"
---
# <a name="breaking-changes-to-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="5811f-102">Modifiche di rilievo nelle funzionalità degli strumenti di gestione in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5811f-102">Breaking Changes to Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="5811f-103">In questo argomento vengono descritte le modifiche di rilievo apportate alle funzionalità degli strumenti di gestione.</span><span class="sxs-lookup"><span data-stu-id="5811f-103">This topic describes breaking changes to management tools features.</span></span> <span data-ttu-id="5811f-104">Tali modifiche potrebbero interrompere il funzionamento di applicazioni, funzionalità o script basati su versioni precedenti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5811f-104">These changes might break applications, scripts, or functionalities that are based on earlier versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5811f-105">È possibile che questi problemi si verifichino quando viene effettuato un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5811f-105">You might encounter these issues when you upgrade.</span></span> <span data-ttu-id="5811f-106">Per altre informazioni, vedere [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="5811f-106">For more information, see [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span></span>  
  
## <a name="breaking-changes-in-sssql14"></a><span data-ttu-id="5811f-107">Modifiche di rilievo in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5811f-107">Breaking Changes in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
 <span data-ttu-id="5811f-108">Informazioni disponibili in futuro.</span><span class="sxs-lookup"><span data-stu-id="5811f-108">Information to come later.</span></span>  
  
## <a name="breaking-changes-in-sssql11"></a><span data-ttu-id="5811f-109">Modifiche di rilievo in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5811f-109">Breaking Changes in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
  
### <a name="you-cannot-use-sssql11-management-tools-to-create-a-utility-control-point-on-a-sskilimanjaro-instance-of-sql-server"></a><span data-ttu-id="5811f-110">Non è possibile utilizzare gli strumenti di gestione di [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] per creare un punto di controllo dell'utilità in un'istanza di [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] di SQL Server</span><span class="sxs-lookup"><span data-stu-id="5811f-110">You cannot use [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Management Tools to create a utility control point on a [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] instance of SQL Server</span></span>  
 <span data-ttu-id="5811f-111">Per creare un punto di controllo dell'utilità in un'istanza di [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], utilizzare gli strumenti di gestione di [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5811f-111">To create a utility control point on an instance of [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], use [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] Management Tools.</span></span>  
  
### <a name="smo-has-been-reversioned-in-sssql11"></a><span data-ttu-id="5811f-112">SMO è stato modificato in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5811f-112">SMO has been reversioned in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
 <span data-ttu-id="5811f-113">È possibile che il codice sviluppato con SMO da [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] o versioni precedenti non venga compilato in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] senza modifiche minori.</span><span class="sxs-lookup"><span data-stu-id="5811f-113">Code developed with SMO from [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] or earlier versions might not build against [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] without minor modifications.</span></span> <span data-ttu-id="5811f-114">Per altre informazioni, vedere [Compatibilità con le versioni precedenti in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span><span class="sxs-lookup"><span data-stu-id="5811f-114">For more information, see [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span></span>  

## <a name="breaking-changes-in-sql-server-2005"></a><a name="previous-versions"></a><span data-ttu-id="5811f-115">Modifiche di rilievo nella SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="5811f-115">Breaking Changes in SQL Server 2005</span></span>  

[!INCLUDE[Archived documentation for very old versions of SQL Server](../includes/paragraph-content/previous-versions-archive-documentation-sql-server.md)]

## <a name="see-also"></a><span data-ttu-id="5811f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5811f-116">See Also</span></span>  
 [<span data-ttu-id="5811f-117">Compatibilità con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="5811f-117">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
 [<span data-ttu-id="5811f-118">Ulteriori informazioni sulle modifiche di rilievo apportate alle funzionalità degli strumenti di gestione in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5811f-118">More about Breaking Changes to Management Tools Features in SQL Server 2014</span></span>](breaking-changes-to-database-engine-features-in-sql-server-2016.md?view=sql-server-2014)  
  
  
