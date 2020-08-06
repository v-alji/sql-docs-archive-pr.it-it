---
title: Configurare notifiche di posta elettronica (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- e-mail [Master Data Services], configuring
- notifications [Master Data Services], configuring notifications
ms.assetid: 4241a6ab-7465-471b-9890-57c6b572037e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: baf60677435122af00f5ee5492e47bafaa45a3ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638451"
---
# <a name="configure-email-notifications-master-data-services"></a><span data-ttu-id="a218f-102">Configurare notifiche di posta elettronica (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a218f-102">Configure Email Notifications (Master Data Services)</span></span>
  <span data-ttu-id="a218f-103">Per fare in modo che [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] invii automaticamente messaggi di posta elettronica, è necessario configurare messaggi di posta elettronica di notifica.</span><span class="sxs-lookup"><span data-stu-id="a218f-103">Configure notification emails when you want [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email messages automatically.</span></span>  
  
### <a name="to-configure-notifications"></a><span data-ttu-id="a218f-104">Per configurare le notifiche</span><span class="sxs-lookup"><span data-stu-id="a218f-104">To configure notifications</span></span>  
  
1.  <span data-ttu-id="a218f-105">Nella pagina [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]Database **di** selezionare il database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a218f-105">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], on the **Database** page, select your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="a218f-106">Nella sezione **Impostazioni sistema** fare clic su **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="a218f-106">In the **System Settings** section, click **Create Profile**.</span></span>  
  
3.  <span data-ttu-id="a218f-107">Completare tutti i campi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="a218f-107">Complete all required fields.</span></span> <span data-ttu-id="a218f-108">Per altre informazioni, vedere [Finestra di dialogo Crea account e profilo di Posta elettronica database &#40;Gestione configurazione Master Data Services&#41;](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="a218f-108">For more information, see [Create Database Mail Profile and Account Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span></span>  
  
4.  <span data-ttu-id="a218f-109">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a218f-109">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a218f-110">Dopo avere configurato le notifiche, non è possibile usare [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] per apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="a218f-110">After you configure notifications, you cannot use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to make changes.</span></span> <span data-ttu-id="a218f-111">È necessario apportare le modifiche direttamente nel database di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a218f-111">You must make changes directly in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="a218f-112">Per altre informazioni, vedere [Oggetti di configurazione di Posta elettronica database](../relational-databases/database-mail/database-mail-configuration-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a218f-112">For more information, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a218f-113">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a218f-113">Next Steps</span></span>  
  
-   <span data-ttu-id="a218f-114">Alcune impostazioni di [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] hanno effetto sulle notifiche.</span><span class="sxs-lookup"><span data-stu-id="a218f-114">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="a218f-115">È possibile regolare tali impostazioni in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] o direttamente nella tabella Impostazioni sistema del database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a218f-115">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="a218f-116">Per altre informazioni, vedere [Impostazioni di sistema &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a218f-116">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a218f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a218f-117">See Also</span></span>  
 <span data-ttu-id="a218f-118">[Notifiche &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a218f-118">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="a218f-119">[Risoluzione dei problemi relativi alle notifiche tramite posta elettronica (Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span><span class="sxs-lookup"><span data-stu-id="a218f-119">[Troubleshooting Email Notifications (Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span></span>  
 [<span data-ttu-id="a218f-120">Configurare le regole di business per l'invio di notifiche &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a218f-120">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
