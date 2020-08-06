---
title: Configurare regole business per l'invio di notifiche (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], configuring notifications
- e-mail [Master Data Services], configuring business rules
- notifications [Master Data Services], configuring business rules
ms.assetid: b24f7b11-ab53-4642-999c-e17b543b3558
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cb1a12167dffe123e55760f031e21499fe22a945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638452"
---
# <a name="configure-business-rules-to-send-notifications-master-data-services"></a><span data-ttu-id="cd115-102">Configurare regole business per l'invio di notifiche (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="cd115-102">Configure Business Rules to Send Notifications (Master Data Services)</span></span>
  <span data-ttu-id="cd115-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è possibile configurare le regole di business per inviare notifiche agli utenti relative alle modifiche dei valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="cd115-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], configure business rules to send notifications when you want to notify users about attribute value changes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cd115-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cd115-104">Prerequisites</span></span>  
 <span data-ttu-id="cd115-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="cd115-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="cd115-106">È necessario disporre dell'autorizzazione per accedere alle aree funzionali **Amministrazione sistema** e **Autorizzazioni utenti e gruppi** .</span><span class="sxs-lookup"><span data-stu-id="cd115-106">You must have permission to access the **System Administration** and **User and Group Permissions** functional areas.</span></span> <span data-ttu-id="cd115-107">Se non si dispone dell'autorizzazione per l'area funzionale **Autorizzazioni utenti e gruppi** , non è possibile visualizzare l'elenco di utenti e gruppi cui inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="cd115-107">If you do not have permission to the **User and Group Permissions** functional area, you cannot view the list of users and groups to send notifications to.</span></span>  
  
-   <span data-ttu-id="cd115-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="cd115-108">You must be a model administrator.</span></span> <span data-ttu-id="cd115-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cd115-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="cd115-110">È necessario che sia presente una regola business che utilizza un'azione di convalida.</span><span class="sxs-lookup"><span data-stu-id="cd115-110">A business rule that uses a validation action must already exist.</span></span> <span data-ttu-id="cd115-111">Per altre informazioni, vedere [Creare e pubblicare una regola di business &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cd115-111">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="cd115-112">È necessario che l'utente o il gruppo che riceve la notifica disponga almeno dell'autorizzazione **Sola lettura** per l'attributo la cui convalida ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cd115-112">The user or group that receives the notification must have at least **Read-only** permission to the attribute that fails validation.</span></span> <span data-ttu-id="cd115-113">Gli utenti o gruppi a cui è stata negata in modo esplicito o implicito l'autorizzazione all'attributo riceveranno la posta elettronica ma non potranno accedere all'attributo in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd115-113">Users or groups that are explicitly or implicitly denied permission to the attribute will receive the email but will not be able to access the attribute in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="cd115-114">Se i messaggi di posta elettronica vengono inviati a un gruppo, verranno ricevuti dai soli membri del gruppo che hanno effettuato l'accesso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd115-114">If mail is sent to a group, only members of the group that have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] will get the email.</span></span>  
  
### <a name="to-configure-business-rules-to-send-notifications"></a><span data-ttu-id="cd115-115">Per configurare le regole business per l'invio di notifiche</span><span class="sxs-lookup"><span data-stu-id="cd115-115">To configure business rules to send notifications</span></span>  
  
1.  <span data-ttu-id="cd115-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="cd115-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="cd115-117">Dalla barra dei menu scegliere **Gestisci** e fare clic su **Regole business**.</span><span class="sxs-lookup"><span data-stu-id="cd115-117">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="cd115-118">Nella pagina **Manutenzione regola business** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="cd115-118">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="cd115-119">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="cd115-119">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="cd115-120">Dall'elenco **tipo di membro** selezionare un tipo di membro.</span><span class="sxs-lookup"><span data-stu-id="cd115-120">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="cd115-121">Dall'elenco **Attributo** selezionare un attributo o lasciare inalterata l'impostazione predefinita **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="cd115-121">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="cd115-122">Nella griglia fare doppio clic sul campo **notifica** nella riga relativa alla regola business.</span><span class="sxs-lookup"><span data-stu-id="cd115-122">In the grid, in the row for the business rule, double-click the **Notification** field.</span></span>  
  
8.  <span data-ttu-id="cd115-123">Dal sottomenu scegliere un utente o un gruppo a cui inviare la notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="cd115-123">From the sub-menu, click a user or group to send the email notification to.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cd115-124">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cd115-124">Next Steps</span></span>  
  
-   <span data-ttu-id="cd115-125">Applicare regole business ai dati eseguendo una delle procedure riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="cd115-125">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="cd115-126">Convalidare membri specifici rispetto a regole business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cd115-126">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="cd115-127">Convalidare una versione usando le regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cd115-127">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   <span data-ttu-id="cd115-128">Configurare il protocollo della posta elettronica come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cd115-128">Configure the email protocol as follows:</span></span>  
  
    -   [<span data-ttu-id="cd115-129">Configurare notifiche di posta elettronica &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cd115-129">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="cd115-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd115-130">See Also</span></span>  
 <span data-ttu-id="cd115-131">[Notifiche &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cd115-131">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 [<span data-ttu-id="cd115-132">Configurare notifiche di posta elettronica &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cd115-132">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
  
