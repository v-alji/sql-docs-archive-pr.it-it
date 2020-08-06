---
title: Compatibilità con le versioni precedenti in SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 2f986436-aaf2-4eaf-9809-df849d97d4fb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73b6f4eebccf23850ccf08ec95ccb59dbc5c6293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628622"
---
# <a name="backward-compatibility-in-smo"></a><span data-ttu-id="4c3c6-102">Compatibilità con le versioni precedenti in SMO</span><span class="sxs-lookup"><span data-stu-id="4c3c6-102">Backward Compatibility in SMO</span></span>
  <span data-ttu-id="4c3c6-103">Le applicazioni SMO create utilizzando le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono essere comunque ricompilate in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]tramite SMO.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-103">SMO applications that were written using previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be recompiled by using SMO in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="migrating-smo-applications"></a><span data-ttu-id="4c3c6-104">Migrazione di applicazioni SMO</span><span class="sxs-lookup"><span data-stu-id="4c3c6-104">Migrating SMO Applications</span></span>  
 <span data-ttu-id="4c3c6-105">È necessario che i riferimenti alle DLL SMO nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengano rimossi e che vengano inclusi invece i riferimenti alle nuove DLL SMO disponibili in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c3c6-105">References to SMO dlls in older versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed, and references to the new SMO dlls that are provided with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be included.</span></span>  
  
 <span data-ttu-id="4c3c6-106">Vengono utilizzati in genere i riferimenti agli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c3c6-106">Minimally, you would reference the following:</span></span>  
  
-   <span data-ttu-id="4c3c6-107">Microsoft.SqlServer.ConnectionInfo</span><span class="sxs-lookup"><span data-stu-id="4c3c6-107">Microsoft.SqlServer.ConnectionInfo</span></span>  
  
-   <span data-ttu-id="4c3c6-108">Microsoft.SqlServer.Smo</span><span class="sxs-lookup"><span data-stu-id="4c3c6-108">Microsoft.SqlServer.Smo</span></span>  
  
-   <span data-ttu-id="4c3c6-109">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="4c3c6-109">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
 <span data-ttu-id="4c3c6-110">Tali file sono necessari per le classi di connessione, le classi di utilità SMO e le classi della libreria Microsoft Foundation Class.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-110">These files are required for connection classes, SMO utility classes, and foundation classes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c3c6-111">Poiché SmoEnum.dll è stato rimosso, è necessario che i riferimenti a tale file vengono rimossi dal progetto [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] SMO.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-111">SmoEnum.dll has been removed so references to it must be removed from the SMO [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] project.</span></span>  
  
 <span data-ttu-id="4c3c6-112">Lo spazio dei nomi è stato modificato ed è pertanto necessario utilizzare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c3c6-112">The namespaces have also changed, so you can use the following:</span></span>  
  
##### <a name="for-visual-c"></a><span data-ttu-id="4c3c6-113">Per Visual C#</span><span class="sxs-lookup"><span data-stu-id="4c3c6-113">For Visual C#</span></span>  
  
```  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
```  
  
##### <a name="for-visual-basic"></a><span data-ttu-id="4c3c6-114">Per Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c3c6-114">For Visual Basic</span></span>  
  
```  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
```  
  
 <span data-ttu-id="4c3c6-115">Se nel codice viene utilizzata la funzionalità URN, ad esempio `Server.GetSqlSmoObject(Urn)`, è necessario collegarsi allo spazio dei nomi Microsoft.SqlServer.Management.Sdk.Sfc.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-115">If your code uses Urn functionality, such as `Server.GetSqlSmoObject(Urn)`, you must link to the Microsoft.SqlServer.Management.Sdk.Sfc namespace.</span></span>  
  
 <span data-ttu-id="4c3c6-116">Se nel codice viene utilizzato direttamente l'oggetto Transfer, è necessario collegarsi allo spazio dei nomi Microsoft.SqlServer.Management.SmoExtended.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-116">If your code uses the Transfer object directly, you will have to link to the Microsoft.SqlServer.Management.SmoExtended namespace.</span></span>  
  
 <span data-ttu-id="4c3c6-117">Potrebbe necessario modificare il codice quando si esegue la relativa migrazione,</span><span class="sxs-lookup"><span data-stu-id="4c3c6-117">When you migrate code, you might have to modify the code.</span></span> <span data-ttu-id="4c3c6-118">poiché numerose caratteristiche di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] sono deprecate in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c3c6-118">This is because several [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] features have been deprecated in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4c3c6-119">Per ulteriori informazioni sulle funzionalità deprecate, vedere [deprecated motore di database features in SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) nella [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentazione online di.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-119">For more information about deprecated features, see [Deprecated Database Engine Features in SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
