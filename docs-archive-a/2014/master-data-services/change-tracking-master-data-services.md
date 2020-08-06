---
title: Rilevamento modifiche (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server]
ms.assetid: 5e879c65-0d38-454f-9a20-62a6e72c89f7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2d3b69057b02884f41a43aa9a009ab3db937ed25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716408"
---
# <a name="change-tracking-master-data-services"></a><span data-ttu-id="7c300-102">Rilevamento modifiche (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7c300-102">Change Tracking (Master Data Services)</span></span>
  <span data-ttu-id="7c300-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è possibile utilizzare gruppi rilevamento delle modifiche per eseguire un'azione quando cambia un valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="7c300-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can use change tracking groups to take action when an attribute value changes.</span></span> <span data-ttu-id="7c300-104">Usare il rilevamento modifiche quando non si conosce il nuovo valore, ma si desidera sapere se sono state apportate modifiche.</span><span class="sxs-lookup"><span data-stu-id="7c300-104">Use change tracking when you don't know what the new value will be, but instead want to know if any change occurred.</span></span>  
  
## <a name="configuring-change-tracking"></a><span data-ttu-id="7c300-105">Configurazione del rilevamento modifiche</span><span class="sxs-lookup"><span data-stu-id="7c300-105">Configuring Change Tracking</span></span>  
 <span data-ttu-id="7c300-106">Per configurare il rilevamento modifiche, aggiungere un attributo a un gruppo rilevamento modifiche.</span><span class="sxs-lookup"><span data-stu-id="7c300-106">To configure change tracking, you add an attribute to a change tracking group.</span></span> <span data-ttu-id="7c300-107">Il gruppo può contenere uno o molti attributi.</span><span class="sxs-lookup"><span data-stu-id="7c300-107">The group can contain one or many attributes.</span></span> <span data-ttu-id="7c300-108">Creare quindi una regola business per definire l'azione da eseguire quando uno degli attributi del gruppo vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="7c300-108">Then, you create a business rule to define the action that is taken when any of the attributes in the group change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c300-109">Le regole business del rilevamento modifiche considerano i dati in gestione temporanea (importati) come modificati.</span><span class="sxs-lookup"><span data-stu-id="7c300-109">Change tracking business rules consider staged (imported) data to be changed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7c300-110">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7c300-110">Related Tasks</span></span>  
  
|<span data-ttu-id="7c300-111">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="7c300-111">Task Description</span></span>|<span data-ttu-id="7c300-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="7c300-112">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="7c300-113">Aggiungere attributi a un gruppo rilevamento modifiche.</span><span class="sxs-lookup"><span data-stu-id="7c300-113">Add attributes to a change tracking group.</span></span>|[<span data-ttu-id="7c300-114">Aggiungere attributi ad un gruppo rilevamento modifiche &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c300-114">Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;</span></span>](add-attributes-to-a-change-tracking-group-master-data-services.md)|  
|<span data-ttu-id="7c300-115">Creare una regola business per avviare azioni in base alle modifiche apportate agli attributi.</span><span class="sxs-lookup"><span data-stu-id="7c300-115">Create a business rule that initiates actions based on attribute changes.</span></span>|[<span data-ttu-id="7c300-116">Inizializzare azioni basate su modifiche dei valori di attributo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c300-116">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="7c300-117">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="7c300-117">Related Content</span></span>  
  
-   [<span data-ttu-id="7c300-118">Convalida &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c300-118">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
-   [<span data-ttu-id="7c300-119">Regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c300-119">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="7c300-120">Attributi &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7c300-120">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
