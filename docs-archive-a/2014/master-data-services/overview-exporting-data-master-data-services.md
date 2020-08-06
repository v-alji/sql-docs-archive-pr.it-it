---
title: Esportazione di dati (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- exporting data [Master Data Services]
- subscription views [Master Data Services]
- subscription views [Master Data Services], about subscription views
ms.assetid: 8b74409a-ea70-45f8-84c7-da6905e4901a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: edae5b996c25a1b6053231ed2f69ef511b9fbfa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628782"
---
# <a name="exporting-data-master-data-services"></a><span data-ttu-id="fb97d-102">Esportazione di dati (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="fb97d-102">Exporting Data (Master Data Services)</span></span>
  <span data-ttu-id="fb97d-103">È possibile esportare dati [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] nei sistemi di sottoscrizione creando viste delle sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="fb97d-103">You can export [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] data to subscribing systems by creating subscriptions views.</span></span> <span data-ttu-id="fb97d-104">Qualsiasi sistema di sottoscrizione può visualizzare quindi i dati pubblicati nel database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb97d-104">Any subscribing system can then view the published data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="fb97d-105">Per ulteriori informazioni sulle viste, consultare la sezione [Viste](../relational-databases/views/views.md).</span><span class="sxs-lookup"><span data-stu-id="fb97d-105">For more information about views, see [Views](../relational-databases/views/views.md).</span></span>  
  
## <a name="subscription-view-formats"></a><span data-ttu-id="fb97d-106">Formati di vista sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="fb97d-106">Subscription View Formats</span></span>  
 <span data-ttu-id="fb97d-107">Quando si crea una vista in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], è possibile effettuare una scelta da un set di formati di viste standard disponibili in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb97d-107">When you create a view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you choose from a set of standard view formats that [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] provides.</span></span> <span data-ttu-id="fb97d-108">Questi formati possono essere utilizzati per creare viste in cui sono visualizzati:</span><span class="sxs-lookup"><span data-stu-id="fb97d-108">You can use these formats to create views that show:</span></span>  
  
-   <span data-ttu-id="fb97d-109">Tutti i membri foglia e i relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="fb97d-109">All leaf members and their attributes.</span></span>  
  
-   <span data-ttu-id="fb97d-110">Tutti i membri consolidati e i relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="fb97d-110">All consolidated members and their attributes.</span></span>  
  
-   <span data-ttu-id="fb97d-111">Tutte le raccolte e i relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="fb97d-111">All collections and their attributes.</span></span>  
  
-   <span data-ttu-id="fb97d-112">I membri aggiunti in modo esplicito a una raccolta.</span><span class="sxs-lookup"><span data-stu-id="fb97d-112">The members explicitly added to a collection.</span></span>  
  
-   <span data-ttu-id="fb97d-113">I membri in una gerarchia derivata, in formato padre-figlio o a livelli.</span><span class="sxs-lookup"><span data-stu-id="fb97d-113">The members in a derived hierarchy, in either a parent child or level format.</span></span>  
  
-   <span data-ttu-id="fb97d-114">I membri in tutte le gerarchie esplicite per un'entità, in formato padre-figlio o a livelli.</span><span class="sxs-lookup"><span data-stu-id="fb97d-114">The members in all explicit hierarchies for an entity, in either a parent child or level format.</span></span>  
  
## <a name="subscription-views-can-become-out-of-date"></a><span data-ttu-id="fb97d-115">Le viste delle sottoscrizioni possono diventare non aggiornate</span><span class="sxs-lookup"><span data-stu-id="fb97d-115">Subscription Views Can Become Out-of-Date</span></span>  
 <span data-ttu-id="fb97d-116">Dopo avere creato una vista sottoscrizioni per un'entità o una gerarchia, le modifiche apportate agli oggetti modello associati non vengono applicate automaticamente nella vista.</span><span class="sxs-lookup"><span data-stu-id="fb97d-116">After you create a subscription view for an entity or hierarchy, changes to the associated model objects are not automatically reflected in the view.</span></span> <span data-ttu-id="fb97d-117">Può essere inoltre necessario rigenerare una vista sottoscrizioni in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] per applicare le modifiche apportate a oggetti modello.</span><span class="sxs-lookup"><span data-stu-id="fb97d-117">You might need to regenerate a subscription view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to reflect changes to model objects.</span></span> <span data-ttu-id="fb97d-118">La colonna **Modificato** nella pagina **Esporta** viene aggiornata a **Vero** quando gli oggetti modello cambiano.</span><span class="sxs-lookup"><span data-stu-id="fb97d-118">The **Changed** column on the **Export** page is updated to **True** when model objects change.</span></span> <span data-ttu-id="fb97d-119">**Vero** indica che è necessario modificare la vista sottoscrizioni e salvarla, in modo da rigenerarla.</span><span class="sxs-lookup"><span data-stu-id="fb97d-119">**True** indicates that you should edit the subscription view and save it, which regenerates the view.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fb97d-120">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="fb97d-120">Related Tasks</span></span>  
  
|<span data-ttu-id="fb97d-121">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="fb97d-121">Task Description</span></span>|<span data-ttu-id="fb97d-122">Argomento</span><span class="sxs-lookup"><span data-stu-id="fb97d-122">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="fb97d-123">Creare una vista sottoscrizioni dei dati master.</span><span class="sxs-lookup"><span data-stu-id="fb97d-123">Create a subscription view of your master data.</span></span>|[<span data-ttu-id="fb97d-124">Creare una vista sottoscrizioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fb97d-124">Create a Subscription View &#40;Master Data Services&#41;</span></span>](create-a-subscription-view-to-export-data-master-data-services.md)|  
|<span data-ttu-id="fb97d-125">Eliminare una vista sottoscrizioni esistente.</span><span class="sxs-lookup"><span data-stu-id="fb97d-125">Delete an existing subscription view.</span></span>|[<span data-ttu-id="fb97d-126">Eliminare una vista sottoscrizioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fb97d-126">Delete a Subscription View &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-subscription-view-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="fb97d-127">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="fb97d-127">Related Content</span></span>  
  
-   [<span data-ttu-id="fb97d-128">Formati di vista sottoscrizioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fb97d-128">Subscription View Formats &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/subscription-view-formats-master-data-services.md)  
  
-   [<span data-ttu-id="fb97d-129">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="fb97d-129">Views</span></span>](../relational-databases/views/views.md)  
  
  
