---
title: rsAccessedDenied - Errore di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsAccessDenied error
ms.assetid: 2f76b1bf-96a2-4755-b76b-84e933220efc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 194006c2ef6f22b9bc27e9e8cbe1eebd027ed6b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629164"
---
# <a name="rsaccesseddenied---reporting-services-error"></a><span data-ttu-id="bded4-102">rsAccessedDenied - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bded4-102">rsAccessedDenied - Reporting Services Error</span></span>
  <span data-ttu-id="bded4-103">L'errore di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]**rsAccessedDenied** si verifica quando un utente non dispone dell'autorizzazione per eseguire un'azione,</span><span class="sxs-lookup"><span data-stu-id="bded4-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] error **rsAccessedDenied** occurs when a user does not have permission to perform an action.</span></span> <span data-ttu-id="bded4-104">ad esempio non dispone di un'assegnazione di ruolo che consenta di aprire un report o non ha aperto il browser con le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="bded4-104">For, example, they do not have a role assignment that allows them to open a report or they did not open their browser with the required permissions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="bded4-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Modalità nativa &#124; modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="bded4-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; SharePoint mode</span></span>|  
  
-   <span data-ttu-id="bded4-106">Se l'errore si è verificato durante l'accesso diretto al server di report tramite URL, verrà eseguito il mapping tra l'eccezione e un errore HTTP 401.</span><span class="sxs-lookup"><span data-stu-id="bded4-106">If the error occurred while accessing the report server directly through a URL, the exception is mapped to an HTTP 401 error.</span></span>  
  
-   <span data-ttu-id="bded4-107">Se si è verificato durante l'utilizzo di Gestione report o un altro strumento, l'errore verrà visualizzato in un'apposita pagina.</span><span class="sxs-lookup"><span data-stu-id="bded4-107">If the error occurred while using Report Manager or another tool, the error appears in an error page.</span></span>  
  
-   <span data-ttu-id="bded4-108">Se si è verificato durante un'operazione, una sottoscrizione o un recapito pianificato, l'errore verrà indicato solo nel file di log del server di report.</span><span class="sxs-lookup"><span data-stu-id="bded4-108">If the error occurred during a scheduled operation, subscription, or delivery, the error will appear in the report server log file only.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bded4-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bded4-109">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bded4-110">**Nome prodotto**</span><span class="sxs-lookup"><span data-stu-id="bded4-110">**Product Name**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="bded4-111">**ID evento**</span><span class="sxs-lookup"><span data-stu-id="bded4-111">**Event ID**</span></span>|<span data-ttu-id="bded4-112">rsAccessedDenied</span><span class="sxs-lookup"><span data-stu-id="bded4-112">rsAccessedDenied</span></span>|  
|<span data-ttu-id="bded4-113">**Origine evento**</span><span class="sxs-lookup"><span data-stu-id="bded4-113">**Event Source**</span></span>|<span data-ttu-id="bded4-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="bded4-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="bded4-115">**Componente**</span><span class="sxs-lookup"><span data-stu-id="bded4-115">**Component**</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="bded4-116">**Testo del messaggio**</span><span class="sxs-lookup"><span data-stu-id="bded4-116">**Message Text**</span></span>|<span data-ttu-id="bded4-117">Le autorizzazioni concesse all'utente 'mydomain\myAccount' non sono sufficienti per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="bded4-117">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="bded4-118">(rsAccessDenied) (ReportingServicesLibrary)</span><span class="sxs-lookup"><span data-stu-id="bded4-118">(rsAccessDenied) (ReportingServicesLibrary)</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="bded4-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="bded4-119">User Action</span></span>  
 <span data-ttu-id="bded4-120">Le autorizzazioni che consentono di accedere al contenuto e alle operazioni del server di report vengono concesse tramite assegnazioni di ruolo.</span><span class="sxs-lookup"><span data-stu-id="bded4-120">Permission to access report server content and operations are granted through role assignments.</span></span> <span data-ttu-id="bded4-121">In una nuova installazione solo gli amministratori locali possono accedere a un server di report.</span><span class="sxs-lookup"><span data-stu-id="bded4-121">On a new installation, only local administrators have access to a report server.</span></span> <span data-ttu-id="bded4-122">Per concedere l'accesso ad altri utenti, l'amministratore locale deve creare un'assegnazione di ruolo che specifica un account di gruppo o un account utente di dominio, uno o più ruoli che definiscono le attività eseguibili dall'utente, nonché un ambito, ovvero in genere la cartella Home o il nodo radice della gerarchia di cartelle del server di report.</span><span class="sxs-lookup"><span data-stu-id="bded4-122">To grant access to other users, a local administrator must create a role assignment that specifies a domain user or group account, one or more roles that define the tasks the user can perform, and a scope (usually the Home folder or root node of the report server folder hierarchy).</span></span> <span data-ttu-id="bded4-123">Per creare le assegnazioni di ruolo, è possibile usare Gestione report.</span><span class="sxs-lookup"><span data-stu-id="bded4-123">You can use Report Manager to create the role assignments.</span></span> <span data-ttu-id="bded4-124">Per altre informazioni, cercare "assegnazioni di ruolo" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bded4-124">For more information, search for "Role Assignments" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="bded4-125">Questo errore viene causato anche dall'amministratore locale del server di report.</span><span class="sxs-lookup"><span data-stu-id="bded4-125">This error is also caused by local administration of the report server.</span></span> <span data-ttu-id="bded4-126">Per altre informazioni, vedere [Configurare un server di report in modalità nativa per gli amministratori locali &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bded4-126">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bded4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bded4-127">See Also</span></span>  
 <span data-ttu-id="bded4-128">[Assegnazioni di ruolo](../security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="bded4-128">[Role Assignments](../security/role-assignments.md) </span></span>  
 <span data-ttu-id="bded4-129">[Concessione di autorizzazioni in un server di report in modalità nativa](../security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="bded4-129">[Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="bded4-130">Ruoli e autorizzazioni &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bded4-130">Roles and Permissions &#40;Reporting Services&#41;</span></span>](../security/roles-and-permissions-reporting-services.md)  
  
  
