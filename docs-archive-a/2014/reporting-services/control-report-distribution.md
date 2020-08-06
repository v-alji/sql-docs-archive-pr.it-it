---
title: Controllare la distribuzione del report | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], report distribution
- subscriptions [Reporting Services], e-mail
- subscriptions [Reporting Services], file share delivery
- file share delivery [Reporting Services]
- e-mail [Reporting Services]
- subscriptions [Reporting Services], security
- mail [Reporting Services]
ms.assetid: 8f15e2c6-a647-4b05-a519-1743b5d8654c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de8a27801ef89f10bf303cee17d1c2d0e1081c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623056"
---
# <a name="control-report-distribution"></a><span data-ttu-id="2cb8d-102">Controllare la distribuzione dei report</span><span class="sxs-lookup"><span data-stu-id="2cb8d-102">Control Report Distribution</span></span>
  <span data-ttu-id="2cb8d-103">È possibile configurare un server di report in modo da ridurre i rischi di sicurezza associati alla distribuzione tramite posta elettronica e condivisione file.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-103">You can configure a report server to reduce the security risks associated with e-mail and file share distribution.</span></span>  
  
## <a name="securing-reports"></a><span data-ttu-id="2cb8d-104">sicurezza di report</span><span class="sxs-lookup"><span data-stu-id="2cb8d-104">Securing Reports</span></span>  
 <span data-ttu-id="2cb8d-105">Per controllare la distribuzione dei report, è innanzitutto necessario proteggerli dall'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-105">The first step in controlling report distribution is to secure the report against unauthorized access.</span></span> <span data-ttu-id="2cb8d-106">Per poter essere utilizzato in una sottoscrizione, un report deve utilizzare un set di credenziali archiviate che rimangano invariate per i singoli recapiti.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-106">To be used in a subscription, a report must use a stored set of credentials that do not vary for individual deliveries.</span></span> <span data-ttu-id="2cb8d-107">Gli utenti che possono accedere al report nel server di report possono eseguirlo ed eventualmente distribuirlo.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-107">Any user who can access the report on the report server can run it and possibly distribute it.</span></span> <span data-ttu-id="2cb8d-108">Per evitare che ciò accada, è necessario limitare l'accesso ai report solo agli utenti per i quali è strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-108">To prevent this from occurring, you must limit report access to only those users who require it.</span></span> <span data-ttu-id="2cb8d-109">Per altre informazioni, vedere [proteggere i report e le risorse](security/secure-reports-and-resources.md) e [proteggere le cartelle](security/secure-folders.md).</span><span class="sxs-lookup"><span data-stu-id="2cb8d-109">For more information, see [Secure Reports and Resources](security/secure-reports-and-resources.md) and [Secure Folders](security/secure-folders.md).</span></span>  
  
 <span data-ttu-id="2cb8d-110">I report con contenuto strettamente riservato che utilizzano la sicurezza dei database per autorizzare gli accessi non possono essere distribuiti tramite sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-110">Highly confidential reports that use database security to authorize access cannot be distributed by way of subscription.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2cb8d-111">I report vengono trasportati come file.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-111">Reports are transported as files.</span></span> <span data-ttu-id="2cb8d-112">I rischi e le precauzioni per i file equivalgono a quelli per i report che vengono salvati su disco o inviati come allegati.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-112">The risks and safeguards that apply to files apply equally to reports that are saved to disk or sent as attachments.</span></span> <span data-ttu-id="2cb8d-113">Un utente che accede a un file può distribuirlo o utilizzarlo a propria discrezione.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-113">Any user who has access to a file can distribute or use the file at his or her discretion.</span></span>  
  
## <a name="controlling-e-mail-delivery"></a><span data-ttu-id="2cb8d-114">Controllo del recapito tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2cb8d-114">Controlling E-Mail Delivery</span></span>  
 <span data-ttu-id="2cb8d-115">È possibile configurare un server di report in modo che la distribuzione tramite posta elettronica sia circoscritta a domini host specifici.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-115">You can configure a report server to limit e-mail distribution to specific host domains.</span></span> <span data-ttu-id="2cb8d-116">È possibile, ad esempio, fare in modo che un server di report recapiti un report solo ai domini indicati nel file di configurazione RSReportServer.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-116">For example, you can prevent a report server from delivering a report to all domains except those listed in the RSReportServer configuration file.</span></span>  
  
 <span data-ttu-id="2cb8d-117">È inoltre possibile definire le impostazioni di configurazione in modo che il campo **A** di una sottoscrizione venga nascosto.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-117">You can also set configuration settings to hide the **To** field in a subscription.</span></span> <span data-ttu-id="2cb8d-118">In questo caso, i report verranno recapitati solo all'utente che definisce la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-118">In this case, reports are delivered only to the user defining the subscription.</span></span> <span data-ttu-id="2cb8d-119">Non è tuttavia possibile impedire a un utente che ha ricevuto un report di inoltrarlo.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-119">However, after a report is sent to a user, you cannot explicitly prevent it from being forwarded.</span></span>  
  
 <span data-ttu-id="2cb8d-120">Il modo più efficace per controllare la distribuzione dei report consiste nel configurare un server di report in modo che invii unicamente un URL del server di report.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-120">The most effective way to control report distribution is to configure a report server to send only a report server URL.</span></span> <span data-ttu-id="2cb8d-121">Il server di report utilizza l'autenticazione di Windows e un modello di autorizzazione basata sui ruoli per controllare l'accesso a un report.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-121">The report server uses Windows Authentication and a role-based authorization model to control access to a report.</span></span> <span data-ttu-id="2cb8d-122">Se un utente riceve per errore tramite posta elettronica un report che non è autorizzato a visualizzare, il server di report non visualizzerà il report.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-122">If a user accidentally receives through e-mail a report that he or she is not authorized to view, the report server will not display the report.</span></span>  
  
## <a name="controlling-file-share-delivery"></a><span data-ttu-id="2cb8d-123">Controllo del recapito tramite condivisione file</span><span class="sxs-lookup"><span data-stu-id="2cb8d-123">Controlling File Share Delivery</span></span>  
 <span data-ttu-id="2cb8d-124">Il recapito tramite condivisione file viene utilizzato per inviare un report a un file presente su un disco rigido.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-124">File share delivery is used to send a report to a file on a hard disk.</span></span> <span data-ttu-id="2cb8d-125">Dopo essere stato salvato su disco, un file non è più soggetto al modello di sicurezza basata sui ruoli utilizzato dal server di report per controllare gli accessi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-125">After the file has been saved to disk, it is no longer subject to the role-based security model that the report server uses to control user access.</span></span> <span data-ttu-id="2cb8d-126">Per proteggere un report recapitato a un disco rigido, è possibile associare elenchi di controllo di accesso (ACL) al file stesso o alla cartella che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-126">To secure a report that has been delivered to disk, you can place Access Control Lists (ACLs) on the file itself or on the folder that contains it.</span></span> <span data-ttu-id="2cb8d-127">In base al sistema operativo, potrebbero essere disponibili ulteriori opzioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2cb8d-127">Additional security options might be available, depending on your operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb8d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cb8d-128">See Also</span></span>  
 <span data-ttu-id="2cb8d-129">[Configurare un server di report per il recapito tramite posta elettronica &#40;Configuration Manager SSRS&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2cb8d-129">[Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="2cb8d-130">[Sottoscrizioni e recapito &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="2cb8d-130">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="2cb8d-131">Creare e gestire sottoscrizioni per server di report in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="2cb8d-131">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../../2014/reporting-services/create-manage-subscriptions-native-mode-report-servers.md)  
  
  
