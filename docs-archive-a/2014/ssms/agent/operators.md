---
title: Operatori | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- operators (users) [Database Engine]
- fail-safe operator [SQL Server]
- aliases [SQL Server], operators
- SQL Server Agent alerts, operators
- contact information [SQL Server Agent]
- net send [SQL Server]
- e-mail [SQL Server], SQL Server Agent operators
- pager notifications [SQL Server Agent]
- mail [SQL Server], SQL Server Agent operators
- operators (users) [Database Engine], defining
- jobs [SQL Server Agent], operators
- alerts [SQL Server], operators
ms.assetid: 38e8488f-2669-4cea-b9c3-5f394a663678
author: stevestein
ms.author: sstein
ms.openlocfilehash: d141a2db9a69603701200bc50dcac57ef402968a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720790"
---
# <a name="operators"></a><span data-ttu-id="16786-102">Operatori</span><span class="sxs-lookup"><span data-stu-id="16786-102">Operators</span></span>
  <span data-ttu-id="16786-103">Gli operatori sono alias per persone o gruppi che possono ricevere notifiche elettroniche a completamento dei processi o quando vengono generati avvisi.</span><span class="sxs-lookup"><span data-stu-id="16786-103">Operators are aliases for people or groups that can receive electronic notification when jobs have completed or alerts have been raised.</span></span> <span data-ttu-id="16786-104">Il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent supporta il servizio di notifica degli amministratori tramite gli operatori.</span><span class="sxs-lookup"><span data-stu-id="16786-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service supports the notification of administrators through operators.</span></span> <span data-ttu-id="16786-105">Gli operatori consentono di abilitare la notifica e le funzionalità di monitoraggio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="16786-105">Operators enable notification and monitoring capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="operator-attributes-and-concepts"></a><span data-ttu-id="16786-106">Attributi e concetti relativi agli operatori</span><span class="sxs-lookup"><span data-stu-id="16786-106">Operator Attributes and Concepts</span></span>  
 <span data-ttu-id="16786-107">Gli attributi principali di un operatore sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="16786-107">The primary attributes of an operator are:</span></span>  
  
-   <span data-ttu-id="16786-108">Nome operatore</span><span class="sxs-lookup"><span data-stu-id="16786-108">Operator name</span></span>  
  
-   <span data-ttu-id="16786-109">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="16786-109">Contact information</span></span>  
  
### <a name="naming-an-operator"></a><span data-ttu-id="16786-110">Denominazione di un operatore</span><span class="sxs-lookup"><span data-stu-id="16786-110">Naming an Operator</span></span>  
 <span data-ttu-id="16786-111">A ogni operatore deve essere assegnato un nome.</span><span class="sxs-lookup"><span data-stu-id="16786-111">Every operator must have a name.</span></span> <span data-ttu-id="16786-112">I nomi degli operatori devono essere univoci nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e non possono essere formati da più di **128** caratteri.</span><span class="sxs-lookup"><span data-stu-id="16786-112">Operator names must be unique within the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and can be no longer than **128** characters.</span></span>  
  
### <a name="contact-information"></a><span data-ttu-id="16786-113">Informazioni sul contatto</span><span class="sxs-lookup"><span data-stu-id="16786-113">Contact Information</span></span>  
 <span data-ttu-id="16786-114">Le informazioni sul contatto di un operatore definiscono la modalità di trasmissione delle notifiche all'operatore.</span><span class="sxs-lookup"><span data-stu-id="16786-114">An operator's contact information defines how the operator is notified.</span></span> <span data-ttu-id="16786-115">Gli operatori possono ricevere notifiche tramite posta elettronica o cercapersone oppure tramite il comando **Net Send** :</span><span class="sxs-lookup"><span data-stu-id="16786-115">Operators can be notified by e-mail, pager, or through the **net send** command:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="16786-116">Le opzioni Cercapersone e **net send** verranno rimosse da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in una versione futura di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16786-116">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="16786-117">Evitare pertanto di utilizzarle in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui sono state implementate.</span><span class="sxs-lookup"><span data-stu-id="16786-117">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="16786-118">**Notifica tramite posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="16786-118">**E-mail notification**</span></span>  
  
     <span data-ttu-id="16786-119">La notifica tramite posta elettronica prevede l'invio di un messaggio di posta elettronica all'operatore.</span><span class="sxs-lookup"><span data-stu-id="16786-119">E-mail notification sends an e-mail message to the operator.</span></span> <span data-ttu-id="16786-120">Per la notifica tramite posta elettronica, è necessario specificare l'indirizzo di posta elettronica dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="16786-120">For e-mail notification, you provide the e-mail address for the operator.</span></span>  
  
