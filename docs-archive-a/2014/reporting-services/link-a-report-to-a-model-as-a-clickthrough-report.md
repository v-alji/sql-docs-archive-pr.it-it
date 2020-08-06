---
title: Collegare un report a un modello come report click-through | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- customizing clickthrough reports
- clickthrough reports, customizing
- clickthrough reports, templates
ms.assetid: 3af42de3-67ef-41c2-bc8a-7045baec6f63
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cb84f8036dbe5a1694628144f0b948452261ca75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625207"
---
# <a name="link-a-report-to-a-model-as-a-clickthrough-report"></a><span data-ttu-id="4f9f1-102">Collegare un report a un modello come report click-through</span><span class="sxs-lookup"><span data-stu-id="4f9f1-102">Link a Report to a Model as a Clickthrough Report</span></span>
  <span data-ttu-id="4f9f1-103">Invece di utilizzare i modelli di report click-through predefiniti, è possibile creare un report con Generatore report e quindi collegarlo a un'entità specifica nel modello di report.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-103">Instead of using the default clickthrough report templates, you can create a Report Builder report and then link it to a specific entity in the report model.</span></span> <span data-ttu-id="4f9f1-104">Quando l'utente che visualizza il report fa clic sui dati interattivi nel report principale, questo report viene visualizzato come report click-through.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-104">When the person viewing the report clicks the interactive data in the main report, this report is displayed as a clickthrough report.</span></span> <span data-ttu-id="4f9f1-105">Per collegare un report a un'entità, utilizzare Gestione report di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9f1-105">To link a report to an entity, use [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4f9f1-106">L'entità primaria, o di base, che viene utilizzata nel report deve coincidere con quella a cui il report è collegato.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-106">The primary, or base, entity that is used in the report must to be the same entity to which the report is linked.</span></span>  
  
### <a name="to-start-report-manager-from-a-browser"></a><span data-ttu-id="4f9f1-107">Per avviare Gestione report da un browser</span><span class="sxs-lookup"><span data-stu-id="4f9f1-107">To start Report Manager from a browser</span></span>  
  
1.  <span data-ttu-id="4f9f1-108">Aprire [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-108">Open [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 or later.</span></span>  
  
2.  <span data-ttu-id="4f9f1-109">Nella barra degli indirizzi del browser digitare l'URL di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-109">In the address bar of the Web browser, type the Report Manager URL.</span></span> <span data-ttu-id="4f9f1-110">Per impostazione predefinita, l'URL è http:// \<*ComputerName*> /Reports.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-110">By default, the URL is http://\<*ComputerName*>/reports.</span></span>  
  
### <a name="to-create-a-customized-clickthrough-report"></a><span data-ttu-id="4f9f1-111">Per creare un report click-through personalizzato</span><span class="sxs-lookup"><span data-stu-id="4f9f1-111">To create a customized clickthrough report</span></span>  
  
1.  <span data-ttu-id="4f9f1-112">Passare al modello di report al quale si desidera aggiungere il report click-through personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-112">Navigate to the report model to which you want to add the customized clickthrough report.</span></span>  
  
2.  <span data-ttu-id="4f9f1-113">Fare doppio clic sul modello di report.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-113">Double-click the report model.</span></span>  
  
3.  <span data-ttu-id="4f9f1-114">Fare clic su **Click-through**.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-114">Click **Clickthrough**.</span></span>  
  
4.  <span data-ttu-id="4f9f1-115">Selezionare l'entità a cui associare il report click-through personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-115">Select the entity to which you want to attach the customized clickthrough report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f9f1-116">Questa entità deve corrispondere all'entità di base del report click-through personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-116">This entity must be the same as the base entity of the customized clickthrough report.</span></span>  
  
5.  <span data-ttu-id="4f9f1-117">Per visualizzare il report personalizzato quando viene selezionata una singola istanza dell'entità scelta, fare clic sul pulsante **Sfoglia** del report a istanza singola.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-117">To display the customized report when a single instance of the selected entity is clicked, click the Single instance report **Browse** button.</span></span>  
  
     <span data-ttu-id="4f9f1-118">-oppure-</span><span class="sxs-lookup"><span data-stu-id="4f9f1-118">-or-</span></span>  
  
     <span data-ttu-id="4f9f1-119">Per visualizzare il report personalizzato quando vengono selezionate più istanze dell'entità scelta, fare clic sul pulsante **Sfoglia** del report a più istanze.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-119">To display the customized report when a multiple instance of the selected entity is clicked, click the Multiple instance report **Browse** button.</span></span>  
  
6.  <span data-ttu-id="4f9f1-120">Selezionare il report, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-120">Select the report and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="4f9f1-121">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="4f9f1-121">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9f1-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f9f1-122">See Also</span></span>  
 [<span data-ttu-id="4f9f1-123">Report click-through &#40;&#41;SSRS</span><span class="sxs-lookup"><span data-stu-id="4f9f1-123">Clickthrough Reports &#40;SSRS&#41;</span></span>](reports/clickthrough-reports-ssrs.md)  
  
  
