---
title: 'Proprietà avviso: nuovo avviso (pagina Opzioni) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.options.f1
ms.assetid: 6e4f41aa-832d-46ba-b6b5-cf1d3b15d33f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a1507372aa1516c2a88b8682faa77a7d57e58f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722227"
---
# <a name="alert-properties-new-alert-options-page"></a><span data-ttu-id="d6c22-102">Proprietà avviso: Nuovo avviso (pagina Opzioni)</span><span class="sxs-lookup"><span data-stu-id="d6c22-102">Alert Properties: New Alert (Options Page)</span></span>
  <span data-ttu-id="d6c22-103">Utilizzare questa pagina per visualizzare e modificare le opzioni per gli [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avvisi di Agent.</span><span class="sxs-lookup"><span data-stu-id="d6c22-103">Use this page to view and modify options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d6c22-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d6c22-104">Options</span></span>  
 <span data-ttu-id="d6c22-105">**Posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d6c22-105">**E-mail**</span></span>  
 <span data-ttu-id="d6c22-106">Consente di includere l'eventuale testo dell'errore risultante dall'evento nelle notifiche inviate tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d6c22-106">Include error text from the event, if any, in e-mail notifications.</span></span>  
  
 <span data-ttu-id="d6c22-107">**Cercapersone**</span><span class="sxs-lookup"><span data-stu-id="d6c22-107">**Pager**</span></span>  
 <span data-ttu-id="d6c22-108">Consente di includere l'eventuale testo dell'errore risultante dall'evento nelle notifiche inviate tramite cercapersone.</span><span class="sxs-lookup"><span data-stu-id="d6c22-108">Include error text from the event, if any, in pager notifications.</span></span>  
  
 <span data-ttu-id="d6c22-109">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="d6c22-109">**Net send**</span></span>  
 <span data-ttu-id="d6c22-110">Consente di includere l'eventuale testo dell'errore risultante dall'evento nelle notifiche Net Send.</span><span class="sxs-lookup"><span data-stu-id="d6c22-110">Include error text from the event, if any, in net send notifications.</span></span>  
  
 <span data-ttu-id="d6c22-111">**Messaggio di notifica aggiuntivo da inviare**</span><span class="sxs-lookup"><span data-stu-id="d6c22-111">**Additional notification message to send**</span></span>  
 <span data-ttu-id="d6c22-112">Consente di digitare un testo aggiuntivo da includere nei messaggi di notifica.</span><span class="sxs-lookup"><span data-stu-id="d6c22-112">Type any additional text to include in notification messages.</span></span>  
  
 <span data-ttu-id="d6c22-113">**Intervallo tra le risposte**</span><span class="sxs-lookup"><span data-stu-id="d6c22-113">**Delay between responses**</span></span>  
 <span data-ttu-id="d6c22-114">Consente di specificare un ritardo per le occorrenze ripetute dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d6c22-114">Specify a delay for repeated occurrences of the event.</span></span> <span data-ttu-id="d6c22-115">È possibile che alcuni eventi si verifichino frequentemente durante un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d6c22-115">Some events may occur frequently during a short period of time.</span></span> <span data-ttu-id="d6c22-116">In questo caso, è possibile che si desideri sapere che l'evento si è verificato ma che non si desideri ricevere una risposta per ogni evento.</span><span class="sxs-lookup"><span data-stu-id="d6c22-116">In this case, you may want to know that the event has occurred, but you may not want a response for every event.</span></span> <span data-ttu-id="d6c22-117">Usare questa opzione per specificare un timeout. Con un ritardo, dopo la risposta dell'avviso a un evento, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent attende il ritardo specificato prima di rispondere di nuovo, indipendentemente dal fatto che l'evento si verifichi durante il ritardo.</span><span class="sxs-lookup"><span data-stu-id="d6c22-117">Use this option to specify a time-out. With a delay, after the alert responds to an event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for the delay specified before responding again, regardless of whether the event occurs during the delay.</span></span>  
  
 <span data-ttu-id="d6c22-118">**Minuti**</span><span class="sxs-lookup"><span data-stu-id="d6c22-118">**Minutes**</span></span>  
 <span data-ttu-id="d6c22-119">Consente di specificare un ritardo in minuti.</span><span class="sxs-lookup"><span data-stu-id="d6c22-119">Specify a delay in minutes.</span></span> <span data-ttu-id="d6c22-120">Per attivare una risposta ogni volta che si verifica l'evento, specificare 0 minuti e 0 secondi.</span><span class="sxs-lookup"><span data-stu-id="d6c22-120">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
 <span data-ttu-id="d6c22-121">**Secondi**</span><span class="sxs-lookup"><span data-stu-id="d6c22-121">**Seconds**</span></span>  
 <span data-ttu-id="d6c22-122">Consente di specificare un ritardo in secondi.</span><span class="sxs-lookup"><span data-stu-id="d6c22-122">Specify a delay in seconds.</span></span> <span data-ttu-id="d6c22-123">Per attivare una risposta ogni volta che si verifica l'evento, specificare 0 minuti e 0 secondi.</span><span class="sxs-lookup"><span data-stu-id="d6c22-123">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c22-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6c22-124">See Also</span></span>  
 [<span data-ttu-id="d6c22-125">Avvisi</span><span class="sxs-lookup"><span data-stu-id="d6c22-125">Alerts</span></span>](alerts.md)  
  
  