-   <span data-ttu-id="16786-121">**Notifica tramite cercapersone**</span><span class="sxs-lookup"><span data-stu-id="16786-121">**Pager notification**</span></span>  
  
     <span data-ttu-id="16786-122">I messaggi vengono inviati al cercapersone tramite la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="16786-122">Paging is implemented by e-mail.</span></span> <span data-ttu-id="16786-123">Per la notifica tramite cercapersone, è necessario specificare l'indirizzo di posta elettronica in cui l'operatore riceve i messaggi del cercapersone.</span><span class="sxs-lookup"><span data-stu-id="16786-123">For pager notification, you provide the e-mail address where the operator receives pager messages.</span></span> <span data-ttu-id="16786-124">Per configurare la notifica tramite cercapersone, è necessario installare nel server di posta un prodotto software che elabori i messaggi di posta in arrivo e li converta in messaggi per cercapersone.</span><span class="sxs-lookup"><span data-stu-id="16786-124">To set up pager notification, you must install software on the mail server that processes inbound mail and converts it to a pager message.</span></span> <span data-ttu-id="16786-125">Il software può operare in diversi modi, tra cui quelli indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="16786-125">The software can take one of several approaches, including:</span></span>  
  
    -   <span data-ttu-id="16786-126">Inoltro della posta a un server di posta remoto nel sito del provider del cercapersone.</span><span class="sxs-lookup"><span data-stu-id="16786-126">Forwarding the mail to a remote mail server at the site of the pager provider.</span></span>  
  
         <span data-ttu-id="16786-127">È necessario che il provider del cercapersone offra questo servizio, anche se il software necessario fa in genere parte del sistema di posta elettronica locale.</span><span class="sxs-lookup"><span data-stu-id="16786-127">The pager provider must offer this service, although the software required is generally available as part of the local mail system.</span></span> <span data-ttu-id="16786-128">Per ulteriori informazioni, vedere la documentazione del cercapersone.</span><span class="sxs-lookup"><span data-stu-id="16786-128">For more information, see your pager documentation.</span></span>  
  
    -   <span data-ttu-id="16786-129">Routing della posta tramite Internet a un server di posta elettronica appartenente al sito del provider del cercapersone.</span><span class="sxs-lookup"><span data-stu-id="16786-129">Routing the e-mail by way of the Internet to an e-mail server at the pager provider's site.</span></span>  
  
         <span data-ttu-id="16786-130">Si tratta di una variante della modalità descritta in precedenza.</span><span class="sxs-lookup"><span data-stu-id="16786-130">This is a variation on the first approach.</span></span>  
  
    -   <span data-ttu-id="16786-131">Elaborazione della posta in arrivo e composizione del numero del cercapersone tramite un modem collegato.</span><span class="sxs-lookup"><span data-stu-id="16786-131">Processing the inbound e-mail and dialing the pager by using an attached modem.</span></span>  
  
         <span data-ttu-id="16786-132">Il prodotto software è di proprietà del provider del servizio cercapersone.</span><span class="sxs-lookup"><span data-stu-id="16786-132">This software is proprietary to pager service providers.</span></span> <span data-ttu-id="16786-133">Il software funziona come client di posta elettronica che elabora periodicamente la posta in arrivo, interpretando una parte dell'indirizzo del messaggio di posta o l'intero indirizzo come numero di cercapersone oppure trovando la corrispondenza tra l'indirizzo di posta elettronica e un numero di cercapersone in una tabella di conversione.</span><span class="sxs-lookup"><span data-stu-id="16786-133">The software acts as a e-mail client that periodically processes its inbox either by interpreting all or part of the e-mail address information as a pager number, or by matching the e-mail name to a pager number in a translation table.</span></span>  
  
         <span data-ttu-id="16786-134">Se tutti gli operatori utilizzano lo stesso provider di cercapersone, è possibile utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per specificare l'eventuale formattazione speciale richiesta dal sistema di comunicazione tra il cercapersone e la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="16786-134">If all of the operators share a pager provider, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to specify any special e-mail formatting that is required by the pager-to-e-mail system.</span></span> <span data-ttu-id="16786-135">La formattazione speciale può essere costituita da un prefisso o da un suffisso e inserita nelle righe seguenti del messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="16786-135">The special formatting can be a prefix or a suffix and can be included in the following lines of the e-mail:</span></span>  
  
         <span data-ttu-id="16786-136">**Soggetto:**</span><span class="sxs-lookup"><span data-stu-id="16786-136">**Subject:**</span></span>  
  
         <span data-ttu-id="16786-137">**Cc**:</span><span class="sxs-lookup"><span data-stu-id="16786-137">**Cc**:</span></span>  
  
         <span data-ttu-id="16786-138">**A**:</span><span class="sxs-lookup"><span data-stu-id="16786-138">**To**:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16786-139">Se si utilizza un sistema di cercapersone alfanumerico a capacità limitata, è possibile ridurre il numero di caratteri escludendo dalla notifica su cercapersone il testo del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="16786-139">If you use a low-capacity alphanumeric paging system, you can shorten the text that is sent by excluding the error text from the pager notification.</span></span> <span data-ttu-id="16786-140">Vi sono, ad esempio, sistemi di cercapersone alfanumerici con un limite di 64 caratteri per chiamata.</span><span class="sxs-lookup"><span data-stu-id="16786-140">An example of a low-capacity alphanumeric paging system is one that is limited to 64 characters per page.</span></span>  
  
