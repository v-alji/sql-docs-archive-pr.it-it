---
title: Compatibilità con le versioni precedenti di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- SSRS, backward compatibility
- SQL Server Reporting Services, backward compatibility
- backward compatibility [Reporting Services]
ms.assetid: 675b0e0e-cfee-4790-9675-80fc3ea6d30f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7203740ba7f52dfc2cd3793a20fed9fecf5f9468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719506"
---
# <a name="reporting-services-backward-compatibility"></a><span data-ttu-id="a378b-102">Compatibilità con le versioni precedenti di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a378b-102">Reporting Services Backward Compatibility</span></span>
  <span data-ttu-id="a378b-103">In questa sezione vengono descritte le modifiche del comportamento tra le versioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a378b-103">This section describes changes in behavior between versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="a378b-104">Vengono illustrate caratteristiche che non sono più disponibili o che verranno rimosse a partire da una delle prossime versioni.</span><span class="sxs-lookup"><span data-stu-id="a378b-104">It covers features that are no longer available or are scheduled to be removed in a future release.</span></span> <span data-ttu-id="a378b-105">Vengono anche descritte modifiche essenziali apportate al prodotto che causeranno l'interruzione del funzionamento di applicazioni personalizzate in cui è inclusa la funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a378b-105">It also describes fundamental changes to the product that are known to break a custom application that includes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a378b-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a378b-106">In This Section</span></span>  
  
|<span data-ttu-id="a378b-107">Argomento</span><span class="sxs-lookup"><span data-stu-id="a378b-107">Topic</span></span>|<span data-ttu-id="a378b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a378b-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a378b-109">Funzionalità non più disponibili di SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a378b-109">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)|<span data-ttu-id="a378b-110">Vengono descritte le funzionalità disponibili nelle versioni precedenti di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , ma che sono state rimosse nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a378b-110">Describes features that existed in earlier versions of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] but that have been removed in later versions.</span></span>|  
|[<span data-ttu-id="a378b-111">Funzionalità deprecate di SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a378b-111">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>](deprecated-features-in-sql-server-reporting-services-ssrs.md)|<span data-ttu-id="a378b-112">Vengono descritte le funzionalità disponibili in questa versione di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] per la compatibilità con le versioni precedenti, ma che verranno rimosse in una versione futura di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a378b-112">Describes features that exist this release of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] for backward compatibility, but which will be removed in a future version of SQL Server.</span></span>|  
|[<span data-ttu-id="a378b-113">Modifiche di rilievo di SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a378b-113">Breaking Changes in SQL Server Reporting Services in SQL Server 2014</span></span>](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="a378b-114">Vengono descritti i problemi che possono verificarsi durante l'aggiornamento di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a378b-114">Describes issues that you might encounter when you upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="a378b-115">Modifiche del comportamento di SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a378b-115">Behavior Changes to SQL Server Reporting Services  in SQL Server 2014</span></span>](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="a378b-116">Vengono descritte le funzionalità che sono state modificate in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a378b-116">Describes features that have changed in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a378b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a378b-117">See Also</span></span>  
 <span data-ttu-id="a378b-118">[Compatibilità con le versioni precedenti](../../2014/getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="a378b-118">[Backward Compatibility](../../2014/getting-started/backward-compatibility.md) </span></span>  
 [<span data-ttu-id="a378b-119">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="a378b-119">Analysis Services Backward Compatibility</span></span>](../../2014/analysis-services/analysis-services-backward-compatibility.md)  
  
  
