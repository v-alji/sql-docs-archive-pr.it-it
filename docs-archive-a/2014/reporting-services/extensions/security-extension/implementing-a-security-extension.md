---
title: Implementazione di un'estensione di sicurezza | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- forms-based authentication [Reporting Services]
- custom authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: d2327e7c-0d48-49e3-bcd9-3bba4e67a68b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e5cf1fa6ce0e0a02a52e6a27f693c152d1f97152
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629217"
---
# <a name="implementing-a-security-extension"></a><span data-ttu-id="8b3c5-102">Implementazione di un'estensione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8b3c5-102">Implementing a Security Extension</span></span>
  <span data-ttu-id="8b3c5-103">L'autenticazione di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows rappresenta il sistema principale per la protezione dei report in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b3c5-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Authentication is the primary system for securing reports in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="8b3c5-104">In alcuni casi, tuttavia, potrebbe essere necessario estendere il sistema di sicurezza di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] per soddisfare i requisiti di sicurezza dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="8b3c5-104">In certain cases, however, you may need to extend the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security system to accommodate custom security in your enterprise.</span></span> <span data-ttu-id="8b3c5-105">A tale scopo, è possibile utilizzare la piattaforma di sviluppo fornita dall'API di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b3c5-105">You can do this using the development platform provided by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="8b3c5-106">In questa sezione viene fornita una panoramica sulle estensioni di sicurezza in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b3c5-106">This section will present an overview of security extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8b3c5-107">Per informazioni complete sull'implementazione, la distribuzione e la rimozione di un'estensione di sicurezza di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], vedere la pagina degli [esempi del prodotto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="8b3c5-107">For complete details about implementing, deploying, and removing a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension, please see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b3c5-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8b3c5-108">In This Section</span></span>  
 [<span data-ttu-id="8b3c5-109">Panoramica delle estensioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8b3c5-109">Security Extensions Overview</span></span>](security-extensions-overview.md)  
 <span data-ttu-id="8b3c5-110">Viene fornita una panoramica sulle estensioni di sicurezza di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8b3c5-110">Provides an overview of Reporting Services Security Extensions.</span></span>  
  
 [<span data-ttu-id="8b3c5-111">Autenticazione in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8b3c5-111">Authentication in Reporting Services</span></span>](authentication-in-reporting-services.md)  
 <span data-ttu-id="8b3c5-112">Viene descritta l'autenticazione in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b3c5-112">Discusses authentication in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="8b3c5-113">Autorizzazione in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8b3c5-113">Authorization in Reporting Services</span></span>](authorization-in-reporting-services.md)  
 <span data-ttu-id="8b3c5-114">Viene descritta l'autorizzazione in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b3c5-114">Covers authorization in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b3c5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b3c5-115">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="8b3c5-116">[Estensioni di Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="8b3c5-116">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="8b3c5-117">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8b3c5-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
