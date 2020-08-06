---
title: Proprietà SQL Server Agent (pagina Sistema avvisi) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.alert.f1
ms.assetid: 3e6d3bfd-20ee-4593-86cc-f65b1c08c69d
author: stevestein
ms.author: sstein
ms.openlocfilehash: ff203be21efbd99b90f02261cfe94dd49bd0d849
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636521"
---
# <a name="sql-server-agent-properties-alert-system-page"></a><span data-ttu-id="13f79-102">Proprietà SQL Server Agent (pagina Sistema avvisi)</span><span class="sxs-lookup"><span data-stu-id="13f79-102">SQL Server Agent Properties (Alert System Page)</span></span>
  <span data-ttu-id="13f79-103">Usare questa pagina per visualizzare e modificare le impostazioni per i messaggi inviati dagli avvisi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="13f79-103">Use this page to view and modify the settings for messages sent by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="13f79-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="13f79-104">Options</span></span>  
 <span data-ttu-id="13f79-105">**Sessione di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="13f79-105">**Mail session**</span></span>  
 <span data-ttu-id="13f79-106">Le opzioni incluse in questa sezione consentono di configurare la posta elettronica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="13f79-106">The options in this section configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span>  
  
 <span data-ttu-id="13f79-107">**Abilita profilo di posta**</span><span class="sxs-lookup"><span data-stu-id="13f79-107">**Enable mail profile**</span></span>  
 <span data-ttu-id="13f79-108">Consente di abilitare la posta elettronica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="13f79-108">Enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span> <span data-ttu-id="13f79-109">Per impostazione predefinita, la posta elettronica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="13f79-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail is not enabled.</span></span>  
  
 <span data-ttu-id="13f79-110">**Sistema di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="13f79-110">**Mail System**</span></span>  
 <span data-ttu-id="13f79-111">Consente di impostare il sistema di posta elettronica utilizzato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="13f79-111">Sets the mail system for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="13f79-112">Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="13f79-112">Database Mail</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13f79-113">Dopo avere modificato il sistema di posta elettronica, è necessario riavviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per rendere operative le modifiche.</span><span class="sxs-lookup"><span data-stu-id="13f79-113">After changing the e-mail system, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service for the change to take effect.</span></span>  
  
 <span data-ttu-id="13f79-114">**Profilo posta**</span><span class="sxs-lookup"><span data-stu-id="13f79-114">**Mail Profile**</span></span>  
 <span data-ttu-id="13f79-115">Consente di impostare il profilo che deve essere utilizzato in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="13f79-115">Sets the profile for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="13f79-116">È possibile selezionare **\<new Database Mail profile...>** anche per creare un nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="13f79-116">You may also select **\<new Database Mail profile...>** to create a new profile.</span></span>  
  
 <span data-ttu-id="13f79-117">**Messaggi di posta elettronica tramite cercapersone**</span><span class="sxs-lookup"><span data-stu-id="13f79-117">**Pager e-mails**</span></span>  
 <span data-ttu-id="13f79-118">Le opzioni incluse in questa sezione consentono di configurare i messaggi di posta elettronica inviati a indirizzi di cercapersone in modo che possano funzionare con il sistema di cercapersone utilizzato.</span><span class="sxs-lookup"><span data-stu-id="13f79-118">The options in this section allow you to configure e-mail messages sent to pager addresses to work with your paging system.</span></span>  
  
 <span data-ttu-id="13f79-119">**Formato indirizzo per messaggi di posta elettronica tramite cercapersone**</span><span class="sxs-lookup"><span data-stu-id="13f79-119">**Address formatting for pager e-mails**</span></span>  
 <span data-ttu-id="13f79-120">Questa sezione consente di specificare il formato degli indirizzi e della riga dell'oggetto dei messaggi di posta elettronica inviati tramite cercapersone.</span><span class="sxs-lookup"><span data-stu-id="13f79-120">This section allows you to specify the format of the addresses and the subject line included in pager e-mails.</span></span>  
  
 <span data-ttu-id="13f79-121">**Riga A**</span><span class="sxs-lookup"><span data-stu-id="13f79-121">**To line**</span></span>  
 <span data-ttu-id="13f79-122">Consente di specificare le opzioni della riga **A** del messaggio</span><span class="sxs-lookup"><span data-stu-id="13f79-122">Specifies the options for the **To** line of the message</span></span>  
  
 <span data-ttu-id="13f79-123">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="13f79-123">**Prefix**</span></span>  
 <span data-ttu-id="13f79-124">Consente di digitare un testo fisso richiesto dal sistema di cercapersone all'inizio della riga **A** dei messaggi inviati a un cercapersone.</span><span class="sxs-lookup"><span data-stu-id="13f79-124">Type any fixed text that your system requires at the beginning of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="13f79-125">**Cercapersone**</span><span class="sxs-lookup"><span data-stu-id="13f79-125">**Pager**</span></span>  
 <span data-ttu-id="13f79-126">Consente di includere l'indirizzo di posta elettronica del messaggio tra il prefisso e il suffisso.</span><span class="sxs-lookup"><span data-stu-id="13f79-126">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="13f79-127">**Suffisso**</span><span class="sxs-lookup"><span data-stu-id="13f79-127">**Suffix**</span></span>  
 <span data-ttu-id="13f79-128">Consente di digitare un testo fisso richiesto dal sistema di cercapersone alla fine della riga **A** dei messaggi inviati a un cercapersone.</span><span class="sxs-lookup"><span data-stu-id="13f79-128">Type any fixed text that your paging system requires at the end of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="13f79-129">**Riga Cc**</span><span class="sxs-lookup"><span data-stu-id="13f79-129">**Cc line**</span></span>  
 <span data-ttu-id="13f79-130">Consente di specificare le opzioni della riga **Cc** del messaggio.</span><span class="sxs-lookup"><span data-stu-id="13f79-130">Specifies options for the **Cc** line of the message.</span></span>  
  
 <span data-ttu-id="13f79-131">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="13f79-131">**Prefix**</span></span>  
 <span data-ttu-id="13f79-132">Consente di digitare un testo fisso richiesto dal sistema di cercapersone all'inizio della riga **Cc** dei messaggi inviati a un cercapersone.</span><span class="sxs-lookup"><span data-stu-id="13f79-132">Type any fixed text that your system requires at the beginning of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="13f79-133">**Cercapersone**</span><span class="sxs-lookup"><span data-stu-id="13f79-133">**Pager**</span></span>  
 <span data-ttu-id="13f79-134">Consente di includere l'indirizzo di posta elettronica del messaggio tra il prefisso e il suffisso.</span><span class="sxs-lookup"><span data-stu-id="13f79-134">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="13f79-135">**Suffisso**</span><span class="sxs-lookup"><span data-stu-id="13f79-135">**Suffix**</span></span>  
 <span data-ttu-id="13f79-136">Consente di digitare un testo fisso richiesto dal sistema di cercapersone alla fine della riga **Cc** dei messaggi inviati a un cercapersone.</span><span class="sxs-lookup"><span data-stu-id="13f79-136">Type any fixed text that your paging system requires at the end of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="13f79-137">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="13f79-137">**Subject**</span></span>  
 <span data-ttu-id="13f79-138">Consente di specificare le opzioni dell'oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="13f79-138">Specifies the options for the subject of the message.</span></span>  
  
 <span data-ttu-id="13f79-139">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="13f79-139">**Prefix**</span></span>  
 <span data-ttu-id="13f79-140">Consente di digitare un testo fisso richiesto dal sistema di cercapersone all'inizio della riga **Oggetto** dei messaggi inviati a un cercapersone.</span><span class="sxs-lookup"><span data-stu-id="13f79-140">Type any fixed text that your paging system requires at the beginning of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="13f79-141">**Suffisso**</span><span class="sxs-lookup"><span data-stu-id="13f79-141">**Suffix**</span></span>  
 <span data-ttu-id="13f79-142">Consente di digitare un testo fisso richiesto dal sistema di cercapersone alla fine della riga **Oggetto** dei messaggi inviati a un cercapersone.</span><span class="sxs-lookup"><span data-stu-id="13f79-142">Type any fixed text that your paging system requires at the end of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="13f79-143">**Includi corpo del messaggio nel messaggio di notifica**</span><span class="sxs-lookup"><span data-stu-id="13f79-143">**Include body of e-mail in notification message**</span></span>  
 <span data-ttu-id="13f79-144">Consente di includere il corpo del messaggio di posta elettronica nel messaggio inviato al cercapersone.</span><span class="sxs-lookup"><span data-stu-id="13f79-144">Includes the body of the e-mail message in the message sent to the pager.</span></span>  
  
 <span data-ttu-id="13f79-145">**Operatore alternativo**</span><span class="sxs-lookup"><span data-stu-id="13f79-145">**Fail-safe operator**</span></span>  
 <span data-ttu-id="13f79-146">Questa sezione consente di specificare le opzioni dell'operatore alternativo.</span><span class="sxs-lookup"><span data-stu-id="13f79-146">This section allows you to specify the options for the fail-safe operator.</span></span>  
  
 <span data-ttu-id="13f79-147">**Abilita operatore alternativo**</span><span class="sxs-lookup"><span data-stu-id="13f79-147">**Enable fail-safe operator**</span></span>  
 <span data-ttu-id="13f79-148">Consente di specificare un operatore alternativo.</span><span class="sxs-lookup"><span data-stu-id="13f79-148">Specifies a fail safe operator.</span></span>  
  
 <span data-ttu-id="13f79-149">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="13f79-149">**Operator**</span></span>  
 <span data-ttu-id="13f79-150">Consente di impostare il nome dell'operatore alternativo a cui inviare le notifiche.</span><span class="sxs-lookup"><span data-stu-id="13f79-150">Sets the name of the operator to receive fail-safe notifications.</span></span>  
  
 <span data-ttu-id="13f79-151">**Notifica tramite**</span><span class="sxs-lookup"><span data-stu-id="13f79-151">**Notify using**</span></span>  
 <span data-ttu-id="13f79-152">Consente di impostare la modalità di invio delle notifiche all'operatore alternativo.</span><span class="sxs-lookup"><span data-stu-id="13f79-152">Sets the method to use for notifying the fail-safe operator.</span></span>  
  
 <span data-ttu-id="13f79-153">**Sostituzione token**</span><span class="sxs-lookup"><span data-stu-id="13f79-153">**Token Replacement**</span></span>  
 <span data-ttu-id="13f79-154">Questa sezione consente di abilitare i token dei passaggi del processo che possono essere utilizzati nei processi eseguiti dagli avvisi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="13f79-154">This section allows you to enable job step tokens that can be used in jobs run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="13f79-155">Per altre informazioni sui token dei passaggi dei processi, vedere [Utilizzo dei token nei passaggi dei processi](use-tokens-in-job-steps.md).</span><span class="sxs-lookup"><span data-stu-id="13f79-155">For more information about job step tokens, see [Use Tokens in Job Steps](use-tokens-in-job-steps.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="13f79-156">Qualsiasi utente di Windows che disponga di autorizzazioni di scrittura per il registro eventi di Windows può accedere ai passaggi dei processi attivati dagli avvisi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="13f79-156">Any Windows user with write permissions on the Windows Event Log may be able to access job steps that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="13f79-157">Per evitare rischi per la sicurezza, i token di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che possono essere utilizzati in processi attivati dagli avvisi sono disabilitati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="13f79-157">To avoid this security risk, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tokens that can be used in jobs activated by alerts are disabled by default.</span></span> <span data-ttu-id="13f79-158">I token interessati sono: **$(A-DBN)** , **$(A-SVR)** , **$(A-ERR)** , **$(A-SEV)** e **$(A-MSG)** .</span><span class="sxs-lookup"><span data-stu-id="13f79-158">These tokens are: **$(A-DBN)**, **$(A-SVR)**, **$(A-ERR)**, **$(A-SEV)**, and **$(A-MSG)**.</span></span>  
>   
>  <span data-ttu-id="13f79-159">Se è necessario utilizzare tali token, prima di abilitarli verificare che solo i membri di gruppi di sicurezza di Windows trusted, ad esempio il gruppo Administrators, dispongano di autorizzazioni di scrittura per il registro eventi del computer in cui è installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13f79-159">If you need to use these tokens, ensure that only members of trusted Windows security groups, such as the Administrators group, have write permissions on the Event Log of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resides before enabling them.</span></span>  
  
 <span data-ttu-id="13f79-160">**Sostituisci token per tutte le risposte del processo ad avvisi**</span><span class="sxs-lookup"><span data-stu-id="13f79-160">**Replace tokens for all job responses to alerts**</span></span>  
 <span data-ttu-id="13f79-161">Selezionare questa casella di controllo per abilitare la sostituzione dei token per i processi attivati dagli avvisi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13f79-161">Select this check box to enable token replacement for jobs that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f79-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13f79-162">See Also</span></span>  
 <span data-ttu-id="13f79-163">[Operatori](operators.md) </span><span class="sxs-lookup"><span data-stu-id="13f79-163">[Operators](operators.md) </span></span>  
 <span data-ttu-id="13f79-164">[Configurare SQL Server Agent Mail per l'uso di Posta elettronica database](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="13f79-164">[Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span></span>  
 [<span data-ttu-id="13f79-165">Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="13f79-165">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
