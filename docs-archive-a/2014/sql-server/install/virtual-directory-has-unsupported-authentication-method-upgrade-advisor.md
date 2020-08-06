---
title: Il metodo di autenticazione della directory virtuale non è supportato (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 216eca6f-9a66-42e1-aa54-dcf99cec9f7d
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 67b1c027b8ed020f65fdea7c093f6d5454f02c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628112"
---
# <a name="virtual-directory-has-unsupported-authentication-method-upgrade-advisor"></a><span data-ttu-id="46eb3-102">Metodo di autenticazione non supportato nella directory virtuale (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="46eb3-102">Virtual directory has unsupported authentication method (Upgrade Advisor)</span></span>
  <span data-ttu-id="46eb3-103">È stato rilevato un metodo di autenticazione non supportato nella directory virtuale del server di report o di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="46eb3-103">Upgrade Advisor detected an unsupported authentication method on the Report Manager or report server virtual directory.</span></span> <span data-ttu-id="46eb3-104">I metodi di autenticazione non supportati dall'aggiornamento sono anonimo, digest e .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="46eb3-104">Authentication methods that are not supported by upgrade include Anonymous, Digest, and .NET Passport.</span></span>  
  
||  
|-|  
|<span data-ttu-id="46eb3-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="46eb3-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="46eb3-106">Componente</span><span class="sxs-lookup"><span data-stu-id="46eb3-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="46eb3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46eb3-107">Description</span></span>  
 <span data-ttu-id="46eb3-108">Non è possibile aggiornare un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] che utilizza uno dei metodi di autenticazione seguenti.</span><span class="sxs-lookup"><span data-stu-id="46eb3-108">Setup cannot upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that uses one of the following authentication methods</span></span>  
  
-   <span data-ttu-id="46eb3-109">Anonimo</span><span class="sxs-lookup"><span data-stu-id="46eb3-109">Anonymous</span></span>  
  
-   <span data-ttu-id="46eb3-110">Digest</span><span class="sxs-lookup"><span data-stu-id="46eb3-110">Digest</span></span>  
  
-   <span data-ttu-id="46eb3-111">.NET Passport</span><span class="sxs-lookup"><span data-stu-id="46eb3-111">.NET Passport</span></span>  
  
 <span data-ttu-id="46eb3-112">Per continuare, è possibile modificare il metodo di autenticazione specificato per le directory virtuali di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in Internet Information Services (IIS) o eseguire la migrazione dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="46eb3-112">To continue, you can either modify the Authentication method that is specified for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories in Internet Information Services (IIS), or you can migrate your installation.</span></span> <span data-ttu-id="46eb3-113">Per ulteriori informazioni sulla migrazione dell'installazione, vedere la documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46eb3-113">For more information about migrating your installation, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="46eb3-114">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="46eb3-114">Corrective Action</span></span>  
 <span data-ttu-id="46eb3-115">Per continuare con aggiornamento, modificare il metodo di autenticazione in IIS per le directory virtuali ReportServer e Report.</span><span class="sxs-lookup"><span data-stu-id="46eb3-115">To continue with upgrade, modify the Authentication method in IIS for the ReportServer and Reports virtual directories.</span></span> <span data-ttu-id="46eb3-116">Per ulteriori informazioni sulla modifica dei metodi di autenticazione in IIS, vedere la documentazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="46eb3-116">For more information about modifying Authentication methods in IIS, see the IIS documentation.</span></span> <span data-ttu-id="46eb3-117">Dopo avere modificato il metodo di autenticazione per le directory virtuali di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], eseguire nuovamente Preparazione aggiornamento per confermare che sono presenti altri problemi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="46eb3-117">After you modify the Authentication method for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories, re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46eb3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46eb3-118">See Also</span></span>  
 [<span data-ttu-id="46eb3-119">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="46eb3-119">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