-   <span data-ttu-id="16786-141">**notifica Net Send**</span><span class="sxs-lookup"><span data-stu-id="16786-141">**net sendnotification**</span></span>  
  
     <span data-ttu-id="16786-142">Questa modalità prevede l'invio all'operatore di un messaggio tramite il comando **Net Send** .</span><span class="sxs-lookup"><span data-stu-id="16786-142">This sends a message to the operator by means of the **net send** command.</span></span> <span data-ttu-id="16786-143">Per la notifica tramite comando **Net Send**, è necessario specificare il destinatario, costituito da un computer o un utente, di un messaggio di rete.</span><span class="sxs-lookup"><span data-stu-id="16786-143">For **net send**, specify the recipient (computer or user) of a network message.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16786-144">Il comando **Net Send** prevede l'uso di Microsoft Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="16786-144">The **net send** command uses Microsoft Windows Messenger.</span></span> <span data-ttu-id="16786-145">Per consentire il corretto invio degli avvisi, il servizio deve essere in esecuzione sia nel computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che in quello utilizzato dall'operatore.</span><span class="sxs-lookup"><span data-stu-id="16786-145">To successfully send alerts, this service must be running on both the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running and the computer that the operator uses.</span></span>  
  
## <a name="alerting-and-fail-safe-operators"></a><span data-ttu-id="16786-146">Invio di notifiche degli avvisi agli operatori e operatori alternativi</span><span class="sxs-lookup"><span data-stu-id="16786-146">Alerting and Fail-Safe Operators</span></span>  
 <span data-ttu-id="16786-147">È possibile selezionare gli operatori che dovranno ricevere le notifiche in risposta a un avviso.</span><span class="sxs-lookup"><span data-stu-id="16786-147">You can choose which operators are to be notified in response to an alert.</span></span> <span data-ttu-id="16786-148">Si possono ad esempio assegnare a rotazione le responsabilità degli operatori tramite la pianificazione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="16786-148">For example, you can assign rotating responsibilities for operator notification by scheduling alerts.</span></span> <span data-ttu-id="16786-149">Ad esempio, la persona A riceverà notifiche degli avvisi generati lunedì, mercoledì o venerdì, mentre la persona B riceverà notifiche degli avvisi generati martedì, giovedì e sabato.</span><span class="sxs-lookup"><span data-stu-id="16786-149">For example, Individual A is notified of alerts that occur on Monday, Wednesday, or Friday, and Individual B is notified of alerts that occur on Tuesday, Thursday, or Saturday.</span></span>  
  
 <span data-ttu-id="16786-150">L'operatore alternativo riceve una notifica relativa a un avviso quando nessuna delle notifiche agli operatori designati tramite cercapersone è riuscita.</span><span class="sxs-lookup"><span data-stu-id="16786-150">The fail-safe operator receives an alert notification after all pager notifications to the designated operators have failed.</span></span> <span data-ttu-id="16786-151">Se, ad esempio, sono stati definiti tre operatori per le notifiche tramite cercapersone e nessuno di questi operatori è raggiungibile, verrà trasmessa una notifica all'operatore alternativo.</span><span class="sxs-lookup"><span data-stu-id="16786-151">For example, if you have defined three operators for pager notifications and none of the designated operators can be paged, the fail-safe operator is notified.</span></span>  
  
 <span data-ttu-id="16786-152">L'operatore alternativo riceve una notifica nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="16786-152">The fail-safe operator is notified when:</span></span>  
  
