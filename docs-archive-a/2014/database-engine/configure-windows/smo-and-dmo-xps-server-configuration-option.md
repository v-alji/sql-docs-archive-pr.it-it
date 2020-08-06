---
title: Opzioni di configurazione del server SMO e DMO XPs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: bcd945ba-5d81-4124-9a2b-d87491c2a369
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f18fc6fafcf033113c983f990700158a10aec92a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724168"
---
# <a name="smo-and-dmo-xps-server-configuration-option"></a><span data-ttu-id="f2707-102">Opzioni di configurazione del server SMO e DMO XPs</span><span class="sxs-lookup"><span data-stu-id="f2707-102">SMO and DMO XPs Server Configuration Option</span></span>
  <span data-ttu-id="f2707-103">L'opzione SMO and DMO XPs consente di abilitare le stored procedure estese SMO ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object) nel server.</span><span class="sxs-lookup"><span data-stu-id="f2707-103">Use the SMO and DMO XPs option to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object (SMO) extended stored procedures on this server.</span></span>  
  
 <span data-ttu-id="f2707-104">Si noti che, a partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], DMO è stato rimosso da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2707-104">Note than beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], DMO has been removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f2707-105">I valori possibili sono illustrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="f2707-105">The possible values are described in the following table:</span></span>  
  
|<span data-ttu-id="f2707-106">valore</span><span class="sxs-lookup"><span data-stu-id="f2707-106">Value</span></span>|<span data-ttu-id="f2707-107">Significato</span><span class="sxs-lookup"><span data-stu-id="f2707-107">Meaning</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="f2707-108">0</span><span class="sxs-lookup"><span data-stu-id="f2707-108">0</span></span>|<span data-ttu-id="f2707-109">Le stored procedure estese SMO non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="f2707-109">SMO XPs are not available.</span></span>|  
|<span data-ttu-id="f2707-110">1</span><span class="sxs-lookup"><span data-stu-id="f2707-110">1</span></span>|<span data-ttu-id="f2707-111">Le stored procedure estese SMO sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="f2707-111">SMO XPs are available.</span></span> <span data-ttu-id="f2707-112">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="f2707-112">This is the default.</span></span>|  
  
 <span data-ttu-id="f2707-113">L'impostazione ha effetto immediato.</span><span class="sxs-lookup"><span data-stu-id="f2707-113">The setting takes effect immediately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f2707-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="f2707-114">Examples</span></span>  
 <span data-ttu-id="f2707-115">Nell'esempio seguente vengono abilitate le stored procedure estese SMO.</span><span class="sxs-lookup"><span data-stu-id="f2707-115">The following example enables SMO extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'SMO and DMO XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2707-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2707-116">See Also</span></span>  
 [<span data-ttu-id="f2707-117">Guida alla programmazione di SQL Server Management Objects &#40;SMO&#41;</span><span class="sxs-lookup"><span data-stu-id="f2707-117">SQL Server Management Objects &#40;SMO&#41; Programming Guide</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
  
