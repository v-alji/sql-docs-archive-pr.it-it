---
title: Assegnare un flag a una versione (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], assigning flags
- versions [Master Data Services], assigning flags
ms.assetid: 6629ec7e-32e7-4a1e-8b31-eb43c5923766
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2de0d0d8d8ea96814e13b9123fe4fcd4782d6bef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637402"
---
# <a name="assign-a-flag-to-a-version-master-data-services"></a><span data-ttu-id="08fff-102">Assegnare un flag a una versione (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="08fff-102">Assign a Flag to a Version (Master Data Services)</span></span>
  <span data-ttu-id="08fff-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]assegnare un flag a una versione per indicare la versione che utenti o sistemi di sottoscrizione devono utilizzare.</span><span class="sxs-lookup"><span data-stu-id="08fff-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign a flag to a version to indicate the version that users or subscribing systems should use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08fff-104">I flag di versione possono essere solo assegnati a una versione alla volta.</span><span class="sxs-lookup"><span data-stu-id="08fff-104">Version flags can be assigned to only one version at a time.</span></span> <span data-ttu-id="08fff-105">Se si assegna un flag già assegnato a un'altra versione, il flag verrà spostato alla versione che si è selezionata.</span><span class="sxs-lookup"><span data-stu-id="08fff-105">If you assign a flag that is already assigned to another version, the flag is moved to the version you selected.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="08fff-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="08fff-106">Prerequisites</span></span>  
 <span data-ttu-id="08fff-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="08fff-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="08fff-108">È necessario avere l'autorizzazione per accedere all'area funzionale **Gestione versioni** .</span><span class="sxs-lookup"><span data-stu-id="08fff-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="08fff-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="08fff-109">You must be a model administrator.</span></span> <span data-ttu-id="08fff-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="08fff-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="08fff-111">È necessario aver creato un flag di versione da assegnare.</span><span class="sxs-lookup"><span data-stu-id="08fff-111">You must have created a version flag to assign.</span></span> <span data-ttu-id="08fff-112">Per altre informazioni, vedere [Creare un flag di versione &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="08fff-112">For more information, see [Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span></span>  
  
### <a name="to-assign-a-flag-to-a-version"></a><span data-ttu-id="08fff-113">Per assegnare un flag a una versione</span><span class="sxs-lookup"><span data-stu-id="08fff-113">To assign a flag to a version</span></span>  
  
1.  <span data-ttu-id="08fff-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Gestione versioni**.</span><span class="sxs-lookup"><span data-stu-id="08fff-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="08fff-115">Nella pagina **Gestisci versioni** nella riga per la versione a cui si vuole assegnare un flag, fare doppio clic sulla cella nella colonna **Flag** .</span><span class="sxs-lookup"><span data-stu-id="08fff-115">On the **Manage Versions** page, in the row for the version to which you want to assign a flag, double-click the cell in the **Flag** column.</span></span>  
  
3.  <span data-ttu-id="08fff-116">Nell'elenco selezionare il flag che si desidera assegnare.</span><span class="sxs-lookup"><span data-stu-id="08fff-116">From the list, select the flag you want to assign.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="08fff-117">Se il flag desiderato non è disponibile, è possibile che sia disponibile solo per le versioni con **Commit completato** .</span><span class="sxs-lookup"><span data-stu-id="08fff-117">If the flag you want is not available, the flag might be available for **Committed** versions only.</span></span> <span data-ttu-id="08fff-118">Per confermare, passare alla pagina **Gestisci flag di versione** e visualizzare il campo **Solo versioni con commit** per il flag.</span><span class="sxs-lookup"><span data-stu-id="08fff-118">To confirm, go to the **Manage Version Flags** page and view the **Committed Versions Only** field for the flag.</span></span>  
  
4.  <span data-ttu-id="08fff-119">Premere INVIO per salvare la modifica la formula.</span><span class="sxs-lookup"><span data-stu-id="08fff-119">Press ENTER to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08fff-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08fff-120">See Also</span></span>  
 <span data-ttu-id="08fff-121">[Creare un flag di versione &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="08fff-121">[Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span></span>  
 [<span data-ttu-id="08fff-122">Versioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="08fff-122">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  