-   <span data-ttu-id="16786-153">Gli operatori ai quali è destinato l'avviso non sono raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="16786-153">The operators responsible for the alert could not be paged.</span></span>  
  
     <span data-ttu-id="16786-154">L'impossibilità di raggiungere tali operatori potrebbe essere dovuta a un errore negli indirizzi dei cercapersone o al fatto che gli operatori non sono in servizio.</span><span class="sxs-lookup"><span data-stu-id="16786-154">Reasons for failure to reach primary operators include incorrect pager addresses and off-duty operators.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="16786-155">Agent non è in grado di accedere alle tabelle di sistema nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="16786-155">Agent cannot access system tables in the **msdb** database.</span></span>  
  
     <span data-ttu-id="16786-156">La tabella di sistema **sysnotifications** specifica le responsabilità degli operatori per i vari tipi di avvisi.</span><span class="sxs-lookup"><span data-stu-id="16786-156">The **sysnotifications** system table specifies operator responsibilities for alerts.</span></span>  
  
 <span data-ttu-id="16786-157">L'operatore alternativo rappresenta una funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="16786-157">The fail-safe operator is a security feature.</span></span> <span data-ttu-id="16786-158">Per questo motivo, non è possibile eliminare l'operatore assegnato a tale compito se non dopo avere riassegnato l'incarico a un altro operatore o avere eliminato completamente l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="16786-158">You cannot delete the operator assigned to fail-safe duty without reassigning fail-safe duty to another operator, or deleting the fail-safe assignment altogether.</span></span>  
  
## <a name="notifying-an-operator"></a><span data-ttu-id="16786-159">Invio di una notifica a un operatore</span><span class="sxs-lookup"><span data-stu-id="16786-159">Notifying an Operator</span></span>  
 <span data-ttu-id="16786-160">Per inviare una notifica a un operatore, è necessario configurare una o più impostazioni tra le seguenti:</span><span class="sxs-lookup"><span data-stu-id="16786-160">You must set up one or more of the following in order to notify an operator:</span></span>  
  
-   <span data-ttu-id="16786-161">Per inviare messaggi di posta elettronica tramite la funzionalità Posta elettronica database, è necessario disporre di accesso a un server di posta che supporti SMTP.</span><span class="sxs-lookup"><span data-stu-id="16786-161">To send e-mail with Database Mail functionality, you must have access to an e-mail server that supports SMTP.</span></span>  
  
-   <span data-ttu-id="16786-162">Per inviare messaggi su cercapersone, è necessario disporre di componenti hardware e/o software di terze parti per il collegamento tra il cercapersone e la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="16786-162">For paging, you must have third-party pager-to-e-mail software and/or hardware.</span></span>  
  
-   <span data-ttu-id="16786-163">Per usare il comando **Net Send**, l'operatore deve essere connesso al computer specificato e il computer specificato deve consentire la ricezione di messaggi da Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="16786-163">To use **net send**, the operator must be logged on to the specified computer, and the specified computer must allow messages from Windows Messenger.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="16786-164">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="16786-164">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16786-165">**Attività**</span><span class="sxs-lookup"><span data-stu-id="16786-165">**Tasks**</span></span>|<span data-ttu-id="16786-166">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="16786-166">**Topic**</span></span>|  
|<span data-ttu-id="16786-167">Attività correlate alla creazione di un operatore</span><span class="sxs-lookup"><span data-stu-id="16786-167">Tasks related to creating an operator</span></span>|[<span data-ttu-id="16786-168">Creazione di un operatore</span><span class="sxs-lookup"><span data-stu-id="16786-168">Create an Operator</span></span>](create-an-operator.md)<br /><br /> [<span data-ttu-id="16786-169">Designate a Fail-Safe Operator</span><span class="sxs-lookup"><span data-stu-id="16786-169">Designate a Fail-Safe Operator</span></span>](designate-a-fail-safe-operator.md)|  
|<span data-ttu-id="16786-170">Attività correlate all'assegnazione di avvisi</span><span class="sxs-lookup"><span data-stu-id="16786-170">Tasks related to assigning alerts</span></span>|[<span data-ttu-id="16786-171">Assegnazione di avvisi a un operatore</span><span class="sxs-lookup"><span data-stu-id="16786-171">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)<br /><br /> [<span data-ttu-id="16786-172">Definizione della risposta a un avviso &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="16786-172">Define the Response to an Alert &#40;SQL Server Management Studio&#41;</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)<br /><br /> [<span data-ttu-id="16786-173">sp_add_notification &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="16786-173">sp_add_notification &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)<br /><br /> [<span data-ttu-id="16786-174">Assegnazione di avvisi a un operatore</span><span class="sxs-lookup"><span data-stu-id="16786-174">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)|  
  
## <a name="see-also"></a><span data-ttu-id="16786-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16786-175">See Also</span></span>  
 [<span data-ttu-id="16786-176">Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="16786-176">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
