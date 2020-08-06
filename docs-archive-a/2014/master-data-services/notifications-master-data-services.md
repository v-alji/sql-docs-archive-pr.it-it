---
title: Notifiche (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- notifications [Master Data Services]
- notifications [Master Data Services], about notifications
- e-mail [Master Data Services]
- e-mail [Master Data Services], about e-mail notifications
ms.assetid: d7ad32d5-9fe5-48fd-8c61-0b00c0aff082
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a61825f9450dd5b708aff8c3fc72f0f12732337b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637382"
---
# <a name="notifications-master-data-services"></a><span data-ttu-id="235a1-102">Notifiche (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="235a1-102">Notifications (Master Data Services)</span></span>
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]<span data-ttu-id="235a1-103">può essere configurato per inviare una notifica tramite posta elettronica quando la convalida delle regole business ha esito negativo o se lo stato di una versione del modello viene modificato.</span><span class="sxs-lookup"><span data-stu-id="235a1-103">can be configured to send an email notification when business rule validation fails or the status of a model version changes.</span></span>  
  
## <a name="how-notifications-are-sent"></a><span data-ttu-id="235a1-104">Modalità di invio delle notifiche</span><span class="sxs-lookup"><span data-stu-id="235a1-104">How Notifications Are Sent</span></span>  
 <span data-ttu-id="235a1-105">È possibile configurare notifiche in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="235a1-105">You configure notifications in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="235a1-106">Le notifiche inviano messaggi di posta elettronica utilizzando Posta elettronica database nell'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] che ospita il [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="235a1-106">Notifications send email messages by using Database Mail on the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that hosts the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="235a1-107">Per altre informazioni su Posta elettronica database, vedere la sezione [Oggetti di configurazione di Posta elettronica database](../relational-databases/database-mail/database-mail-configuration-objects.md) nella documentazione online di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="235a1-107">For more information about Database Mail, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="when-notifications-are-sent"></a><span data-ttu-id="235a1-108">Quando vengono inviate le notifiche</span><span class="sxs-lookup"><span data-stu-id="235a1-108">When Notifications Are Sent</span></span>  
 <span data-ttu-id="235a1-109">Dopo la configurazione delle notifiche, è possibile inviare notifiche automatiche tramite posta elettronica nelle due istanze seguenti.</span><span class="sxs-lookup"><span data-stu-id="235a1-109">After notifications are configured, automated email notifications can be sent in the following instances.</span></span>  
  
|<span data-ttu-id="235a1-110">Istanza</span><span class="sxs-lookup"><span data-stu-id="235a1-110">Instance</span></span>|<span data-ttu-id="235a1-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="235a1-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="235a1-112">La convalida dei dati tramite regole business ha esito negativo</span><span class="sxs-lookup"><span data-stu-id="235a1-112">Data fails business rule validation</span></span>|<span data-ttu-id="235a1-113">È necessario configurare singole regole business per l'invio di posta elettronica quando la convalida tramite regole business di un valore di attributo ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="235a1-113">Individual business rules must be configured to send email when an attribute value fails business rule validation.</span></span> <span data-ttu-id="235a1-114">Per altre informazioni, vedere [Configurare le regole di business per l'invio di notifiche &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="235a1-114">For more information, see [Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span></span>|  
|<span data-ttu-id="235a1-115">Lo stato della versione di un modello viene modificato</span><span class="sxs-lookup"><span data-stu-id="235a1-115">Model version status changes</span></span>|<span data-ttu-id="235a1-116">Ogni volta che lo stato della versione di un modello viene modificato, vengono inviate automaticamente notifiche agli utenti configurati come amministratori del modello.</span><span class="sxs-lookup"><span data-stu-id="235a1-116">Each time a model version's status changes, users that are model administrators receive notifications automatically.</span></span> <span data-ttu-id="235a1-117">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="235a1-117">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>|  
  
## <a name="system-settings"></a><span data-ttu-id="235a1-118">Impostazioni sistema</span><span class="sxs-lookup"><span data-stu-id="235a1-118">System Settings</span></span>  
 <span data-ttu-id="235a1-119">Alcune impostazioni di [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] hanno effetto sulle notifiche.</span><span class="sxs-lookup"><span data-stu-id="235a1-119">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="235a1-120">È possibile regolare tali impostazioni in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] o direttamente nella tabella Impostazioni sistema del database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="235a1-120">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="235a1-121">Per altre informazioni, vedere [Impostazioni di sistema &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="235a1-121">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="235a1-122">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="235a1-122">Related Tasks</span></span>  
  
|<span data-ttu-id="235a1-123">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="235a1-123">Task Description</span></span>|<span data-ttu-id="235a1-124">Argomento</span><span class="sxs-lookup"><span data-stu-id="235a1-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="235a1-125">Configurare [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] per inviare notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="235a1-125">Configure [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email notifications.</span></span>|[<span data-ttu-id="235a1-126">Configurare notifiche di posta elettronica &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="235a1-126">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)|  
|<span data-ttu-id="235a1-127">Configurare [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] per inviare notifiche quando i valori dell'attributo vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="235a1-127">Configure [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to send notifications when attribute values change.</span></span>|[<span data-ttu-id="235a1-128">Configurare le regole di business per l'invio di notifiche &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="235a1-128">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](configure-business-rules-to-send-notifications-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="235a1-129">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="235a1-129">Related Content</span></span>  
  
-   [<span data-ttu-id="235a1-130">Regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="235a1-130">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="235a1-131">Versioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="235a1-131">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
-   [<span data-ttu-id="235a1-132">Risoluzione dei problemi relativi alle notifiche di posta elettronica (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="235a1-132">Troubleshooting Email Notifications (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx)  
  
  
