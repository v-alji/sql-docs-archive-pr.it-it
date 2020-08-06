---
title: Sospendere l'elaborazione di report e sottoscrizioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- subscriptions [Reporting Services], pausing
- report processing [Reporting Services], pausing
- shared data sources [Reporting Services]
- pausing subscription processing
- pausing report processing
- temporarily stopping report processing
- disabling shared data sources
- roles [Reporting Services], modifying
- shared schedules [Reporting Services], pausing
ms.assetid: 3cf9a240-24cc-46d4-bec6-976f82d8f830
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1607637630c507588602dd7e566917ce1eeb6080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721053"
---
# <a name="pause-report-and-subscription-processing"></a><span data-ttu-id="a6bc5-102">Sospendere l'elaborazione del report e della sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="a6bc5-102">Pause Report and Subscription Processing</span></span>
  <span data-ttu-id="a6bc5-103">Non è possibile sospendere direttamente un report o una sottoscrizione,</span><span class="sxs-lookup"><span data-stu-id="a6bc5-103">You cannot pause a report or subscription directly.</span></span> <span data-ttu-id="a6bc5-104">tuttavia è possibile interromperne l'elaborazione prima dell'avvio del processo o quando viene stabilita una connessione all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-104">However, you can interrupt report and subscription processing prior to the process starting or when a data source connection is made.</span></span> <span data-ttu-id="a6bc5-105">È inoltre possibile impedire l'elaborazione di una sottoscrizione o di un report rendendolo inaccessibile agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-105">You can also prevent a report or subscription from processing by making it inaccessible to users.</span></span>  
  
 <span data-ttu-id="a6bc5-106">Per impedire temporaneamente un'elaborazione, utilizzare le strategie seguenti.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-106">The following strategies can be used to temporarily prevent a process from occurring.</span></span>  
  
## <a name="modify-role-assignments-to-prevent-access"></a><span data-ttu-id="a6bc5-107">Modifica delle assegnazioni di ruolo per impedire l'accesso</span><span class="sxs-lookup"><span data-stu-id="a6bc5-107">Modify Role Assignments to Prevent Access</span></span>  
 <span data-ttu-id="a6bc5-108">Il modo migliore per rendere non disponibile un report consiste nel rimuovere temporaneamente l'assegnazione di ruolo che consente l'accesso al report.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-108">The best way to make a report unavailable is to temporarily remove the role assignment that provides access to the report.</span></span> <span data-ttu-id="a6bc5-109">Questa strategia può essere utilizzata con tutti i report, indipendentemente dalla modalità di connessione all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-109">This approach can be used on all reports regardless of how the data source connection is made.</span></span> <span data-ttu-id="a6bc5-110">L'operazione ha effetto solo sul report in questione, non su altri report o elementi.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-110">This approach targets only the report, without affecting the operation of other reports or items.</span></span>  
  
 <span data-ttu-id="a6bc5-111">Per rimuovere l'assegnazione di ruolo, aprire la pagina delle proprietà sicurezza del report in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-111">To remove the role assignment, open the Security Properties page of the report in Report Manager.</span></span> <span data-ttu-id="a6bc5-112">Se il report eredita la sicurezza da un elemento padre, è possibile fare clic su **Modifica sicurezza elemento** per creare criteri di sicurezza restrittivi privi di assegnazioni di ruolo che consentono l'accesso a numerosi utenti. È possibile, ad esempio, rimuovere un'assegnazione di ruolo che consente l'accesso al gruppo Everyone e mantenere l'assegnazione di ruolo che consente l'accesso a un gruppo ristretto di utenti, ad esempio Administrators.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-112">If the report inherits security from a parent, you can click **Edit Item Security** to create a restrictive security policy that omits role assignments that provide widespread access (for example, you can remove a role assignment that provides access to Everyone, and keep the role assignment that provides access to a small group of users, such as Administrators).</span></span>  
  
## <a name="disable-a-shared-data-source"></a><span data-ttu-id="a6bc5-113">Disabilitazione di un'origine dei dati condivisa</span><span class="sxs-lookup"><span data-stu-id="a6bc5-113">Disable a Shared Data Source</span></span>  
 <span data-ttu-id="a6bc5-114">Uno dei vantaggi dell'utilizzo di origini dei dati condivise è rappresentato dalla possibilità di disabilitarle per impedire l'esecuzione di un report o di una sottoscrizione guidata dai dati.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-114">One advantage to using shared data sources is that you can disable it to prevent a report or data-driven subscription from running.</span></span> <span data-ttu-id="a6bc5-115">Quando si disabilita un'origine dei dati condivisa, il report viene disconnesso dalla relativa origine dei dati esterna.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-115">Disabling a shared data source disconnects the report from its external source.</span></span> <span data-ttu-id="a6bc5-116">Dopo la disabilitazione l'origine dei dati non sarà più disponibile per tutti i report e le sottoscrizioni che la utilizzano.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-116">While it is disabled, the data source is unavailable to all reports and subscriptions that use it.</span></span> <span data-ttu-id="a6bc5-117">Per disabilitare un'origine dati condivisa, aprire l'origine dati in Gestione report e deselezionare la casella di controllo **Abilita questa origine dati** .</span><span class="sxs-lookup"><span data-stu-id="a6bc5-117">To disable a shared data source, open the data source in Report Manager and clear the **Enable this data source** check box.</span></span>  
  
 <span data-ttu-id="a6bc5-118">Si noti che il report viene caricato anche se la relativa origine dei dati non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-118">Note that the report still loads even if the data source is unavailable.</span></span> <span data-ttu-id="a6bc5-119">Il report non conterrà dati, ma gli utenti con le autorizzazioni appropriate potranno accedere alle pagine delle proprietà, alle impostazioni di sicurezza, alla cronologia e alle informazioni di sottoscrizione associate al report.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-119">The report does not contain data, but users with appropriate permissions can access the property pages, security settings, report history, and subscription information associated with the report.</span></span>  
  
## <a name="pause-a-shared-schedule"></a><span data-ttu-id="a6bc5-120">Sospensione di una pianificazione condivisa</span><span class="sxs-lookup"><span data-stu-id="a6bc5-120">Pause a Shared Schedule</span></span>  
 <span data-ttu-id="a6bc5-121">Se una sottoscrizione o un report viene eseguito in base a una pianificazione condivisa, è possibile sospendere la pianificazione per impedire l'elaborazione del report o della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-121">If a report or subscription runs from a shared schedule, you can pause the schedule to prevent processing.</span></span> <span data-ttu-id="a6bc5-122">Tutte le operazioni di elaborazione del report o della sottoscrizione eseguite in base alla pianificazione verranno posticipate fino a quando verrà ripresa la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a6bc5-122">All report and subscription processing that is driven by the schedule is deferred until the schedule is resumed.</span></span> <span data-ttu-id="a6bc5-123">Per altre informazioni, vedere [sospendere e riprendere le pianificazioni condivise](schedules.md).</span><span class="sxs-lookup"><span data-stu-id="a6bc5-123">For more information, see [Pause and Resume Shared Schedules](schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6bc5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6bc5-124">See Also</span></span>  
 <span data-ttu-id="a6bc5-125">[Server di report di Reporting Services &#40;modalità nativa&#41;](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a6bc5-125">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="a6bc5-126">[Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a6bc5-126">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="a6bc5-127">Pagina delle proprietà sicurezza, Elementi &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="a6bc5-127">Security Properties Page, Items &#40;Report Manager&#41;</span></span>](../security-properties-page-items-report-manager.md)  
  
  
