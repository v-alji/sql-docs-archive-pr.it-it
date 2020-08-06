---
title: Configurare avvisi per notificare agli amministratori eventuali errori dei criteri| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, configure alerts
ms.assetid: e8e60159-d5b0-49d5-91f3-af8e9cb994c1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9eb84ced3bb6313dd5920deaf479925556f08fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711896"
---
# <a name="configure-alerts-to-notify-policy-administrators-of-policy-failures"></a><span data-ttu-id="e660a-102">Configurare avvisi per notificare agli amministratori eventuali errori dei criteri</span><span class="sxs-lookup"><span data-stu-id="e660a-102">Configure Alerts to Notify Policy Administrators of Policy Failures</span></span>
  <span data-ttu-id="e660a-103">Se si verifica una violazione quando i criteri di gestione basata su criteri vengono eseguiti in una delle tre modalità di valutazione automatiche, viene scritto un messaggio nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="e660a-103">When Policy-Based Management policies are executed in one of the three automated evaluation modes, if a policy violation occurs, a message is written to the event log.</span></span> <span data-ttu-id="e660a-104">Per ricevere una notifica relativa all'avvenuta scrittura del messaggio nel registro eventi, è possibile creare un avviso per rilevare il messaggio ed eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="e660a-104">To be notified when this message is written to the event log, you can create an alert to detect the message and perform an action.</span></span> <span data-ttu-id="e660a-105">L'avviso dovrà rilevare i messaggi come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e660a-105">The alert should detect the messages as shown in the following table.</span></span>  
  
|<span data-ttu-id="e660a-106">Modalità di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e660a-106">Execution mode</span></span>|<span data-ttu-id="e660a-107">Numero di messaggio</span><span class="sxs-lookup"><span data-stu-id="e660a-107">Message number</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="e660a-108">Su modifica: impedisci esecuzione</span><span class="sxs-lookup"><span data-stu-id="e660a-108">On change: prevent</span></span><br /><br /> <span data-ttu-id="e660a-109">(se automatica)</span><span class="sxs-lookup"><span data-stu-id="e660a-109">(if automatic)</span></span>|<span data-ttu-id="e660a-110">34050</span><span class="sxs-lookup"><span data-stu-id="e660a-110">34050</span></span>|  
|<span data-ttu-id="e660a-111">Su modifica: impedisci esecuzione</span><span class="sxs-lookup"><span data-stu-id="e660a-111">On change: prevent</span></span><br /><br /> <span data-ttu-id="e660a-112">(se Su richiesta)</span><span class="sxs-lookup"><span data-stu-id="e660a-112">(if On demand)</span></span>|<span data-ttu-id="e660a-113">34051</span><span class="sxs-lookup"><span data-stu-id="e660a-113">34051</span></span>|  
|<span data-ttu-id="e660a-114">Su pianificazione</span><span class="sxs-lookup"><span data-stu-id="e660a-114">On schedule</span></span>|<span data-ttu-id="e660a-115">34052</span><span class="sxs-lookup"><span data-stu-id="e660a-115">34052</span></span>|  
|<span data-ttu-id="e660a-116">Su modifica</span><span class="sxs-lookup"><span data-stu-id="e660a-116">On change</span></span>|<span data-ttu-id="e660a-117">34053</span><span class="sxs-lookup"><span data-stu-id="e660a-117">34053</span></span>|  
  
 <span data-ttu-id="e660a-118">Per configurare un avviso per rispondere ai messaggi di errore relativi alla gestione basata su criteri, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e660a-118">To set up an alert to respond to the Policy-Based Management error messages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="e660a-119">Creazione di un operatore</span><span class="sxs-lookup"><span data-stu-id="e660a-119">Create an Operator</span></span>](../../ssms/agent/create-an-operator.md)  
  
-   [<span data-ttu-id="e660a-120">Creazione di un avviso utilizzando un numero di errore</span><span class="sxs-lookup"><span data-stu-id="e660a-120">Create an Alert Using an Error Number</span></span>](../../ssms/agent/create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="e660a-121">Assegnazione di avvisi a un operatore</span><span class="sxs-lookup"><span data-stu-id="e660a-121">Assign Alerts to an Operator</span></span>](../../ssms/agent/assign-alerts-to-an-operator.md)  
  
## <a name="permissions"></a><span data-ttu-id="e660a-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e660a-122">Permissions</span></span>  
 <span data-ttu-id="e660a-123">Quando i criteri vengono valutati su richiesta, vengono eseguiti nel contesto di sicurezza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e660a-123">When policies are evaluated on demand, they execute in the security context of the user.</span></span> <span data-ttu-id="e660a-124">Per poter scrivere nel log degli errori, l'utente deve disporre di autorizzazioni ALTER TRACE o deve essere un membro del ruolo predefinito del server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="e660a-124">To write to the error log, the user must have ALTER TRACE permissions or be a member of the sysadmin fixed server role.</span></span> <span data-ttu-id="e660a-125">I criteri valutati da un utente che dispone di privilegi di livello inferiore non verranno scritti nel registro eventi e non genereranno un avviso.</span><span class="sxs-lookup"><span data-stu-id="e660a-125">Policies that are evaluated by a user that has less privileges will not write to the event log, and will not fire an alert.</span></span>  
  
 <span data-ttu-id="e660a-126">Le modalità di esecuzione automatiche possono essere eseguite solo da membri del ruolo sysadmin.</span><span class="sxs-lookup"><span data-stu-id="e660a-126">The automated execution modes execute as a member of the sysadmin role.</span></span> <span data-ttu-id="e660a-127">Tale ruolo consente la scrittura dei criteri nel log degli errori e la generazione di un avviso.</span><span class="sxs-lookup"><span data-stu-id="e660a-127">This allows the policy to write to the error log and raise an alert.</span></span>  
  
## <a name="additional-considerations-about-alerts"></a><span data-ttu-id="e660a-128">Considerazioni aggiuntive sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="e660a-128">Additional Considerations About Alerts</span></span>  
 <span data-ttu-id="e660a-129">Tenere presente le considerazioni aggiuntive seguenti relative agli avvisi:</span><span class="sxs-lookup"><span data-stu-id="e660a-129">Be aware of the following additional considerations about alerts:</span></span>  
  
-   <span data-ttu-id="e660a-130">Gli avvisi vengono generati solo per i criteri abilitati.</span><span class="sxs-lookup"><span data-stu-id="e660a-130">Alerts are raised only for policies that are enabled.</span></span> <span data-ttu-id="e660a-131">Poiché i criteri **Su richiesta** non possono essere abilitati, non vengono generati avvisi per i criteri eseguiti su richiesta.</span><span class="sxs-lookup"><span data-stu-id="e660a-131">Because **On demand** policies cannot be enabled, alerts are not raised for policies that are executed on demand.</span></span>  
  
-   <span data-ttu-id="e660a-132">Se l'azione che si desidera eseguire include l'invio di un messaggio di posta elettronica, è necessario configurare un account di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e660a-132">If the action you want to take includes sending an e-mail message, you must configure a mail account.</span></span> <span data-ttu-id="e660a-133">È consigliabile utilizzare Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="e660a-133">We recommend that you use Database Mail.</span></span> <span data-ttu-id="e660a-134">Per altre informazioni su come configurare Posta elettronica database, vedere [Creare un account di Posta elettronica database](../database-mail/create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="e660a-134">For more information about how to set up Database Mail, see [Create a Database Mail Account](../database-mail/create-a-database-mail-account.md).</span></span>  
  
  
