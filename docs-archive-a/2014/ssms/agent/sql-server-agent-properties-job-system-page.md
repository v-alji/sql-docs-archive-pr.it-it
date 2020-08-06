---
title: Proprietà SQL Server Agent (pagina Sistema processi) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.job.f1
ms.assetid: e171d13e-1302-4f0e-88be-67d656aec8d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 743a8d558e97e9ad83cfc66e9ef1adf2e1bc0c2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636515"
---
# <a name="sql-server-agent-properties-job-system-page"></a><span data-ttu-id="ec6bf-102">Proprietà SQL Server Agent (pagina Sistema processi)</span><span class="sxs-lookup"><span data-stu-id="ec6bf-102">SQL Server Agent Properties (Job System Page)</span></span>
  <span data-ttu-id="ec6bf-103">Utilizzare questa pagina per visualizzare e modificare il modo in cui il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servizio Agent gestisce i processi.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-103">Use this page to view and modify how the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service manages jobs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ec6bf-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ec6bf-104">Options</span></span>  
 <span data-ttu-id="ec6bf-105">**Intervallo di timeout chiusura (secondi)**</span><span class="sxs-lookup"><span data-stu-id="ec6bf-105">**Shutdown time-out interval (in seconds)**</span></span>  
 <span data-ttu-id="ec6bf-106">Consente di specificare il numero di secondi di attesa del completamento dei processi prima che questi vengano chiusi da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-106">Specifies the number of seconds that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for jobs to complete before shutting down.</span></span> <span data-ttu-id="ec6bf-107">Se il processo è ancora in esecuzione dopo la scadenza dell'intervallo specificato, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent lo arresterà in modo forzato.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-107">If the job is still running after the interval specified, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent forcefully stops the job.</span></span>  
  
 <span data-ttu-id="ec6bf-108">**Usa account proxy non amministratore**</span><span class="sxs-lookup"><span data-stu-id="ec6bf-108">**Use a non-administrator proxy account**</span></span>  
 <span data-ttu-id="ec6bf-109">Imposta un account proxy non amministratore per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-109">Sets a non-administrator proxy account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="ec6bf-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]e versioni successive supportano più proxy, pertanto questa opzione è applicabile solo quando si gestisce [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Versioni di Agent precedenti a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ec6bf-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="ec6bf-111">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="ec6bf-111">**User name**</span></span>  
 <span data-ttu-id="ec6bf-112">Digitare il nome dell'utente per l'account proxy non amministratore.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-112">Type the name of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ec6bf-113">supporta più proxy, pertanto questa opzione è applicabile unicamente quando si gestiscono versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent precedenti a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec6bf-113">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="ec6bf-114">**Password**</span><span class="sxs-lookup"><span data-stu-id="ec6bf-114">**Password**</span></span>  
 <span data-ttu-id="ec6bf-115">Digitare la password dell'utente per l'account proxy non amministratore.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-115">Type the password of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="ec6bf-116">e versioni successive supportano più proxy, pertanto questa opzione è applicabile unicamente quando si gestiscono le versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec6bf-116">and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="ec6bf-117">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ec6bf-117">**Domain**</span></span>  
 <span data-ttu-id="ec6bf-118">Digitare il dominio dell'utente per l'account proxy non amministratore.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-118">Type the domain of the user for the non-administrative proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ec6bf-119">supporta più proxy, pertanto questa opzione è applicabile unicamente quando si gestiscono versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent precedenti a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec6bf-119">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6bf-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec6bf-120">See Also</span></span>  
 [<span data-ttu-id="ec6bf-121">Implementazione di processi</span><span class="sxs-lookup"><span data-stu-id="ec6bf-121">Implement Jobs</span></span>](implement-jobs.md)  
  
  
