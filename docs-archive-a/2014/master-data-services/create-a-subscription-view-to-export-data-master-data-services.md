---
title: Creare una vista sottoscrizioni (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- subscription views [Master Data Services], creating
- creating subscription views [Master Data Services]
ms.assetid: a5e28961-af16-414a-9845-d2e06aac5214
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e5e2b901e56d75e97a444fd2858ef95872f3b766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635102"
---
# <a name="create-a-subscription-view-master-data-services"></a><span data-ttu-id="95cf2-102">Creare una vista sottoscrizioni (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="95cf2-102">Create a Subscription View (Master Data Services)</span></span>
  <span data-ttu-id="95cf2-103">Creare una vista sottoscrizioni quando si desidera creare una vista dei dati nel [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database per l'utilizzo da parte dei sistemi di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="95cf2-103">Create a subscription view when you want to create a view of your data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database for use by subscribing systems.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="95cf2-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="95cf2-104">Prerequisites</span></span>  
 <span data-ttu-id="95cf2-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="95cf2-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="95cf2-106">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Gestione integrazione** .</span><span class="sxs-lookup"><span data-stu-id="95cf2-106">You must have permission to access the **Integration Management** functional area.</span></span>  
  
-   <span data-ttu-id="95cf2-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="95cf2-107">You must be a model administrator.</span></span> <span data-ttu-id="95cf2-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="95cf2-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-subscription-view"></a><span data-ttu-id="95cf2-109">Per creare una vista sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="95cf2-109">To create a subscription view</span></span>  
  
1.  <span data-ttu-id="95cf2-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]fare clic su **Gestione integrazione**.</span><span class="sxs-lookup"><span data-stu-id="95cf2-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Integration Management**.</span></span>  
  
2.  <span data-ttu-id="95cf2-111">Dalla barra dei menu scegliere **Crea viste**.</span><span class="sxs-lookup"><span data-stu-id="95cf2-111">From the menu bar, click **Create Views**.</span></span>  
  
3.  <span data-ttu-id="95cf2-112">Nella pagina **viste sottoscrizioni** fare clic su **Aggiungi vista sottoscrizioni**.</span><span class="sxs-lookup"><span data-stu-id="95cf2-112">On the **Subscription Views** page, click **Add subscription view**.</span></span>  
  
4.  <span data-ttu-id="95cf2-113">Nella casella **nome vista** sottoscrizioni del riquadro **Crea vista sottoscrizioni** Digitare un nome per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="95cf2-113">In the **Create Subscription View** pane, in the **Subscription view name** box, type a name for the view.</span></span>  
  
5.  <span data-ttu-id="95cf2-114">Selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="95cf2-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="95cf2-115">Selezionare l'opzione **versione** o **flag versione** , quindi selezionare una voce dall'elenco corrispondente.</span><span class="sxs-lookup"><span data-stu-id="95cf2-115">Select either the **Version** or **Version Flag** option, and then select from the corresponding list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="95cf2-116">Creare una vista sottoscrizioni basata su un flag di versione.</span><span class="sxs-lookup"><span data-stu-id="95cf2-116">Create a subscription view based on a version flag.</span></span> <span data-ttu-id="95cf2-117">Quando si blocca una versione, è possibile riassegnare il flag a una versione aperta senza aggiornare la vista sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="95cf2-117">When you lock a version, you can reassign the flag to an open version without updating the subscription view.</span></span>  
  
7.  <span data-ttu-id="95cf2-118">Selezionare l'opzione **entità** o **gerarchia derivata** , quindi selezionare una voce dall'elenco corrispondente.</span><span class="sxs-lookup"><span data-stu-id="95cf2-118">Select either the **Entity** or **Derived hierarchy** option, and then select from the corresponding list.</span></span>  
  
8.  <span data-ttu-id="95cf2-119">Selezionare un formato di vista sottoscrizioni dall'elenco **Formato** .</span><span class="sxs-lookup"><span data-stu-id="95cf2-119">From the **Format** list, select a subscription view format.</span></span>  
  
9. <span data-ttu-id="95cf2-120">Se si sceglie **Livelli espliciti** o **Livelli derivati** dall'elenco **Formato** , digitare il numero di livelli della gerarchia da includere nella vista.</span><span class="sxs-lookup"><span data-stu-id="95cf2-120">If you chose **Explicit levels** or **Derived levels** from the **Format** list, type the number of levels in the hierarchy to include in the view.</span></span>  
  
10. <span data-ttu-id="95cf2-121">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="95cf2-121">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95cf2-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95cf2-122">See Also</span></span>  
 <span data-ttu-id="95cf2-123">[Esportazione dei dati &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="95cf2-123">[Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span></span>  
 <span data-ttu-id="95cf2-124">[Eliminare una vista sottoscrizioni &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="95cf2-124">[Delete a Subscription View &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span></span>  
 [<span data-ttu-id="95cf2-125">Creare un flag di versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="95cf2-125">Create a Version Flag &#40;Master Data Services&#41;</span></span>](create-a-version-flag-master-data-services.md)  
  
  
